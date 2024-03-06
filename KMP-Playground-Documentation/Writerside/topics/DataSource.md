# DataSource

a `DataSource` handles interactions with external data sources like 
databases or APIs. It abstracts away the details of data access 
and provides a simple interface for the rest of the application. 

This separation of concerns keeps the inner layers focused on business 
logic and ensures flexibility in adapting to changes in data sources.

## getPlatform

```Kotlin
expect class DataSource(): Source {
    override fun getPlatform(): Platform
}
```

This code snippet defines an `expect` class named `DataSource`, 
which serves as an abstraction for a data source in a Kotlin Multiplatform project. 

It declares a method `getPlatform()` that returns a `Platform` object. 

The implementation of this method is left abstract, 
indicated by the absence of a body in the declaration. 

This allows platform-specific implementations to be provided 
in platform-specific modules using the `actual` keyword. 

Overall, the `expect` keyword defines a platform-independent 
interface or declaration that must be implemented by platform-specific code.