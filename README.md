# My openssl library for leanring. 

# The xcode index setup. 
- Make project xw_openssl
- Set the xcode project "C Hearder Search Path" and "C Lib Search Path", absolute path to this project's include folder the for the crypto include folder. 

# Installatio on Mac and setup for personal project
```
brew install --force openssl
Warning: openssl: this formula has no --force option so it will be ignored!
==> Downloading https://homebrew.bintray.com/bottles/openssl-1.0.2k.sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring openssl-1.0.2k.sierra.bottle.tar.gz
==> Using the sandbox
==> Caveats
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

This formula is keg-only, which means it was not symlinked into /usr/local.

Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries

If you need to have this software first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.zshrc

For compilers to find this software you may need to set:
    LDFLAGS:  -L/usr/local/opt/openssl/lib
    CPPFLAGS: -I/usr/local/opt/openssl/include
For pkg-config to find this software you may need to set:
    PKG_CONFIG_PATH: /usr/local/opt/openssl/lib/pkgconfig

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.2k: 1,696 files, 12M
```


# Secure programming with the OpenSSL API
- Create basic secure and unsecure connections
- From https://www.ibm.com/developerworks/library/l-openssl/
- In Folder xw_test/intro-openssl/
```
.
└── intro-openssl
    ├── README
    ├── TrustStore.pem
    ├── nossl.c
    └── withssl.c
```

### This is the right command to include the lib. 
```
 ✘ guanghe@GUANGHE-M-H03T  ~/Documents/STUDY/Projects_personal/xw_openssl/xw_test/intro-openssl   master ●✚  gcc -g -O2 -Wall -Wextra -I/usr/local/opt/openssl/include -rdynamic -L/usr/local/opt/openssl/lib -lcrypto nossl.c -o nossl                              
Undefined symbols for architecture x86_64:
  "_SSL_load_error_strings", referenced from:
      _main in nossl-668935.o
ld: symbol(s) not found for architecture x86_64
clang: error: linker command failed with exit code 1 (use -v to see invocation)

gcc -Wall -Wextra -Werror -o nossl -I/usr/local/opt/openssl/include -L/usr/local/opt/openssl/lib -lssl -lcrypto nossl.c
```
