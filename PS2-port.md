A PS2 port may be a bit pointless but also really cool.
Here is what would have to be done for the whole thing:

- reverse and use custom IOP modules. cdstream.irx, musicstr.irx, sampman.irx
- use sony IOP modules (padman &c.)
- probably use original 3.1 or 3.5 RW for PS2 (librw would need a lot of work)
- modify RW like R* did (RpGeometry allocation, skyFread, what else?)
- CDma, anim update in SPR
- CTimer
- CFileMgr and bits of CStreaming
- VU0 code for some math functions
- probably a bunch of debugging stuff for sanity?
- we currently assume `not _WIN32 == POSIX`, implement POSIX macros to differentiate it

Check https://github.com/GTAmodding/rwtest for some stuff
- uses RW 3.1
- cdstream implemented and working
- skyfs uses cdstream
- CFileMgr done (uses skyfs)
- simple pad handling. proper CPad should be trivial
