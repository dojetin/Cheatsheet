# Scripting in PowerShell

Verificar: Get-ExecutionPolicy
Aplicar: Set-ExecutionPolicy RemoteSigned
Aplicar: Set-ExecutionPolicy Unrestricted
Verificar: Get-ExecutionPolicy

Bypass temporal del script: powershell.exe -ExecutionPolicy Bypass Ejemplo.ps1

## Ver Servicios en ejecución
Get-Service | Where-Object {$_.Status -eq "Running"}

## TOP10 Servicios en ejecución
Get-Service | Where-Object {$_.Status -eq "Running"} | Sort-Object -Property DisplayName | Select-Object -Property Displayname, Name, ServcesDependedOn -First 10

## Ver Procesos que empiecen por la letra "S"
Get-Process -Name s* | Select-Object ProcessName -Unique

## Ver Procesos que empiecen por la letra "S", con datos de tiempo
Get-Process S* | Select-Object Processname, StartTime, @{Name="Horas en ejecucion";Expression={((Get-Date) - $_.StartTime).Hours}} -Unique

## Personalización de la salida
Get-Service s* | Sort-Object Status | Format-Table Name, DisplayName, @{Name="Estado";Expression={if ($_.status -eq "running") {"Ejecutando"} else {"Parado"}}}

## Exportar a un fichero 
Get-Service s* | Out-File servicios.txt

## Primer script en PowerShell
Write-Output “Hello World”

## Pedir Nombre y saludar
$var1 = “Hola ”
$var2 = Read-Host “¿Cómo te llamas?”
$var1 + $var2

## For
For ($a=1; $a –le 100; $a++) {echo $a}

## If
If (Get-ChildItem –File = "C:\Users\Server\Downloads\resultado.txt") {echo OK} Else {echo NOT OK}

## Scripts en Registros del sistema
Get-ChildItem HKCU:

## Crear una carpeta
New-Item -Path 'C:\temp\NewFolder' -ItemType Directory

## Reproducir con voz
$a = New-Object –ComObject SAPI.SPVoice
$a. speak(“Hola amigos de fesac, hablo mejor que loquendo”)

