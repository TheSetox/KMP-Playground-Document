# DataSource.ios

## getPlatform

```Kotlin
    actual override fun getPlatform(): Platform {
        val platformName = UIDevice.currentDevice.systemName() + " " +
                UIDevice.currentDevice.systemVersion
        return Platform(platformName)
    }
```

This code snippet provides a platform-specific implementation of the 
`getPlatform()` function for iOS in a Kotlin Multiplatform project. 

Utilizing the `actual override` keywords, it retrieves the system name and 
version of the iOS device using `UIDevice.currentDevice.systemName()` 
and `UIDevice.currentDevice.systemVersion`, respectively. 

Then, it constructs a `Platform` object with the obtained platform information 
and returns it. 

This approach enables customization based on platform specifics while 
maintaining a consistent interface across different platforms.