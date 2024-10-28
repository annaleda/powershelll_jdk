# powershelll_jdk

$url = "https://download.oracle.com/java/23/latest/jdk-23_windows-x64_bin.zip"
$output = "$env:TEMP\jdk-23_windows-x64_bin.zip"
Invoke-WebRequest -Uri $url -OutFile $output

Expand-Archive -Path $output -DestinationPath "C:\Program Files\Java\jdk-23"

$env:JAVA_HOME = "C:\Program Files\Java\jdk-23"
[System.Environment]::SetEnvironmentVariable("JAVA_HOME", $env:JAVA_HOME, [System.EnvironmentVariableTarget]::Machine)

$newPath = "$env:JAVA_HOME\bin;$env:Path"
[System.Environment]::SetEnvironmentVariable("Path", $newPath, [System.EnvironmentVariableTarget]::Machine)

--CAMBIA LE VARIABILI DELLA 23 PER LASCIARTELE

--JDK 11
Expand-Archive -Path "C:\Users\annaleda\Downloads\jdk-11.0.24+8-windows-x64.zip" -DestinationPath "C:\Program Files\Java\jdk-11.0.24"
$env:JAVA_HOME = "C:\Program Files\Java\jdk-11.0.24"
[System.Environment]::SetEnvironmentVariable("JAVA_HOME", $env:JAVA_HOME, [System.EnvironmentVariableTarget]::Machine)

$newPath = "$env:JAVA_HOME\bin;$env:Path"
[System.Environment]::SetEnvironmentVariable("Path", $newPath, [System.EnvironmentVariableTarget]::Machine)
