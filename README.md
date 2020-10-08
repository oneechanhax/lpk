# lpk
 a "Little" package manager

Concept, written in c++
will follow apk(alpine package keeper) style.

lpk add [package]
lpk del [package]
lpk list ([package]) - list packages and/or info

Sandboxing was thought of but docker has it figured out.
Instead we will go for universal packages with tests. 
lpk will simulate adding the packages, run tests in the background, then push updates to the filesystem.
btrfs *could* make this seemless with snapshotting every step of the way and changing root as packages passes the tests.
It is unknown how to easily do this on other filesystems.
