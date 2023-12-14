# NOW-AES: an AES implementation in the project [HPC-NOW](https://github.com/zhenrong-wang/hpc-now)

# 1. Background

The project [HPC-NOW](https://github.com/zhenrong-wang/hpc-now) needs to handle sensitive information. Therefore, we implemented an AES module based on the [NIST standard FIPS-197](https://csrc.nist.gov/pubs/fips/197/final)

**DESCLAIMER**

**Encryption/Decryption is extremely important and critical for information security. This project is released under the MIT terms, which means there is no WARRANTY. It is always recommended to use widely-validated implementations such as openSSL.**

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
2. Build command example: `gcc now-crypto-aes.c -o now-aes.exe`

## 3.2 Run

**COMMAND FORMAT** `./now-aes.exe OPTION INPUT_FILE OUTPUT_FILE MD5_LIKE_STRING`

- **OPTION**: Can only be **decrypt** or **encrypt**
- **INPUT_FILE**: The path of the input file. E.g. `~/input.zip`
- **OUTPUT_FILE**: The path of the output file. E.g. `~/output.zip.enc` or `~/output.zip` 
- **MD5_LIKE_STRING**: This program read an MD5 string and assemble a 128-bit (16 byte) encryption key.

### An Example for UNIX-like OS:

- `./now-aes.exe encrypt ~/input.dat ~/encrypted.bin 56196c87917f0bca0c209346abb4c05f`
- `./now-aes.exe decrypt ~/encrypted.bin ~/output.dat 56196c87917f0bca0c209346abb4c05f`

### An Example for Windows:

- `.\now-aes.exe encrypt c:\users\public\input.dat c:\users\public\encrypted.bin 56196c87917f0bca0c209346abb4c05f`
- `.\now-aes.exe decrypt c:\users\public\encrypted.bin c:\users\public\output.dat 56196c87917f0bca0c209346abb4c05f`

**You can validate the encryption/decryption by compare the hashes(MD5 or SHA) of the original file and the encrypted+decrypted file.**

# 4 Bugs and Communications

Please submit issues to this repo. I'd be glad to communicate on any issues.

Or, you can also email me: zhenrongwang@live.com
