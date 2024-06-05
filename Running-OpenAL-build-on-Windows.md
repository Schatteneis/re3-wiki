You have to copy 3 DLLs from their corresponding folders to GTA3 root folder.

DLLs you should use vary depending on architecture(32/64 bit) of your build, so here is a guide to find them;

- libmpg123-0.dll - `re3/vendor/mpg123/dist/Win(32|64)`
- libsndfile-1.dll - `re3/vendor/libsndfile/dist/Win(32|64)`
- OpenAL32.dll _(yes, it has 32 no matter what)_ - `re3/openal-soft/dist/Win(32/64)`

Missing libmpg123-0.dll or libsndfile-1.dll will throw "DLL missing" error at the start, so you'll know it.

Missing OpenAL32.dll will give assert(if asserts are enabled, otherwise it will crash the game) on start.