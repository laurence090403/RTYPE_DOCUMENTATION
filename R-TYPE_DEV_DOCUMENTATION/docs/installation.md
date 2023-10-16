# Installation

## Prerequisites
- install Visual studio
- install buildtools of visual studio
- install C++ dependencies and cmake in visual studio
- install conan

## Installation instructions
- install Visual studio
To install Visual Studio, you can follow these steps:

    1- Visit the official Visual Studio website:  [vscode](https://visualstudio.microsoft.com/.)

    2- On the website, you'll see different versions of Visual Studio available. Choose the edition that suits your needs (e.g., Visual Studio Community, Visual Studio Professional, or Visual Studio Enterprise) and click on the "Download" button for that edition.

    3- Once you click on the "Download" button, the Visual Studio installer will start downloading.

    4- Once the installer is downloaded, run it by double-clicking on the downloaded file.

    5- The installer will launch, and you'll be presented with different installation options and workloads. Workloads are sets of tools and features tailored for specific types of development, such as .NET desktop development, web development, or game development. Select the workloads you need for your development projects. You can also choose individual components if you prefer a more customized installation.

    6- After selecting the workloads and components, click on the "Install" button to start the installation process. You may need to accept the license terms and choose the installation location during this process.

    7- The installer will begin downloading and installing the selected components. This process may take some time, depending on your internet connection speed and the selected components.

    8- Once the installation is complete, you can launch Visual Studio from the Start menu or desktop shortcut.

    9- When you first launch Visual Studio, you may be prompted to sign in with your Microsoft account or create a new account. Signing in allows you to personalize your Visual Studio experience and access additional features.

    10- After signing in, you should be ready to start using Visual Studio for your development projects.

Remember to check the system requirements for the specific version of Visual Studio you are installing to ensure compatibility with your operating system.

- install buildtools of visual studio

If you already have Visual Studio Code installed and you just want to install the Build Tools for Visual Studio, you can follow these steps:

    1- Go to the Visual Studio downloads page: https://visualstudio.microsoft.com/downloads/.

    2- Scroll down to the "All downloads" section. Look for the "Tools for Visual Studio" category and click on it.

    3- In the "Tools for Visual Studio" section, you will find different options. Look for the "Build Tools for Visual Studio" option and click the "Download" button.

    4- The Visual Studio Build Tools installer will start downloading.

    5- Once the installer is downloaded, run it by double-clicking on the downloaded file.

    6- The installer will launch and present you with various installation options. Make sure the "Workloads" tab is selected.

    7- In the list of workloads, you will find different options for specific types of development. Select the workloads you need for your projects. For example, you might choose ".NET desktop build tools" or "Web development build tools." You can also choose individual components if you prefer a more customized installation.

    8-After selecting the workloads and components, click the "Install" button to start the installation process. You may need to accept the license terms during this process.

    9- The installer will begin downloading and installing the selected components. This process may take some time, depending on your internet connection speed and the selected components.

    10- Once the installation is complete, you can use the Build Tools for Visual Studio from the command line or integrate them into your preferred development environment.

It's important to note that the Build Tools for Visual Studio provide command-line tools and compilers without the Visual Studio IDE. They are designed for scenarios where you only need the build-related tools and not the full development environment.


- install C++ dependencies and cmake in visual studio

To install C++ dependencies and CMake in Visual Studio, you can follow these steps:

    1- Open Visual Studio and go to the "Extensions" menu.

    2- Select "Manage Extensions" from the dropdown menu. This will open the Extensions and Updates window.

    3- In the search bar of the Extensions and Updates window, type "C++" and press Enter.

    4- Look for the "C++ Desktop Development" extension and click on the "Download" button next to it.

    5- Wait for the extension to be downloaded and installed. You may need to restart Visual Studio after the installation is complete.

    6- Once Visual Studio restarts, go to the "File" menu and select "New" and then "Project". This will open the New Project window.

    7- In the New Project window, expand the "Installed" templates on the left-hand side and select "Visual C++".

    8- Choose a project template that suits your needs, such as "Console Application" or "Windows Desktop Application". Select the template and click "Next".

    9- Configure the project settings as desired, and click on the "Create" button to create the project.

    10- Once the project is created, you can start adding C++ code files to it.

    11- To use CMake in Visual Studio, you can either create a new project with CMake support or add CMake support to an existing project.

        To create a new project with CMake support:
            Go to the "File" menu and select "New" and then "Project".
            In the New Project window, expand the "Installed" templates on the left-hand side and select "C++".
            Select the "CMake Project" template and click "Next".
            Configure the project settings and click on the "Create" button to create the project.

        To add CMake support to an existing project:
            Right-click on the project in the Solution Explorer and select "Add" and then "New Item".
            In the Add New Item window, search for "CMake" in the search bar.
            Select the "CMake Settings" item and click "Add".

    12- Once you have a project with CMake support, you can configure your CMakeLists.txt file to specify the dependencies and build settings for your project.

        Open the CMakeLists.txt file in your project.
        Use the CMake commands and syntax to configure your project's dependencies, include directories, libraries, and build options.

    13- Build your project by selecting "Build" from the Visual Studio menu or pressing Ctrl+Shift+B.

That's it! You have now installed C++ dependencies and CMake in Visual Studio, and you can start developing C++ projects using these tools.

Please note that the specific steps may vary slightly depending on the version of Visual Studio you are using.

- install conan

To install Conan, a package manager for C++ dependencies, you can follow these steps:

    1- Open a command prompt or terminal window.

    2- Make sure you have Python installed on your system. You can check if Python is installed by running the following command:

        python --version

        If Python is not installed, visit the Python website (https://www.python.org/) and download the latest version of Python for your operating system. Follow the installation instructions provided.

    3- Once Python is installed, you can install Conan using pip, the package installer for Python. Run the following command:

        pip install conan

        This command will download and install Conan and its dependencies.

    4- After the installation is complete, you can verify that Conan is installed correctly by running the following command:

        conan --version
    
        This command will display the version of Conan installed on your system.

    5- Conan is now installed and ready to use. You can start using Conan to manage C++ dependencies for your projects.

    To learn more about how to use Conan, you can refer to the Conan documentation (https://docs.conan.io/).

That's it! You have successfully installed Conan on your system. You can now use Conan to manage your C++ dependencies for your projects.

## Examples of use

clone the project

`git clone git@github.com:EpitechPromo2025/B-CPP-500-COT-5-1-rtype-yannick.keke.git`

launch cmake

`cmake -S . -B ./build/`

then make

`cd build/`
`make`

and the project is finally ready to launch

### Usage 📋
Make sure you have cmake installed
STEP1: Compile on Linux

- pip install conan
- conan profile detect --force
- conan install . --output-folder=build --build=missing
- cd build
- cmake -DCMAKE_BUILD_TYPE=Release ..
- make
- root of the project run the binaries

STEP2: Compile on Windows

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

To launch the server:

`./r_type_server  <address> <port> <lobby_status>`

Now, the clients could connect to the server

To launch the client:

`./r_type_client  <address> <port> <sound> <lobby_status>`

Enjoy the gameplay, and tell your friends to join you ! 🎉
