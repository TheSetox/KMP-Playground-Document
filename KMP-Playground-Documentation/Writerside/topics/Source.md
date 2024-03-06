# Source

The `Source` interface defines a blueprint for classes in a 
Kotlin Multiplatform project. 

It serves as a placeholder for common functionality or
behavior that these classes should implement

## getPlatform

```Kotlin
expect class DataSource(): Source {
    override fun getPlatform(): Platform
}
```

This code snippet defines an interface named `Source`,
which serves as a contract for classes that provide platform-specific information.

It declares a method `getPlatform()` that returns a `Platform` object.

Classes implementing this interface are required to provide their
own implementation of the `getPlatform()` method.

This interface can be used as a common abstraction for platform-specific
functionality in a Kotlin Multiplatform project.