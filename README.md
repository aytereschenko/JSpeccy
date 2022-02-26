# JSpeccy

## A multiplatform ZX Spectrum emulator written in Java language.

* Emulates ZX Spectrum models 16k, 48k, 128k, +2 and +2a
* Uses the same Z80 core as [Z80Core](http://github.com/jsanchezv/Z80Core) project.
* Contended memory emulation.
* Border effects (Aquaplane, The Sentinel)
* Selectable border size (no border, standard, complete, huge)
* High resolution color effects (Uridium, Black Lamp)
* Emulation for screen scanlines, PAL effect or RGB monitor
* Floating bus emulation (Arkanoid, Sidewize, Cobra)
* Beeper & MIC emulation (Cobra's Arc)
* Read/Write SNA/Z80/SP/SZX snapshot formats
* LOAD/SAVE Tape files in TAP/TZX/CSW formats
* Emulates Kempston, Sinclair 1/2, Cursor AGF, Fuller joysticks using keyboard cursor keys.
* AY-3-8910 PSG emulation, including Fuller Audio Box, with Mono & Stereo ABC/ACB/BAC modes.
* Interfaz I with up to 8 Microdrives, using real emulation when using MDV files.
* Interfaz II ROM emulation.
* Multiface One/128/Plus 3 emulation
* ULA+ mode support (up to 64 colors on screen)
* LEC Memory expansion, up to 528 KB, to use LEC CP/M v2.2, using Microdrives as storage
* Window can be maximized up to x4.
* Selectable emulation speed up to x10 (35 Mhz CPU)
* Translations to English, Spanish & Italian
* Complete command line support, to integrate JSpeccy with front-ends.
* Support for Recreated ZX Spectrum keyboard.

## Building the emulator

To build JSpeccy you need to have [Apache Maven](https://maven.apache.org) installed and run the following command from the console to generate a file called `JSpeccy.jar` under the `target` directory:

    mvn clean package

The compiled target Java executable generated by the build process includes all the required dependencies.

> NOTE: the file path to the project must not contain any spaces for the build to succeed.

To scan the source code for potential programming issues run the following commands from the console:

    mvn spotbugs:check
    mvn spotbugs:gui

Please note, that for convenience, this project also includes a Maven wrapper script, `mvnw`, which can be used to install and run a sandboxed version of Maven thus eliminating the requirement to have a shared version of Maven installed on your system.  The wrapper script can be invoked with the same parameters as Maven itself. e.g. `./mvnw clean package`

## Running the emulator

To run JSpeccy you need to have Java 11 onwards installed. Run with:

    ./target/JSpeccy.jar

A configuration file named JSpeccy.xml will be created on the user directory.

On Unix/Linux platforms using X11, Java 8 have a bug redrawing the screen. Java 8 uses the XRender extension by default and this causes some problems. To resolve it, you can test two possible solutions:

First, you can add the option that uses the OpenGL backend:

    java -Dsun.java2d.opengl=True -jar ./target/JSpeccy.jar

The OpenGL backend solution can be problematic when a good OpenGL driver is not available or X11 is using Mesa. In these cases you can use:

    java -Dsun.java2d.xrender=false -jar ./target/JSpeccy.jar

Please note that the XRender redraw bug is still present in Java 17, so you need still need to the solution described above.

Web: [JSpeccy](http://jspeccy.speccy.org) (only in Spanish, I'm sorry)

## Project documentation summary

The build process includes support for generating a detailed product documentation summary which includes [SpotBugs](https://spotbugs.github.io/) reports and [OWASP](https://owasp.org/) dependency vulnerability reports amongst other useful pieces of information.
To generate the reports run the following command:

    mvn clean install site

And then open the resulting [*target/site/index.html*](target/site/index.html]) file in a web browser.
