# ![](res/image/logo.png)

[![Build Status](https://travis-ci.org/metalwood/libsg.svg?branch=master)](https://travis-ci.org/metalwood/libsg)

## Overview

Cross-platform C utility library focusing on developer-friendly.

## Idea

* *Reuse, not rework or reinvent.*

* *Using C to build important infrastructure, not everything.*

## Feature

* *One key to build, no dependency*

* *High performance for key modules*

* *Efficient development*

```
    /* sample of normal md5 library api */

    FILE *fp;
    struct md5_context *ctx;
    char buf[256], md5_sum[33];
    size_t size;
    assert(fp = fopen("/home/test_file", "rb"));
    assert(ctx = md5_start());
    while (!feof(fp)) {
        size = fread(buf, 1, 256, fp);
        if (size > 0)
            md5_update(ctx, buf, size);
    }
    md5_final(ctx, md5_sum);
    fclose(fp);
```

```
    /* sample of libsg md5 api */

    struct sg_md_sum md5_sum = {0};
    assert(sg_md_file("/home/test_file", SGMDTYPE_MD5, &md5_sum) == true);
```

* *Easy-to-understand APIs*

## Supported Platforms

Linux ／ Windows ／ macOS

## Download

https://github.com/metalwood/libsg/archive/master.zip

## Build & install

Before building, make sure CMake / XMake and C compiler(gcc/clang/msvc) has been installed correctly.
Make sure the source path does not have space.

Linux / macOS

        $ mkdir build
        $ cd build
        $ cmake ..
        $ make -j4

Windows

        $ md build
        $ cd build
        $ cmake ..
        open .sln with Visual Studio and compile the project

## API doc & demo

coming soon

## Modules

**compress** `zip`

**container** `bip_buf` `bloom_filter` `json` `kfifo` `list` `msgpack` `queue` `vsbuf` `xml`

**crypto** `md` (message digest) `mac` (message authentication code) `sym`: (symmetric encryption)

**db** `sqlite` `ejdb` `bdb`

**hash** `crc` `uuid` `murmur`

**math** `big_float` `big_int` `c_float` `c_int` `num_sys` `random` `speed`

**net** `dns_server` `etp` `etp_server` `http` `http_server` `net_card` `ntp` `ntp_server` `port` `proxy` `quic` `quic_server` `tcp` `tcp_server` `udp` `udp_server` `websocket`

**str** `base64` `charset` `regex` `snprintf` `string` `vsstr` (variable-sized string) `vsstr_list`

**sys** `atom` `clock` `cron` `daemon` `dynlib` `fs` `limit` `memory` `mq` `mutex` `os` `pipe` `proc` `rwlock` `sem` `shell` `shm` `sleep` `spin_lock` `thread` `type`

**util** `assert` `compiler` `dump` `err` `log` `trick`

## Code specification

English: [Linux kernel coding style](https://www.kernel.org/doc/Documentation/CodingStyle)            简体中文: [Linux内核编码风格](http://www.cnblogs.com/baochuan/archive/2013/04/08/3006615.html)

## Contact

email: metalwood@foxmail.com                   QQ群: `556925561`

## Contributors

metalwood `metalwood@foxmail.com`

canmor `476010464@qq.com`

vincent `vin@misday.com`
