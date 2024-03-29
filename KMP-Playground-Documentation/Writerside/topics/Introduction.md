# Kotlin Multiplatform Playground

This is a Kotlin Multiplatform project targeting Android, iOS, Web,
Desktop, Server.

## Kotlin Multiplatform with Compose Multiplatform (Main Structure)

```plantuml
@startuml

folder Project {
    folder composeApp {
        component androidMain as androidCompose
        component iosMain as iosCompose
        component commonMain as commonCompose
        component desktopMain as desktopCompose
        component webMain as webCompose
    }
    component iosApp
    folder shared {
        component androidMain
        component commonMain
        component iosMain
        component desktopMain
        component webMain
    }
    component server
}

"Android Entry Point" ---> androidCompose
"iOS Entry Point" --> iosApp
"web Entry Point" ---> webCompose
"Desktop Entry Point" ---> desktopCompose
"Server Entry Point" --> server

commonCompose --> commonMain

iosApp --> iosCompose

commonMain --> iosMain
commonMain --> androidMain
commonMain --> desktopMain
commonMain --> webMain

server -> commonMain

iosCompose --> commonCompose
androidCompose --> commonCompose
desktopCompose --> commonCompose
webCompose --> commonCompose

@enduml
```