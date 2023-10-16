# FAQ

## Usage 📋

### STEP1: Compile on Linux

- pip install conan
- conan profile detect --force
- conan install . --output-folder=build --build=missing
- cd build
- cmake -DCMAKE_BUILD_TYPE=Release ..
- make
- root of the project run the binaries

### STEP2: Compile on Windows

- install Visual studio
- install buildtools of visual studio
- install C++ dependencies and cmake in visual studio
- install conan
- conan profile detect --force
- conan install . --output-folder=build --build=missing
- cd build
- cmake -DCMAKE_TOOLCHAIN_FILE=. ..
- cmake --build . --config Release
- root of the project run the binaries
- these are the binaries: r-type_server.exe and r-type_client.exe

### STEP3: CPACK TO UNZIP AND BUILD THE PROJECT

CMake has a corresponding meta package system CPack, which generates configuration files for numerous packaging systems. Distributing code and binary executablees and libraries to users without requiring them to compile a project is done via these packages. CPack creates these binary packages like Windows .msi, Linux .deb/.rpm, MacOS .dmg, etc. CPack also creates traditional source archives as are also generated by GitHub Releases, but with fine-grained control of the contents.

Assuming the PROJECT_BINARY_DIR is “build”, CPack generates build/CPackConfig.cmake for binary packages and build/CPackSourceConfig.cmake for source packages. CPackConfig.cmake is generated according to install() commands in the CMakeLists.txt files of the project.

Note that in general “install()” DESTINATION should always use relative paths. CPack ignores install() items with absolute DESTINATION.

CPackSourceConfig.cmake works the opposite way–it includes everything not excluded by CPACK_SOURCE_IGNORE_FILES, so we make a file cmake/.cpack_ignore with regex excluding non-source files. As a last step at the end of the main CMakeLists.txt after all install(), we include cmake/cpack.cmake.

Run this script (builder.sh) at the root of the project:

`./builder.sh`

It will create a package folder at the root of the project. This folder contain a R-Type-0.1.1-Source.tar.bz2 file. To unzip it run this command:

`tar -xvf R-Type-0.1.1-Source.tar.bz2`

This command will create a R-Type-0.1.1-Source folder which contain all the ressources of our project. Enjoy the game 🎮
### To launch the server:

`./r_type_server  <address> <port> <lobby_status>`

Now, the clients could connect to the server

### To launch the client:

`./r_type_client  <address> <port> <sound> <lobby_status>`