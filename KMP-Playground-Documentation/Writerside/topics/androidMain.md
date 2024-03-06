# androidMain

In `androidMain`, you don't need to add the specific composable
item. Because we can create that in the `commonMain` instead.

But if there is any special requirement that requires
`androidMain`, then we can add more implementation here.

## Running the App

In Compose Multiplatform, you don't need a separate module
for the `androidApp`. It is already included in this module.

So you can run specific gradle files in the `composeApp` module
to run the `androidApp` or use the IDE.

## Sample Code

_MainActivity.kt_
```Kotlin
package org.example.project

import App
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.runtime.Composable
import androidx.compose.ui.tooling.preview.Preview

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            App()
        }
    }
}

@Preview
@Composable
fun AppAndroidPreview() {
    App()
}
```