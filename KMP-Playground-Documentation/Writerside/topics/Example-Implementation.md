# Example Implementation

This a basic example on creating a server in **Ktor**.

```Kotlin
fun main() {
    embeddedServer(
        Netty,
        port = SERVER_PORT,
        host = "0.0.0.0",
        module = Application::module
    ).start(wait = true)
}

fun Application.module() {
    routing {
        get("/hello") {
            call.respondText("Ktor: ")
        }
    }
}
```