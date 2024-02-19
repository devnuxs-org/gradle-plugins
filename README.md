# gradle-plugins

gradle wrapper plugins with good default settings

# Available plugins
## General plugins
| Plugin | Description | Includes | Based on |
| ------ | ----------- | -------- | -------- |
| org.devnuxs.java | Java plugin without toolchain | org.devnuxs.spotless | java |
| org.devnuxs.java17 | Java plugin with toolchain for Java 17 | org.devnuxs.spotless | org.devnuxs.java |
| org.devnuxs.java21 | Java plugin with toolchain for Java 17 | org.devnuxs.spotless | org.devnuxs.java |
| org.devnuxs.spotless | Spotless plugin | | com.diffplug.spotless |
| org.devnuxs.release | Release plugin with default settings | | pl.allegro.tech.build.axion-release |
| org.devnuxs.repo | Repository plugin with default settings for drmaniacs repository | | - |

## Quarkus plugins
| Plugin | Description | Includes | Based on |
| ------ | ----------- | -------- | -------- |
| org.devnuxs.quarkus | Quarkus plugin with latest quarkus version | org.devnuxs.java21 | io.quarkus |
| org.devnuxs.quarkus-k8 | Quarkus plugin with latest quarkus version and pre configured kubernetes deployment for drmaniac | | org.devnuxs.quarkus |

## Generator plugins
| Plugin | Description | Includes | Based on |
| ------ | ----------- | -------- | -------- |
| org.devnuxs.openapi | OpenAPI plugin to generate client and server code | | org.openapi.generator |



# How to use
## General plugins
### Java plugin
```groovy
plugins {
    id 'org.devnuxs.java' version '1.0.0'
}
```
### Java 17 plugin
```groovy
plugins {
    id 'org.devnuxs.java17' version '1.0.0'
}
```
### Java 21 plugin
```groovy
plugins {
    id 'org.devnuxs.java21' version '1.0.0'
}
```
### Spotless plugin
```groovy
plugins {
    id 'org.devnuxs.spotless' version '1.0.0'
}
```
### Release plugin
```groovy
plugins {
    id 'org.devnuxs.release' version '1.0.0'
}
```
### Repository plugin
```groovy
plugins {
    id 'org.devnuxs.repo' version '1.0.0'
}
```
## Quarkus plugins
### Quarkus plugin
```groovy
plugins {
    id 'org.devnuxs.quarkus' version '1.0.0'
}
```
### Quarkus k8 plugin
```groovy
plugins {
    id 'org.devnuxs.quarkus-k8' version '1.0.0'
}
```
## Generator plugins
### OpenAPI plugin
```groovy
plugins {
    id 'org.devnuxs.openapi' version '1.0.0'
}
```
