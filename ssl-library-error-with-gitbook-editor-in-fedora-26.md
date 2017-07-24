## libssl.so errors with gitbook editor in Fedora 26

When tried to use **gitbook editor**, it throws and error that `libssl.so.1.0.0` isn't found. Even installing `compat-openssl` package doesn't solve the problem. Then tried symlinking the libraries in `/lib64` which are installed by `compat-openssl10` package. Then again it didn't solve the problem. Found the solution in a reddit post though

### Solution:

The solution is quite simple. Just downloading the deb file from Ubuntu Xenial \(16.04\) archive and using the two file`libssl.so.1.0.0` and `libcrypto.so.1.0.0` should fix the issue.

Download the archive from the link [https://packages.ubuntu.com/xenial/amd64/libssl1.0.0/download](https://packages.ubuntu.com/xenial/amd64/libssl1.0.0/download)

Then extract the deb file. If `dpkg-deb` is available, then just do `dpkg-deb -R deb-file-name /directory-to-extract` like command. 

Now copy the two files into a directory and edit the `gitbook-editor.desktop` file's `Exec=` line to add those two files into `LD_LIBRARY_PATH` environment variable. Don't copy them directory to `/lib64` because there might be some other files with same name which can create a huge problem.

The exec line in `gitbook-editor.desktop` file should look like this

```bash
Exec=env LD_LIBRARY_PATH=/opt/gitbook-editor/openssl-1.0.0 /opt/gitbook-editor/editor
```

Assuming the files are in `/opt/gitbook-editor/openssl-1.0.0` directory.

