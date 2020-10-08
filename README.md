# lpk
 a "Little" package manager

Concept, written in c++20   
will follow apk(alpine package keeper) style of usage and internal design.   
coroutines can be utilixed to follow that design. flow from web directly into decompressor, from decompressor into signature checker and filesystem, once fully unpacked without signature errors, move unpacked files to desired locations. this should be instant as its a move not a copy or a write, its already on disk.

### lpk add [package]   
### lpk del [package]    
### lpk list ([package]) 
list all available packages and/or info   

Sandboxing was thought of but docker came first and did it in a good way.
This may be a better alternative to flatpak as instead of installing many many dependancies for one application, it can be integrated with the os instead.   
If needed, lpk could make a chroot env and do some light sandboxing but full on sandboxing should be flatpack instead of lpk.    
lpks job is to make commands on the main ttys work, not `flatpak run net.com.package` but instead just `package` as a command.   
lpk should make packages use as many dependancies as already available.
   
## Universal packages
any package from any repository is possible.
run tests 
btrfs *could* make this seemless with snapshotting every step of the way and changing root as packages passes the tests.   
It is unknown how to easily do this on other filesystems.   

### lpk repo add [repo] 
runs sanity tests to ensure working system. checks for linking errors, try a compile, etc.

### lpk repo del [repo]
### lpk repo list [repo]
