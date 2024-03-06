# DataSource.android

## getPlatform

```Kotlin
    actual override fun getPlatform(): Platform {
        val platformName = "Android ${Build.VERSION.SDK_INT}"
        return Platform(platformName)
    }
```

This code snippet overrides the `getPlatform()` function with a 
platform-specific implementation for Android. 

It constructs a `Platform` object with the platform name containing the 
current Android SDK version retrieved using `Build.VERSION.SDK_INT`, 
and returns it. 

This allows for differentiation between platforms while maintaining a 
unified interface in Kotlin Multiplatform projects.