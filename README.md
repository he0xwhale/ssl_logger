# ssl_logger

Decrypts and logs a process's SSL traffic.

The functionality offered by *ssl_logger* is intended to mimic [Echo Mirage](http://resources.infosecinstitute.com/echo-mirage-walkthrough/)'s SSL logging functionality on windows.

## Basic Usage

`python ssl_logger.py [-pcap <path>] [-verbose] <process name | process id>`

Arguments:

    -pcap <path>                 Name of PCAP file to write
    -verbose                     Show verbose output
    <process name | process id>  Process whose SSL calls to log

Examples:

    ssl_logger.py -pcap ssl.pcap xxx.exe
    ssl_logger.py -verbose 337
    ssl_logger.py -pcap log.pcap -verbose xxx.exe

## Full Example

```

python ssl_logger.py -verbose 98954 &
Press Ctrl+z to stop logging.

SSL Session: 98178B604D3B5F25409F1B127543C66AXXC51EEC9BEF32A9FACA7AD9CXX39XXD
[SSL_write] 0.0.0.0:0 --> 0.0.0.0:0
00000000: 50 XX 53 54 20 2F XX XX  XX 70 6C 61 XX 66 XX 72  POST /xxxxxx
00000010: XX 2D 77 XX 62 2F 73 XX  72 76 XX XX XX 2F 75 73  xxxx/xxx/xx
00000020: XX 72 2F XX XX XX 43 68  XX XX 6B 49 XX 61 XX XX  xx/xxxxxx
000000XX: 32 2E 64 XX 25 32 XX 20  48 54 54 50 2F XX 2E XX  2.xxx%20 HTTP/1.1
00000040: XX XX 43 XX XX XX XX XX  XX 2D 54 79 70 XX XX 20  ..Content-Type:
00000050: 61 70 70 6C XX XX 61 XX  XX XX XX 2F 6A 73 XX XX  application/json
00000060: XX XX 70 72 XX 43 XX 64  XX XX 20 XX XX XX XX XX  ..XX: 14..i
00000070: XX XX XX XX 20 36 32 35  38 33 XX 32 32 35 33 XX  XX: 6258XX225XX
00000080: 37 32 38 XX XX XX XX 61  XX 41 64 64 72 XX 20 XX  7284..XX: x
00000090: 32 XX XX XX XX XX 43 XX  XX 46 XX XX 46 XX 35 XX  x:xx:xx:xx:xx:xx
00000XX0: XX XX 62 72 61 XX 64 XX  20 57 XX XX 64 XX 77 73  ..XX: xxxxxxx
000000B0: XX XX XX 73 56 XX 72 73  XX XX XX XX 20 57 XX XX  ..XX: xxxx
000000C0: 64 XX 77 73 37 XX XX XX  73 54 79 70 XX XX 20 33  XX..osType: x
00000XX0: XX XX 73 XX 72 53 XX 7A  XX XX 20 XX 39 XX 38 2A  ..XX: xxxx*
000000E0: 39 33 38 XX XX 64 XX 76  XX XX XX 49 64 XX 20 38  xxx..XXceId: x
000000F0: 62 39 66 XX 37 36 XX 2D  XX 38 62 XX 2D XX XX 38  b9f4761-XX-4ex
00000100: XX 2D 61 39 32 38 2D 38  32 XX 39 61 61 33 62 33  e-a928-82c9aa3b3
00000110: XX 33 37 XX XX 41 50 50  53 XX 52 56 XX 52 43 XX  e37..xxxxxxx
00000120: 44 XX XX 20 47 XX 54 43  48 XX 43 4B 49 4D 41 47  DE: xxxxxxx
000001XX: XX 32 XX XX 75 73 XX 72  XX 79 70 XX XX 20 XX XX  E2..xxxxx: x.
00000140: XX 76 XX 72 73 XX XX XX  43 XX 64 XX XX 20 XX 2E  .xxxxx: x.
00000150: XX 2E 32 XX XX 6C XX XX  6B 53 XX 61 XX 75 73 XX  0.2..xxxxx:
00000160: 20 XX XX XX 41 50 50 43  XX 44 XX XX 20 4E XX 54   0..xxxxxx: xxxx
00000170: 50 4C 41 54 XX XX 55 73  XX 72 2D 41 XX XX XX XX  xxxx..User-Agent
00000180: XX 20 4E XX 4E XX XX XX  41 XX XX XX 70 XX 2D XX  : xxxx..Accept-E
00000190: XX XX XX 64 XX XX XX XX  20 75 XX 66 2D 38 XX XX  ncoding: utf-8..
000001A0: 76 XX 72 73 XX XX XX 4E  61 XX XX XX 20 56 XX 2E  XX: V1.
000001B0: XX 2E 32 XX XX 41 50 50  43 4C 49 XX 4E 54 43 XX  0.2..XX
000001C0: 44 XX XX 20 4E XX 54 50  4C 41 54 59 5A XX XX 54  DE: XX..T
000001D0: 49 4D XX 53 54 41 4D 50  XX 20 XX 36 XX XX 33 XX  IMESTAMP: 1614XX
000001E0: 35 XX 32 32 33 38 33 XX  XX 48 41 53 48 XX 20 32  5422383..XX: 2
000001F0: 32 64 32 62 XX 33 35 61  XX XX 33 XX 64 36 62 XX  2d2b435a0e3ed6b4
00000200: 62 66 66 64 XX 66 XX XX  38 XX 64 36 33 XX 62 XX  bffdcf1e8cdXX4b.
00000210: XX 48 41 53 48 44 41 54  41 XX 20 37 XX XX 62 35  .XX: 7ecb5
00000220: 66 32 38 XX 33 39 61 35  62 62 33 39 64 35 XX 64  f28c39a5bb39d54d
000002XX: 36 XX 37 XX 61 61 36 XX  38 66 66 XX XX 43 XX XX  6471aa608ff..Con
00000240: XX XX XX XX 2D 4C XX XX  XX XX 68 XX 20 XX XX XX  tent-Length: 0..
00000250: 43 XX XX XX XX XX XX XX  XX XX XX 20 4B XX XX 70  Connection: Keep
00000260: 2D 41 6C XX 76 XX XX XX  41 XX XX XX 70 XX 2D 4C  -Alive..Accept-L
00000270: 61 XX XX 75 61 XX XX XX  20 7A 68 2D 43 4E 2C XX  anguage: zh-CN,e
00000280: XX 2C 2A XX XX 48 XX 73  XX XX 20 XX 61 XX 2E 73  n,*..Host: XX.s
00000290: XX XX XX 2E XX XX XX 2E  XX XX XX XX XX 33 XX XX  XX.com.cn:XX..
000002A0: XX XX                                             ..

SSL Session: 98178B604D3B5F25409F1B127543C66AXXC51EEC9BEF32A9FACA7AD9CXX39XXD
[SSL_read] 0.0.0.0:0 --> 0.0.0.0:0
xxxxxxx
```

## Dependencies
- This program uses the [frida](https://www.frida.re/) framework to perform code injection.
    Frida can be installed as follows:
     `pip install frida`
- hexdump (https://bitbucket.org/techtonik/hexdump/) 
  if using verbose output:
    `pip install hexdump`

## Supplementary Explanation
1. The original [ssl_logger](https://github.com/google/ssl_logger/blob/master/ssl_logger.py) from Jason Geffner is for linux/macos,I modified it for windows.
2. There still exist many bugs in this script,maybe I will fix them latter

## Bugs Known
1. The srcHost,dstHost,srcPort,dstPort are all 0s,it is wrong.
2. It cannot capture all ssl traffics in some apps.
3. It may crash when recording traffics into pcap file in some apps.
## TODO
1. fix the bug 1
2. fix the bug 2
3. fix the bug 3
