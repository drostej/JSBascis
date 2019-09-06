# Descrution Pattern bei js Objekten
 const { statusCode } = response;
 // hier wird eine Konstante mit dem Namen statusCode erzeugt, die einem Feld statusCode in der
 // response entspricht

tutorials
https://pouchdb.com/2015/05/18/we-have-a-problem-with-promises.html

## Prüfen ob neue libraries zur Verfügung stehen
npm-check

## NPM Check global installieren
$ npm install -g npm-check

## Testing

expect und mocha

Das in die package.json


"scripts": {
    "test": "mocha"
  }


## Intellij shortcuts

Für unitTests den Konfigorder in das Projektroot

ALT + Shift + Cursor - blockweise verschieben

Alt + Apfel + L  = Intellij autoformat

Apfel + F12 = Strukturübersicht

Apfel + D   = Kopieren und direkt den markierten Text davorsetzeen 

Apfel + klick auf eine Deklaraion = In den code springen  
  
Apfel + / im Nummernblock - blockweise kopieren

## aws
### url für den tef account
https://tefde-ccm-infra-user.signin.aws.amazon.com/console



###Zugriff auf den ci runner
ssh -i "gitlab_ci_runner_key.pem" ec2-user@172.18.197.121



## docker

docker build -f ./docker/postgres/Dockerfile .
docker run -d -p 5432:5432 postgres_for_consent

Successfully built 819a13b10470

docker-compose -f docker-housekeeping.yml up

### docker build 
erzeugt man aus einem dockerfile ein dockerimage
Empfohlene Optoin -t = tag und das Zielverzeichnis, in dem das eingetragen wird


#### docker images
Liste aller images

### mit docker run

Mit jedem docker run erhöt sich sich anzahl des betreffenden Conainerimages. Das ist mit docker ps --all 
vollziehbar.

Auf ein Image anzuwenden => erzeugt einen conainer auf der basis eines images
 
 Beispiel
 'docker run hks-housekeeping '
 
 Mit docker run kann ein enviroment mitgegeben werden wie env, -p 5432:5432 etc....

### start oder stop 
vorhandene Container starten und stoppen

## docker compose (Beispiel siehe Anhang)
docker-compose up

##  docker-compose ps
Prüfen ob alle container hochgefahren sind


## Mit network könnte im Nachgang eine komplexere Netzwerkumgebung konfigurieret werden, wenn 
sie kurz zeitverzögert danach aufgerufen würde

###
Arbeit mit den docker containern (3d45 steht für die Container ID)
docker inspect 3d45 - hier lässt sich die IP Adresse beispielsweise auslesen und mit welchem enviroment gearbeitet wurde
=> ermitteltes 

docker docker exec -it 7d000118a4ff bash


## aws
https://eu-central-1.console.aws.amazon.com/ecs/home?region=eu-central-1#/repositories/tefde-ccm-docker:coms:hks-housekeeping#images;tagStatus=ALL

Nicht vergessen auf die Rolle PowerUserAccess gewechselt wird


## kubernetes 
https://api.coms-dev.aws.de.pri.o2.com/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/log/consms-dev/hks-housekeeping-77b76dc797-xn4ln/pod?namespace=consms-dev

Um den richtigen Fokus zu erhalten wählt man nach dem login namespace -> consms -> overview -> Übersicht über Instanzen und Logfiles

In dem dashboard auf workload klicken. In den pods das logs Menü (ähnlich eines Burgermenüs) anlicken.
Mit dem "weiteres" Menü kann der Container gelöscht oder anderes getan werden.

### url
https://api.coms-dev.aws.de.pri.o2.com/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/overview?namespace=default


## gitlab

```git checkout feature-COMS-102-Multiple-Oneclicks
cd api-consent
npm version prerelease
cd ..
cd demo-app
npm version prerelease
git commit -a -m “version bump”
git push
````

## code coverage
