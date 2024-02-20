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

If you want to use the plugins without version, you can use the following code in your settings.gradle file:

Add the following code to your gradle.properties file:
```properties (gradle.properties)
devnuxsPluginVersion=0.1.1
```

Add the following code to your settings.gradle file:
```groovy (settings.gradle)
pluginManagement {
    repositories {
        gradlePluginPortal()
        maven {
            url 'https://git.drmaniac.de/api/packages/repository/maven'
        }
    }
    resolutionStrategy {
        eachPlugin {
            if (requested.id.namespace == 'org.devnuxs') {
                useModule("org.devnuxs.${requested.id.name}:org.devnuxs.${requested.id.name}.gradle.plugin:${devnuxsPluginVersion}")
            }
        }
    }
}
```

Then you can use the plugins without version in your build.gradle file:
```groovy (build.gradle)
plugins {
    id 'org.devnuxs.java'
    id 'org.devnuxs.java17'
    id 'org.devnuxs.java21'
    id 'org.devnuxs.spotless'
    id 'org.devnuxs.release'
    id 'org.devnuxs.repo'
    id 'org.devnuxs.quarkus'
    id 'org.devnuxs.quarkus-k8'
    id 'org.devnuxs.openapi'
}
```