# JavaFX Game Project

This project is a JavaFX-based game built with Maven, leveraging the JavaRush game engine library. The purpose of this project is to create a runnable jar file containing all dependencies and resources, providing a standalone execution for the game. And show ability to set up Maven dependencies and plugins in other projects. 

## Key Features
- **Built with JavaFX**: Utilizes JavaFX for UI and graphics rendering.
- **JavaRush Game Engine**: Implements game logic and physics using the `desktop-game-engine` library.
- **JUnit Integration**: Includes unit tests using JUnit 5 for reliable code quality.
- **Standalone Execution**: Produces a runnable JAR file containing all necessary dependencies.

## Dependencies
The following dependencies are configured in the `pom.xml` file:

- **Apache Commons Lang**: `org.apache.commons:commons-lang3:3.12.0`
- **JavaFX Controls**: `org.openjfx:javafx-controls:18.0.1`
- **JavaRush Game Engine**: `com.javarush:desktop-game-engine:1.0`
- **JUnit Jupiter Engine** (scope test): `org.junit.jupiter:junit-jupiter-engine:5.8.2`

## Maven Plugins
The project is configured with several Maven plugins:

1. **Dependency Installation Plugin**: Adds `com.javarush:desktop-game-engine:1.0` from the `lib` directory to the local Maven repository.
2. **Maven Compiler Plugin**: Ensures the project is compiled with the specified Java version.
3. **Maven Jar Plugin**: Creates a JAR file with the following `MANIFEST.MF` sections:
    - **Class-Path**: Lists all JAR dependencies.
    - **Main-Class**: Set to `org.eclipse.jdt.internal.jarinjarloader.JarRsrcLoader`.
    - **Rsrc-Main-Class**: Set to `com.javarush.games.racer.RacerGame`.
4. **Maven Surefire Plugin**: Configures tests, excluding the `StrangeTest` while allowing all other tests to run.

## Resources
A resources section is added to the `pom.xml` file to ensure that compiled JAR dependencies are packaged within the resulting JAR under the `lib/` directory.

## Build and Run Instructions
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd project-maven
   ```

2. Install dependencies:
   ```bash
   mvn install
   ```

3. Build the project:
   ```bash
   mvn package
   ```

4. Run the generated JAR file:
   ```bash
   java -jar target/<jar-file-name>.jar
   ```

## Project Structure
- `src/main/java`: Contains the game source code.
- `src/test/java`: Includes unit tests.
- `lib`: Directory for the `desktop-game-engine` library.
- `pom.xml`: Maven configuration file.

## Final Output
The build process generates a JAR file that:
- Embeds all required dependencies in the `lib/` folder.
- Configures the MANIFEST.MF file for standalone execution.
- Excludes `StrangeTest` during the testing phase.

---

This project demonstrates a complete Maven build pipeline for a JavaFX game, including dependency management, plugin configuration, and JAR packaging. By following the steps outlined above, you can build and run the game on your local machine.
