# WeGrow

WeGrow is a Java project with a Maven build configured for a Spring MVC web application. It targets Java 17 and produces a deployable WAR archive.

The project is currently an initial scaffold: Spring dependencies and WAR packaging are configured, and `Main.java` contains a small console example. Application controllers, pages, and business features have not been implemented yet.

## Technology stack

| Component | Version / configuration |
| --- | --- |
| Java | 17 target |
| Spring Context & Spring MVC | 6.2.12 |
| Jakarta Servlet API | 6.0.0, provided by the servlet container |
| Build tool | Apache Maven |
| Packaging | WAR (`wegrow.war`) |

## Getting started

Install a JDK 17 or newer and Apache Maven, then confirm they are available in your terminal:

```sh
java -version
mvn -version
```

Clone the repository:

```sh
git clone https://github.com/ezraidimariam/WeGrow.git
cd WeGrow
```

Build the project:

```sh
mvn clean package
```

Maven downloads the required dependencies on the first build. The generated archive is `target/wegrow.war`.

## Run the console example

After building, run the existing example:

```sh
java -cp target/classes org.example.Main
```

It prints a welcome message followed by the numbers 1 through 5. You can also run `Main.java` directly from your IDE.

## Web deployment

The WAR is intended for a Jakarta Servlet 6.0-compatible container. The Servlet API dependency is marked `provided`, so the deployment container must supply it.

The scaffold does not yet configure a Spring MVC dispatcher, controllers, or web pages. Building the WAR therefore does not provide a usable web interface yet. Once web initialization and routes are added, deploy `target/wegrow.war` through your container's normal deployment process.

## Project layout

```text
WeGrow/
├── pom.xml                              # Dependencies and Maven build configuration
├── src/main/java/org/example/Main.java  # Console example
└── target/                              # Generated build output (ignored by Git)
```

## Development commands

```sh
mvn compile       # Compile Java sources
mvn test          # Run tests when test sources are added
mvn clean package # Rebuild the WAR from scratch
```

When contributing, keep changes focused, describe their purpose, and verify the Maven build before opening a pull request.
