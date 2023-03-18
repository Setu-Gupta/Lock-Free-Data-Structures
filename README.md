# How to build:
Go to the LFDS directory and build the shared object file in desired build mode. `release` and `debug` are the supported build modes.
```console
~$ cd LFDS
~$ make <build_mode>
```

# How to use:
Refer to the examples provided in the `Tests` directory to see how to build your code with the `lfds` library.
* Include the header files from `LFDS/headers` in your code. Remember to add `LFDS/headers` to the include path of your compiler appropriately.
* While building your code, add `LFDS` to the linker path of your compiler so that it can locate the shared object file. Also make sure to add the appropriate flags to link with the `lfds.so` file.
