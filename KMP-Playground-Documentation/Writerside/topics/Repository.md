# Repository

A Repository Interface defines methods for accessing and 
managing data in a standardized way, abstracting 
underlying data storage mechanisms.

## Repository Interface

```Kotlin
interface Repository {
    fun getPlatform(): Platform
}
```

### Get Platform object

```Kotlin
fun getPlatform(): Platform
```

An interface to get the `Platform` object.

### Platform object

```Kotlin
data class Platform(
    val name: String
)
```

`Platform` object only have a `name`.

> In the future, we will move this to a different
> file. But right now, it is included in the 
> `Repository` file.
{style="note"}