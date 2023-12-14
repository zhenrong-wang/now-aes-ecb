# NOW-AES: an AES implementation in the project HPC-NOW

# 1. Background

The project [HPC-NOW](https://github.com/zhenrong-wang/hpc-now) needs to handle sensitive information. Therefore, we implemented an AES module based on the [NIST standard FIPS-197](https://csrc.nist.gov/pubs/fips/197/final)

# 2. Brief Intro

**Program Name**: NOW-AES: an AES implementation in the project HPC-NOW

**Purpose**: block-level encryption/decryption.

**License**: MIT

**Technical Reference**: [NIST standard FIPS-197](https://csrc.nist.gov/pubs/fips/197/final)

# 3. How-To: Build, Run, and Use

## 3.1 Build

### 3.1.1 Prerequisites

You need a C compiler to build. 

- For Microsoft Windows users, [mingw](https://sourceforge.net/projects/mingw/) is a good choice
- For GNU/Linux Distro or other *nix users, the [GNU Compiler Collections](https://gcc.gnu.org/), known as gcc, is a perfect one
- For macOS users, [clang](https://clang.llvm.org/) is easy to install and use (brew is not needed to install clang on macOS).

### 3.1.2 Build Guide

1. Use `git` to clone this code: `git clone https://github.com/zhenrong-wang/now-aes-ecb.git`
2. Build command example: `gcc now-crypto-aes.c -o my-if97.exe -lm`

Note: the `-lm` may not be valid for Windows or macOS. It is necessary for GNU/Linux distros.

## 3.2 Run

### Run the Test Data

Suppose you have followed the steps above and built the my-if97.exe in the source code folder.

- `cd test`
- `../my-if97.exe` (**UNIX-like OS**) or `..\my-if97.exe` (**Microsoft Windows**)

If you see the output below, congrats, you've built the binary successfully.

    ...

    1       25000000.00000000       873.00000000
    1       23960000.00000000       811.00000000
    1       6000000.00000000        811.00000000
    1       6000000.00000000        573.00000000

    # Calculation finished. Please check _properties.dat for results.
    # Press any key to exit.

    @ Any problems found, please contact the author.
    @ Zhenrong Wang, zhenrongwang@live.com.

### An Example for UNIX-like OS:

Suppose the working directory is `/home/amber/water-steam/`

Suppose the absolute path of the executable is `/home/amber/bin/my-if97.exe`

- `$ cd /home/amber/water-steam/`
- `$ vim _input.dat` # Create an input file named '**_input.dat**' with some input data (See Section 3.3 below)
- `$ /home/amber/bin/my-if97.exe`

### An Example for Windows:

Suppose the working directory is `C:\Users\amber\water-steam\`

Suppose the absolute path of the executable is `C:\Users\amber\bin\my-if97.exe`

- Open a Command Prompt Window
- `cd C:\Users\amber\water-steam\`
- `notepad _input.dat`
- `C:\Users\amber\bin\my-if97.exe`

## 3.3 Use

For the **_input.dat** file, you need to input the data in lines. A single line refers to a point. Strict format:

`POINT_TYPE(int),PARAM1(float/double),PARAM2 (float/double)` 

**Please separate the params by a comma ','**

POINT_TYPE: 

- 1 Pressure and Temperature
- 2 Pressure and Density
- 3 Pressure and Specific Internal Energy
- 4 Pressure and Specific Enthalpy
- 5 Pressure and Specific Entropy
- 6 Temperature and Density
- 7 Temperature and Specific Internal Energy
- 8 Temperature and Specific Enthalpy
- 9 Temperature and Specific Entropy
- 10 Specific Enthalpy and Specific Entropy
- 11 Pressure and Steam Dryness
- 12 Temperature and Steam Dryness

Example: `1,100000,300`

Example: `1,1e5,3e2`

Units:

- Pressure(p): Pa
- Temperature(t): K
- Density(r): kg/m3
- Specific Internal Energy(u): J/kg
- Specific Enthalpy(h): J/kg
- Specific Entropy(s): J/(kg.K)

## 3.4 Output

The program writes out a file named '**_properties.dat**' in the working directory. 

# 4 Bugs and Communications

Please submit issues to this repo. I'd be glad to communicate on any issues.

Or, you can also email me: zhenrongwang@live.com
