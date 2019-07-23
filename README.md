 
# SonarQube  Instalacion

## Requisitos

```
1. Docker
2. Python + PIP
```

## Instalacion SonarQube

```
1. docker run -d --name sonarqube -p 9000:9000 sonarqube
2. Default you can login as admin with password admin.
```

## Instalacion SonarQube Scanner

```
1. Descargar SonarQube Scanner 
https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner
```

## Instalacion PyLint

```
1. sudo apt-get install pylint # Debian https://www.pylint.org/#install
```

## Instalacion Bandit

```
1. pip3 install bandit # https://github.com/PyCQA/bandit
```

## Extencion de reglas

Las reglas por defectos en sonarqube para Python son minimas. 

```
Rules Active Inactive
Total 437 2
Bugs 12 0
Vulnerabilities 0 0
Code Smells 415 2
Security Hotspots 10 0
```

Es por ello que se debe extender esta clase de reglas y activar todas las relacionadas a Python.


## Import Bandit Issues Reports

```
1. bandit --format json --output bandit-report.json --recursive /path/to/your/python/project
```

## Import Pylint Issues Report


```
1. pylint <module_or_package> -r n --msg-template="{path}:{line}: [{msg_id}({symbol}), {obj}] {msg}" > <report_file> 
```

## Creacion archivo configuracion

1. Creacion dentro de la carpeta del proyecto el archivo sonar-project.properties,

```
sonar.projectKey=solpro:python
sonar.projectName=SolPRO Python
sonar.projectVersion=1.0
sonar.sources=.
sonar.language=py
sonar.sourceEncoding=UTF-8
sonar.host.url=http://0.0.0.0:9000
sonar.python.bandit.reportPaths=/<path>/bandit-report.json
sonar.python.pylint.reportPath=/<path>/pylint-report.txt
```

## Ejecucion SonarQube


```
1. Ingresar carpeta de proyecto y ejecutar
2. /<path>/sonar-scanner
```
