# UseCase

A Use Case outlines specific actions a system takes 
to achieve a goal, detailing interactions between 
users and the system.

## Getting the Platform name.

```Kotlin
val platformName: Repository.() -> String = {
    // Return
    getPlatform().name
}
```

This is to showcase how we can get the platform name.

we have used a high-order function that is stored
in a variable.

The high-order function uses extension function to be 
able to use the functionality of the `Repository`.