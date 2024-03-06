# DataSource.wasmJs

## getPlatform

```Kotlin
    actual override fun getPlatform(): Platform {
        val platformName = "Web with Kotlin/Wasm"
        return Platform(platformName)
    }
```


This code snippet showcases a platform-specific implementation of the 
`getPlatform()` function for web browsers using Kotlin/Wasm (WebAssembly) 
in a Kotlin Multiplatform project. 

It constructs a `Platform` object with the platform name set to 
"Web with Kotlin/Wasm" and returns it. 

The `actual override` keywords indicate that this function provides a 
platform-specific implementation, allowing for differentiation between 
platforms while maintaining a consistent interface across 
Kotlin Multiplatform projects.