This wiki page shows how to build re3 on AMD64 and ARM64 Macs. In case of issues, fill an issue on github to be reviewed by one of the re3 developers.

You need libraries and headers of;
- openal
- glfw (min. 3.3 is required)
- mpg123  

to be installed via Homebrew or MacPorts.

## Steps

* Copy all the game contents to another directory. GTA Mac versions are packaged inside some kind of Wine wrapper, make sure you only copy the game directory's itself which should be something like "~/Library/Application Support/Steam/steamapps/common/grand theft auto iii/Grand Theft Auto III.app/Contents/Resources/transgaming/c_drive/Program Files/Rockstar Games/Grand Theft Auto III".

* Switch to another directory which you will use for building premake5, and build your own premake5 from source (Not explained in this tutorial).

* Switch to a directory you want to use for building re3, and run `$ git clone --recursive https://github.com/GTAmodding/re3.git` to clone the project to your PC.

* Enter the newly created `re3` directory.  

* Move premake5 binary to here, and run it with `--with-librw gmake2` arguments.

* Enter the ``build`` directory and run ``$ make help`` to see a help message with supported build configurations and architectures. As of now, refer to one of the available configurations:
  - ``debug_macosx-arm64-librw_gl3_glfw-oal`` (for Apple ARM CPU)
  - ``release_macosx-arm64-librw_gl3_glfw-oal``
  - ``debug_macosx-amd64-librw_gl3_glfw-oal`` (for Intel CPU)
  - ``release_macosx-amd64-librw_gl3_glfw-oal``

* Compile librw and re3 by running ``$ make config=(your configuration goes here)``. If you want you can change compiler with setting `CC` and `CXX`.

* In case you didn't copy some of the required gamefiles, copy all content from ``re3/gamefiles/`` to the game directory you just copied from Steam files.  
**Beware:** You should select "Replace" if MacOS asks you what it should do with existing files.

* (If you didn't set GTA_III_RE_DIR env. variable) Revisit the `re3` directory, go to `bin` and find the appropriate `re3` binary you just compiled, and copy it to your game folder with GTA3 inside.

* If the resulting binary has ".app" extension, remove it.

* Give `re3` binary "executable" permission, and use xattr to remove "quarantine" extended attribute, game won't run without:
> sudo chmod a+x re3  
 sudo xattr -r -d com.apple.quarantine re3

* Play the game by running ``$ ./re3``

You can expect poor performance on intermediate resolutions, since there is some unknown scaling going on under the hood.

Remember that re3 is an actively developed project which doesn't have a final version, so in case you'd like to get the game updated you have to reproduce the steps above.