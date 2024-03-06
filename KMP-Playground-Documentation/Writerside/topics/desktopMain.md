# desktopMain

This is the start of the `desktopMain`.

You can add more UI specific to desktopMain or
combine multiple composable.

## Running the desktop app

There will be a play or run button beside
`main` to be able to run the desktop app.

or you can use the gradle script under
composeApp `run/desktopRun`.

## Sample Code

_main.kt_
```Kotlin
import androidx.compose.runtime.Composable
import androidx.compose.ui.window.Window
import androidx.compose.ui.window.application

fun main() = application {
    Window(
        onCloseRequest = ::exitApplication, 
        title = "SampleMultiplatform"
    ) {
        App()
    }
}
```