# Main Goal

The main goal of this project is to showcase how we
can integrate a Modularize structure following Fun 
Clean Architecture in Kotlin Multiplatform.

> This is not meant for one fit size solution for your
> application. 
> 
> This is meant for exploring modularization
> and showcasing Fun Clean Architecture in Kotlin Multiplatform.
> 
> It is better to evaluate your application before
> incorporating any architecture design.
{style="warning"}

## Expected Architecture when Finished

The goal is to create a design that is similar to the
diagram below:


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
        folder androidMain {
            component AndroidViewModel
        }
        folder commonMain {
            component ViewModel as commonViewModel
        }
        folder iosMain {
            component ViewModel as iosViewModel
        }
        folder desktopMain {
            component ViewModel as desktopViewModel
        }
        folder webMain {
            component ViewModel as webViewModel
        }
    }
    component server
    folder domain {
        component UseCase
        component Repository
    }
    folder shared-data {
        folder commonMain as commonData {
            component DataRepository
            component Source
            component DataSource
        }
        folder androidMain as androidData {
            component DataSource as AndroidSource
        }
        folder iosMain as iosData {
            component DataSource as iOSSource
        }
        folder webMain as webData {
            component DataSource as webSource
        }
        folder desktopMain as desktopData {
            component DataSource as desktopSource
        }
    }
}

"Android Entry Point" ---> androidCompose
"iOS Entry Point" --> iosApp
"web Entry Point" ---> webCompose
"Desktop Entry Point" ---> desktopCompose
"Server Entry Point" --> server

iosApp --> iosCompose

iosCompose --> commonCompose
androidCompose --> commonCompose
desktopCompose --> commonCompose
webCompose --> commonCompose

commonCompose --> commonViewModel


commonViewModel --> iosViewModel
commonViewModel -> AndroidViewModel
commonViewModel ---> desktopViewModel
commonViewModel ---> webViewModel

commonViewModel --> UseCase

server -> UseCase
UseCase --> Repository

Repository ..> DataRepository
DataRepository --> Source
Source ..> DataSource

DataSource -> AndroidSource
DataSource --> iOSSource
DataSource --> desktopSource
DataSource --> webSource


@enduml
```
