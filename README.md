# OpenLiberty + Vaadin Demo

## How to run

### Developing
* ``mvn vaadin:prepare-frontend``
* ``mvn`` (automatically calls default goal ``liberty:run``)
* You can also run it [in dev mode](https://openliberty.io/guides/maven-intro.html#running-the-application) using ``mvn liberty:dev``

### Production
* To create an executable jar run ``mvn clean package liberty:create liberty:install-feature liberty:deploy liberty:package -P production -Dinclude=minify,runnable``

## Remarks and conclusions
OpenLiberty was designed for MicroServices. Vaadin is not a microservice.

* Due to some reason every output of the OpenLiberty is getting translated - This makes looking up errors more difficult
* [Vaadin Live Reload](https://vaadin.com/docs/latest/configuration/live-reload) does not support OpenLiberty's dev mode 
* The system is way to complex. E.g. [when building a JAR](https://stackoverflow.com/a/67027769)
* There are inconveniences from AppServers (e.g. no main-Method)
* The production JAR is big (~130MB) and slow to start (~15s)
* Spring Boot (or Quarkus) can do the same but better, are easier to use and have more widespread usage
