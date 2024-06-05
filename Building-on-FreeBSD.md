This wiki page shows how to build re3 on FreeBSD on a amd64/x86_64 system. Tested on FreeBSD 12.2-RELEASE. Building on different architectures has not been tested and you might have to rely on adjusting the packages and code yourself. In case of issues, fill an issue on github to be reviewed by one of the re3 developers.

* Get the required packages by either building them in the `/usr/ports` directory or installing them via ``pkg``:

   `$ pkg install git premake5 gmake glfw glew openal-soft mpg123 libsndfile libsysinfo`

   Disclaimer: you need to get premake5, there are also other premake versions available, only premake5 is supported. You will also need GNU make and not the built-in BSD make. (Library libsndfile is optional.)

* Run `$ git clone --recursive https://github.com/GTAmodding/re3.git` to clone the project to your PC

* Enter the newly created `re3` directory and run `$ premake5 --with-librw gmake2`, remember to use premake5 you either have built in `/usr/ports` or installed it via `pkg`

* Enter the ``build`` directory and run ``$ gmake help`` to see a help message with supported build configurations. As of now, refer to one of the available configurations:
  - ``debug_bsd-x86-librw_gl3_glfw-oal``
  - ``debug_bsd-amd64-librw_gl3_glfw-oal``
  - ``debug_bsd-arm-librw_gl3_glfw-oal``
  - ``debug_bsd-arm64-librw_gl3_glfw-oal``
  - ``release_bsd-x86-librw_gl3_glfw-oal``
  - ``release_bsd-arm-librw_gl3_glfw-oal``
  - ``release_bsd-arm64-librw_gl3_glfw-oal``

* Compile librw and re3 by running ``$ gmake CC=clang CXX=clang++ config=(your configuration goes here)``

* In case you didn't copy some of the required gamefiles, copy all content from ``re3/gamefiles/`` to the game root directory

* (If you didn't set GTA_III_RE_DIR env. variable) Revisit the `re3` directory, go to `bin` and find the appropriate `re3` binary you just compiled, and copy it to your game folder with GTA3 inside

* Play the game by running ``$ ./re3``

Remember that re3 is an actively developed project which doesn't have a final version, so in case you'd like to get the game updated you have to reproduce the steps above.