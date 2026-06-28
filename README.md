# HFDInstaller

HFDInstaller is a standalone installer for **Harambe Final Destination**, a Minecraft Java server project.

This project is a modified fork of the Essential Installer source code. It has been adapted for use with Harambe Final Destination and is not affiliated with, endorsed by, sponsored by, or officially connected to Essential, Essential Mod, Essential Loader, Essential Installer, ModCore Inc., Mojang, Microsoft, or Minecraft.

The original Essential Installer project is primarily written in Kotlin and includes a Rust wrapper, which searches for an existing Java install and can download one if none is found. HFDInstaller keeps that general installer structure while changing the branding, metadata, resources, and configuration for Harambe Final Destination.

## Important Notice
All Essential names, marks, branding, and logos belong to their respective owners. This modified version does not use the Essential name or branding as its own project identity.
This project should be treated as a separate fork. Please do not contact Essential support channels for help with HFDInstaller.

## Building

Before building the HFD Installer, you must have both Rust and a Java 8 JDK installed.

### Building the installer

To build the installer, navigate to the `installer` folder and run `./gradlew build`.
Depending on your system and internet connection, the first build may take a few minutes.

Once finished, you should be able to find the Installer jar in `installer/build/libs/installer.jar`.

For convenience, if using a Jetbrains IDE, such as IntelliJ IDEA, run configurations are provided in the project.

### Building the wrapper

#### macOS

For macOS, a convenience script is provided and can be run by running `./scripts/macos-full.sh`

The script will output the location of the final .app.

#### Windows

1. Compile the installer JAR
2. Move the installer.jar to `wrapper/resources/installer.jar`
3. Compile the wrapper with `cargo build --release --target x86_64-pc-windows-msvc` (run from within `wrapper` folder)
4. Find the compiled .exe file in `wrapper/target/x86_64-pc-windows-msvc/release/`.

## Customizing the installer

The installer was written with customization in mind from the start, to allow the community to use it for their own projects.
There are already many configurable things, but many more are currently still being developed and various refactors are currently planned/in the works.
If you are planning to adapt this for your project, we advise you to wait for future updates which will make that much easier.
Currently, much of the customization is not yet documented; such documentation and more proper guides will be added
in the future.

For configurability, see:

- [wrapper/resources/info](wrapper/resources/info)
- [installer/src/main/resources](installer/src/main/resources)
    - Documentation in [MetadataManager](installer/src/main/kotlin/gg/essential/installer/metadata/MetadataManager.kt)

## License

This project is distributed under the included [LICENSE](LICENSE)file.

The original Essential Installer license allows modified versions and forks in accordance with GPL-3, while also containing additional terms. Keep the license file and legal notices intact when modifying or redistributing this project.

If you distribute compiled builds of HFDInstaller, make sure the corresponding source code and license information are also available as required by the license.
