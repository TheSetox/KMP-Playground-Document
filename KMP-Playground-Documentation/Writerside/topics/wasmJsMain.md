# wasmJsMain

This is where you integrate the `commonMain` compose UI.

You can change specific UI requirement for web.

But most of the time, the `commonMain` can handle it.

## Sample Code

_main.kt_
```Kotlin
import androidx.compose.ui.ExperimentalComposeUiApi
import androidx.compose.ui.window.CanvasBasedWindow

@OptIn(ExperimentalComposeUiApi::class)
fun main() {
    CanvasBasedWindow(canvasElementId = "ComposeTarget") { 
        App() 
    }
}
```