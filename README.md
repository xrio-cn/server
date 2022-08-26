# Introduce

  A high performance game server framework.

# Support Platform

  * MacOSX

  * FreeBSD

  * Linux

  * MSYS / CYGWIN / WSL2

# Usage

  Referring to the `GNU99` standard compilation, currently only the `openssl` library is required to provide encryption, decryption and `TLS` interaction.

## 1. Install

  `CMAKE` can be used to build frameworks.

  The following are alternative ways to build the framework:

  |NAME|OPTIONAL|Description|
  |:-:|:-:|:-:|
  |USE_INCLUDES|1|Include header files after build|
  |USE_TCMALLOC|1|Specifies the memory allocator|
  |USE_MIMALLOC|1|Specifies the memory allocator|

  Then, we can make built-in libraries depend on third-party implementations to provide better performance depending on some circumstances:

  |NAME|OPTIONAL|Description|
  |:-:|:-:|:-:|
  |USE_ZLIB|1|By default, `miniz` is used. If `ZLIB` or `ZLIB-NG` is available, this option can be enabled|
  |USE_PCRE|1|The default `re` library is implemented using `POSXI Regex`, this option can be enabled if `PCRE` is installed|
  |USE_PCRE2|1|The default `re` library is implemented using `POSXI Regex`, this option can be enabled if `PCRE2` is installed|
  |USE_PCRE2_JIT|1|The default `re` library is implemented using `POSXI Regex`, this option can be enabled if `PCRE2` is installed and supports `JIT`|
  |USE_BROTLI|1|Make httpd support `brotli` compression if you installed|
  |USE_ICONV|1|Use `libiconv` to provide character set conversion|

  some specific options:

  |NAME|OPTIONAL|Description|
  |:-:|:-:|:-:|
  |USE_ATOMIC|1|Use `stdatomic` instead of the `__sync_*` function|
  |USE_PAUSE|1|Enable assembly `PAUSE` Optimization|
  |USE_SSE4|1|Enable `SSE4` instruction set support|
  |USE_AVX2|1|Enable `AVX2` instruction set support|

  Installation command line example:

  <details>

  <summary>1. Compile by default</summary>

```bash
[candy@MacBookPro:~/Documents/xrio] $ cmake -B build -DCMAKE_INSTALL_PREFIX=test
======================================
Project Name   : xrio
Author  Name   : CandyMi
Author  Email  : 869646063@qq.com
Author  Github : github.com/CandyMi
======================================
-- The C compiler identification is AppleClang 13.1.6.13160021
-- The CXX compiler identification is AppleClang 13.1.6.13160021
-- Check for working C compiler: /Library/Developer/CommandLineTools/usr/bin/cc
-- Check for working C compiler: /Library/Developer/CommandLineTools/usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found OpenSSL: /usr/local/ssl/lib/libcrypto.a (found suitable version "1.0.2q", minimum required is "1.0.2")
-- Configuring done
-- Generating done
-- Build files have been written to: /Users/candy/Documents/xrio/build
```

  </details>


  <details>

  <summary>2. Enable instruction set support</summary>

```bash
[candy@MacBookPro:~/Documents/xrio] $ cmake -B build -DCMAKE_INSTALL_PREFIX=test -DUSE_SSE4=1 -DUSE_AVX2=1
======================================
Project Name   : xrio
Author  Name   : CandyMi
Author  Email  : 869646063@qq.com
Author  Github : github.com/CandyMi
======================================
-- The C compiler identification is AppleClang 13.1.6.13160021
-- The CXX compiler identification is AppleClang 13.1.6.13160021
-- Check for working C compiler: /Library/Developer/CommandLineTools/usr/bin/cc
-- Check for working C compiler: /Library/Developer/CommandLineTools/usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found OpenSSL: /usr/local/ssl/lib/libcrypto.a (found suitable version "1.0.2q", minimum required is "1.0.2")
-- `xrioadmin` set `SSE` enable.
-- `xrioadmin` set `AVX` enable.
-- Configuring done
-- Generating done
-- Build files have been written to: /Users/candy/Documents/xrio/build
```

  </details>


## 2. Documents

  TODO.
  
# LICENSE 

  To be determined.
