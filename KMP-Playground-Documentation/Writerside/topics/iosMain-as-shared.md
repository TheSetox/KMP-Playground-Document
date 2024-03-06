# iosMain

Holds platform-specific code for iOS within the shared module.

> Right now, there is nothing added here.
{style="note"}

## Expected Diagram Result

```plantuml
@startuml

component composeApp

folder shared {
    folder commonMain {
        component ViewModel as common
    }
    folder iosMain {
        component ViewModel as ios
    }
}


composeApp --> common
common -> ios

@enduml
```