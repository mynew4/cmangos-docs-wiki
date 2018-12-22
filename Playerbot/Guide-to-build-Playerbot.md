*Note: PlayerBot mod currently only supports cmake build.*

#### Build instructions
In order to build the optional PlayerBot mod in CMaNGOS core, simply follow the instructions in Installation-Instructions

You only need to add an option when reaching the cmake configuration steps in Installation-Instructions#compiling-cmangos-and-scriptdev2-nix

When invoking `cmake` you need to add the following option: `-DBUILD_PLAYERBOT=ON` along with all your other options like debug or target directory.

That's it. Follow all the other steps as usual and the core will build with the optional PlayerBot mod embedded.