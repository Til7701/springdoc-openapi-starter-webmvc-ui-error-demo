# springdoc-openapi 2.8.7 Error Demo

This is a quick demonstration of an error occurring when opening the swagger ui with
springdoc-openapi to 2.8.7.

This error is caused by defining a default value for anything.

The issue can be fixed by registering the `Jdk8Module` with the `ObjectMapper` like this `Json31.mapper().registerModule(new Jdk8Module());`.

## Discovery

The error was reported here: https://github.com/swagger-api/swagger-core/issues/4903

## Building the project

This project is written in Java 21 and uses Maven as its build tool.
To build the project, you need to have Java 21 installed.
Clone this repository and run the following command in the root directory of the project:

```bash
./mvnw clean install package
```

## OpenAPI

This project uses OpenAPI to document the API and generate the server code.
The OpenAPI Document is located [here](https://github.com/uol-esis/TH1-OpenAPI).
You can read up on OpenAPI and the specification [here](https://spec.openapis.org/oas/v3.0.3) and use the
[Reference Guide](https://swagger.io/docs/specification/v3_0/about/) by Swagger.

To generate the server code we are using the OpenAPI Generator via the Maven plugin.
You can find the documentation for the Java generator [here](https://openapi-generator.tech/docs/generators/java/).

If you want to run the project for the first time or have made changes to the OpenAPI specification, you need to
generate the server code. You can do this by running the following command:

```bash
./mvnw clean compile
```

After generating the server code, you can run the project as described above.
While the project is running, you can access the Swagger UI at http://localhost:8080/swagger-ui/index.html

> **Note:** If you are using an IDE, you might have to set `target/generated-sources/openapi/src/main/java` as a
> generated sources root to avoid compilation errors.
