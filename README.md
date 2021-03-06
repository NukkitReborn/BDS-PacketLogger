# BDS-PacketLogger

This is a PoC project to log all the packets running throught BDS by using trampoline hook.

## Instructions

* Build the DLL using cmake
* Start BDS
* Use your favourite injector to inject the DLL
* Ready to go
* Packet logs are also written to the files under `packet_logs` directory.

## Features
* No hard-coded value used for packets, all dumped from memory at runtime
* Reliable and easy to use, no need to create a proxy
* Don't worry about encryption. Our best friend BDS will handle it for you. LOL.

## Screenshots
![](https://github.com/NukkitReborn/BDS-PacketLogger/raw/master/screenshots/screenshot1.png)
![](https://github.com/NukkitReborn/BDS-PacketLogger/raw/master/screenshots/screenshot2.png)

## How to update
There are two offsets used in this project, which can be located in `offset.h`.

* `fn_Packet_ReadExtended` is the relative address of function `Packet::readExtended` in module `bedrock_server.exe`. Currently, the value is `0x348C70`.

* `fn_NetworkHandler_SendInternal` is the relative address of function `NetworkHandler::_sendInternal` in module `bedrock_server.exe`. Currently, the value is `0x62B250`.

The values can be easily updated from the Program Database File `bedrock_server.pdb` which comes along with the executable.

## Credits

The following project is used for hooking. Many thanks to the contributers.
* [MinHook](https://github.com/TsudaKageyu/minhook)
