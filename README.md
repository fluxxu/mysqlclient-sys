mysqlclient-sys
======

Autogenerated Rust bindings for libmysql-client (`#include <mysql.h>`)

Building
--------

For this crate to build, `libmysqlclient` must be installed on your system
(`brew install mysql` on macOS, `apt-get install libmysqlclient-dev` on Ubuntu,
included with the server distribution on Windows). Additionally, either
`pkg-config` or `mysql_config` must be present and able to successfully locate
`libmysqlclient`.

The build script of the crate will attempt to find the lib path of
libmysql-client using the following methods:
- First, if the environment variables MYSQLCLIENT_LIB_DIR and MYSQLCLIENT_INCLUDE_DIR are set, it will use their values
- If the environment variable isn't set, it will attempt to use pkg-config to locate it. All the config options,
  such as `PKG_CONFIG_ALLOW_CROSS`, `PKG_CONFIG_ALL_STATIC` etc., of the crate
  [pkg-config](http://alexcrichton.com/pkg-config-rs/pkg_config/index.html)
  apply.
- If the library cannot be found using `pkg-config`, it will invoke the command
  `mysql_config --variable=pkglibdir`

The bindings will be generated against the headers present on your system at
compile time. We will attempt to determine the include directory by using the
output of the first command in this list to return successfully:

- `pkg-config --variable=includedir mysqlclient`
- `mysql_config --variable=pkgincludedir`

## License

Licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.
