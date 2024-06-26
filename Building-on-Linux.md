This wiki page shows how to build re3 on various Linux distros. Tested on x86, x86_64, arm64 architectures, and GCC 7.5.0, 8.3.0, clang 10.0 compilers. In case of issues, fill an issue on github to be reviewed by one of the re3 developers.

You need libraries and headers of;
- openal / libopenal-dev
- GLEW / libglew-dev (i386 unavailable on apt after Ubuntu 19.10)
- glfw / libglfw3-dev (min. 3.3 is required, i386 unavailable on apt after Ubuntu 19.10)
- libsndfile1-dev (*Caution:* install this before libmpg123-dev, optional)
- libmpg123-dev

and compilers set up, i.e. for Ubuntu you should install `build-essential`.

## Steps

* Run `$ git clone --recursive https://github.com/GTAmodding/re3.git` to clone the project to your PC

* Enter the newly created `re3` directory;
   * If you're on x86/x86_64, run `$ ./premake5Linux --with-librw gmake2`.
   * If you're on i.e. arm/arm64, you need to build your own premake5 from source. Then you can proceed to running premake5 with `--with-librw gmake2` arguments.

* Enter the ``build`` directory and run ``$ make help`` to see a help message with supported build configurations and architectures. As of now, refer to one of the available configurations:
  - ``debug_linux-x86-librw_gl3_glfw-oal``
  - ``debug_linux-amd64-librw_gl3_glfw-oal``
  - ``debug_linux-arm-librw_gl3_glfw-oal``
  - ``debug_linux-arm64-librw_gl3_glfw-oal``
  - ``release_linux-x86-librw_gl3_glfw-oal``
  - ``release_linux-amd64-librw_gl3_glfw-oal``
  - ``release_linux-arm-librw_gl3_glfw-oal``
  - ``release_linux-arm64-librw_gl3_glfw-oal``


* Compile librw and re3 by running ``$ make config=(your configuration goes here)``. If you want you can change compiler with setting `CC` and `CXX`.

* In case you didn't copy some of the required gamefiles, copy all content from ``re3/gamefiles/`` to the game root directory

* (If you didn't set GTA_III_RE_DIR env. variable) Revisit the `re3` directory, go to `bin` and find the appropriate `re3` binary you just compiled, and copy it to your game folder with GTA3 inside

* Play the game by running ``$ ./re3``

You can expect poor performance if you're not using Nvidia/AMD drivers. (At least it was in my case with my iGPU)

Remember that re3 is an actively developed project which doesn't have a final version, so in case you'd like to get the game updated you have to reproduce the steps above.

Struct sizes are different then on Windows, so don't enable validating struct sizes. Needlesly to say, your previous savegames will be incompatible.