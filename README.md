XSOB Clang 
=============

```txt
Based on LLVM X86_64 Linux
LLVM on Github: https://github.com/llvm/llvm-project
```
# How To Use?

1. Extract first
------------
```bash
 tar -xvf FILE.tar.gz
```

2. Change Permission to rwx
-------------
```bash
 chmod -R 700 PATH
```

3. Create C/CPP File
-------------
```cpp
  #include <stdio.h>
   int main(){
     // basic code 
    cout << "Hello World" << endl;
   }
```

4. Compile it
----------------
```bash
./CLANGPATH/bin/clang *.cpp -o OUTFILE
```

5. Done
--------


# Usage for compiling kernel

> don't forget to input your defconfig before building
```bash
  make -j$(nproc --all) \
        ARCH=arm64 \
        O=out \
        CC=/path/bin/clang \
        CROSS_COMPILE=arm64-linux-gnu- \
        DEVICE_defconfig
```

Clang only:
-------------

```bash
   make -j$(nproc --all) \
        ARCH=arm64 \
        O=out \
        CC=/path/bin/clang
```

Combo Methode:
--------------

arm64:
------
```bash
sudo apt install gcc-arch64-linux-gnu
```
```bash
  make -j$(nproc --all) \
        ARCH=arm64 \
        O=out \
        CC=/path/bin/clang \
        CROSS_COMPILE=arm64-linux-gnu-
```

arm32:
------
```bash
sudo apt install gcc-arm-linux-gnueabi-
```
```bash
  make -j$(nproc --all) \
        ARCH=arm \
        O=out \
        CC=/path/bin/clang \
        CROSS_COMPILE=arm-linux-gnueabi-
```

