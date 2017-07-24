## libssl.so errors with gitbook editor in Fedora 26

When tried to use **gitbook editor**, it throws and error that `libssl.so.1.0.0` isn't found. Even installing `compat-openssl` package doesn't solve the problem. Then tried symlinking the libraries in `/lib64` which are installed by `compat-openssl10` package. Then again it didn't solve the problem. Found the solution in a reddit post though

### Solution:

The solution is quite simple. Just downloading the deb file from Ubuntu Xenial \(16.04\) archive and putting the `libssl.so.1.0.0` and `libcrypto.so.1.0.0` file in `/lib64/` fixed the issue. 

Download the archive from the link [https://packages.ubuntu.com/xenial/amd64/libssl1.0.0/download](https://packages.ubuntu.com/xenial/amd64/libssl1.0.0/download)

Then extract the deb file. If `dpkg-deb` is available, then just do `dpkg-deb -R deb-file-name /directory-to-extract` like command. Anyway, once you get the libs, copy them to ``/lib64``` like this

`sudo cp temp/lib/x86_64-linux-gnu/lib* /lib64/ -v`







