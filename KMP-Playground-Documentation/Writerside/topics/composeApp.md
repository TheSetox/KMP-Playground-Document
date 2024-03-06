# composeApp

`composeApp module` is for code that will be shared across 
your Compose Multiplatform applications. 

It contains several subfolders:

- `commonMain` is for code that’s common for all targets.
- Other folders are for Kotlin code that will be compiled for 
only the platform indicated in the folder name. 
For example, if you want to use Apple’s CoreCrypto for the iOS 
part of your Kotlin app, iosMain would be the right folder for 
such calls.

```plantuml
@startuml

component iosApp
folder composeApps {
    component androidMain
    component iosMain
    component commonMain
    component desktopMain
    component wasmJsMain
}

"iOS Entry Point" --> iosApp
iosApp --> iosMain
iosMain --> commonMain

"Android Entry Point" --> androidMain
androidMain --> commonMain

"Desktop Entry Point" --> desktopMain
desktopMain --> commonMain

"Web Entry Point" --> wasmJsMain
wasmJsMain --> commonMain

commonMain --> "shared module(Exit to next module)"

@enduml
```