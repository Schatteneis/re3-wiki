### Quick Guide

The easiest way to compile and run `re3` is to first [install](https://visualstudio.microsoft.com/downloads/) Visual Studio 2015 or later in your machine. You need to make sure you also download the "Desktop development with C++" additional package as shown in the image below.

<p align="center"><img src="https://i.imgur.com/GFoyUCe.png" width="520" alt=""/><br><sup>Visual Studio Installer: C++ Tools</sup></p>

You'll need `git` installed in your computer to pull the code. You can get it [here](https://git-scm.com/download/win).
Then open Command Prompt and change directory (`cd`) to a path where you would like to store the code like `C:\Windows`. Don't forget to include the **--recursive** parameter. Otherwise additional dependencies won't be downloaded and the code will not compile.

<p align="center"><img src="https://i.imgur.com/b2j0gBT.png" width="520" alt=""/><br><sup></sup></p>

You should also use `setx` to define the directory where GTA is installed in your computer. Usually it's in `C:\Program Files (x86)\Steam\steamapps\common\Grand Theft Auto 3`. This is necessary to copy the `re3` executable into GTA 3 directory after each build.

<p align="center"><img src="https://i.imgur.com/P12h5ka.png" width="520" alt=""/><br><sup></sup></p>

If the clone succeed then a folder called `re3` will be created. You can just `cd re3` or open with the File Explorer. You can click one of `premake-vs<X>.cmd` files to generate the VS solution files. In my case, as VS 2019 is installed, then it would be `premake-vs2019.cmd`.

<p align="center"><img src="https://i.imgur.com/zvzCsRV.png" width="520" alt=""/><br><sup></sup></p>

A `build` folder will be created. Open it and click at `re3.sln` file to open the project.

<p align="center"><img src="https://i.imgur.com/H5hteju.png" width="520" alt=""/><br><sup></sup></p>

You should see a window that looks like this. Let's choose `win-x86-librw_d3d9-oal` configuration to get started. Either press `F7` key into your keyboard or go to `Build > Build Solution` menu entry.

<p align="center"><img src="https://i.imgur.com/9ayMXJO.png" width="520" alt=""/><br><sup></sup></p>

Now you must copy some extra `DLL` files to your GTA installation directory. Copy both of `vendor/mpg123/dist/Win32/libmpg123-0.dll` and `vendor/openal-soft/dist/Win32/OpenAL32.dll` there like shown in the image below. Also note: your game directory should be as vanilla as possible. In other words, don't install any modifications (e.g. CLEO), otherwise the game may crash.

<p align="center"><img src="https://i.imgur.com/hyl8UTd.png" width="520" alt=""/><br><sup></sup></p>

If you compile the "Debug" variant the executable will be only named `re3.exe`. The "Release" one will be `re3-release.exe`. Note that both `libmpg123-0.dll` and `OpenAL32.dll` are copied into the game folder.

### Premake Options

The basic syntax to generate the build files using [premake](https://premake.github.io/) is: `premake5 COMMAND [options...]`. The command can be any of `vs<X>` (e.g. `vs2019`). The options are listed below:

- `with-librw`: compile using the [open source](https://github.com/aap/librw) RW implementation by aap. This will require the dependency to be present at `vendor/librw`
- `with-asan`: build with [address sanitizer](https://en.wikipedia.org/wiki/AddressSanitizer)
- `with-lto`: build with [link time optimization](https://en.wikipedia.org/wiki/Interprocedural_optimization#WPO_and_LTO)
- `glfwdir64`: specify the path to GLFW 64-bit installation directory (where you unpacked the .zip file)
- `glfwdir32`: specify the path to GLFW 32-bit installation directory
- `no-git-hash`: disable generating the repository hash every build
- `no-full-paths`: don't print [full paths](https://docs.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2010/027c4t2s(v=vs.100)) into binary (windows only)

If you want to compile with [GLFW](https://www.glfw.org/), then you must specify `--glfwdir<X>`. If you unpack the zip file into the `vendor` folder, then this won't be necessary.

You can also run `premake5 --help` to view a full list of options.