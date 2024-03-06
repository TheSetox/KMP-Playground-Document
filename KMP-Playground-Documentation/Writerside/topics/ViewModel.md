# ViewModel
<show-structure for="chapter,procedure" depth="3"/>

the ViewModel acts as a mediator between the UI layer and the domain layer, which contains the business logic. 
It focuses solely on managing the presentation logic, handling user interactions, and updating the UI 
accordingly.

## Current code

> This is under evaluation and incomplete.
{style="note"}

_ViewModel.kt_
```Kotlin
class ViewModel(private val mainScreen: MainScreen = MainScreen()) {

    fun getState(): MainState {
        val result = mainScreen fetches platformName
        return result.reduceToState()
    }
}

fun String.reduceToState(): MainState {
    val state = MainState()
    if (isEmpty()) state.error = "Error can't fetch data"
    if (isNotEmpty()) state.success = this
    return state
}

class MainScreen(private val repository: Repository = DataRepository()) {
    infix fun fetches(useCase: Repository.() -> String): String {
        return repository.useCase()
    }
}

data class MainState(
    var success: String = "",
    var error: String = ""
)
```

### ViewModel
{collapsible="true" default-state="expanded"}
```Kotlin
class ViewModel(private val mainScreen: MainScreen = MainScreen()) {

}
```

The `ViewModel` class encapsulates the logic for managing data and state transitions within the application. 

It interacts with the `MainScreen` to fetch platform-specific data and then processes it to derive the 
application's current state.

#### getState
{collapsible="true" default-state="expanded"}
```Kotlin
    fun getState(): MainState {
        val result = mainScreen fetches platformName
        return result.reduceToState()
    }
```
The `getState` function within the `ViewModel` class retrieves the current state of the application. 

It delegates the task of fetching platform-specific data to the `MainScreen`, then processes the result 
to derive the application state using the `reduceToState` extension function.

### reduceToState
{collapsible="true" default-state="expanded"}
```Kotlin
fun String.reduceToState(): MainState {
    val state = MainState()
    if (isEmpty()) state.error = "Error can't fetch data"
    if (isNotEmpty()) state.success = this
    return state
}
```

The `reduceToState` extension function operates on a `String` object, transforming it into a 
`MainState` object based on certain conditions. 

- If the string is **empty**, it sets an error message in the state indicating data retrieval failure. 
- If the string is **not empty**, it sets the success message in the state with the retrieved data.

### MainScreen
{collapsible="true" default-state="expanded"}
```Kotlin
class MainScreen(private val repository: Repository = DataRepository()) {
    infix fun fetches(useCase: Repository.() -> String): String {
        return repository.useCase()
    }
}
```

The `MainScreen` class serves as an entry point for fetching platform-specific data. 

It delegates data retrieval tasks to a `Repository` implementation and provides a convenient 
DSL-style function `fetches` for invoking data retrieval use cases.

### MainState
{collapsible="true" default-state="expanded"}
```Kotlin
data class MainState(
    var success: String = "",
    var error: String = ""
)
```

The `MainState` data class represents the current state of the application. 

It contains fields to hold success and error messages, providing a structured way to 
communicate the outcome of data retrieval operations to other components in the application.

