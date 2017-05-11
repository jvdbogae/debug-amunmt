# Issue 71
When running the commands located in ```scripts/validate-test.sh``` we get an error, causing the validation to fail.
The commands issued are:
```bash
prefix=model/model.npz
dev=data/newsdev2016.bpe.ro
ref=data/newsdev2016.tok.en
cat $dev | ../../build/amun -c $prefix.dev.npz.amun.yml -b 12 -n --mini-batch 10 --maxi-batch 100 

```

Error message:
```bash
*** Error in `../../build/amun': free(): invalid next size (fast): 0x00007f824c00b590 ***
======= Backtrace: =========
/lib/x86_64-linux-gnu/libc.so.6(+0x777e5)[0x7f825af747e5]
/lib/x86_64-linux-gnu/libc.so.6(+0x7fe0a)[0x7f825af7ce0a]
/lib/x86_64-linux-gnu/libc.so.6(cfree+0x4c)[0x7f825af8098c]
../../build/amun[0x436094]
../../build/amun[0x4a8bc8]
../../build/amun[0x4aa57c]
../../build/amun[0x4abb40]
../../build/amun[0x4be2eb]
../../build/amun[0x4be503]
../../build/amun[0x41fbbf]
../../build/amun[0x421cb9]
/lib/x86_64-linux-gnu/libpthread.so.0(+0xea99)[0x7f825f3eea99]
../../build/amun[0x41f54f]
../../build/amun[0x43d8db]
/usr/lib/x86_64-linux-gnu/libstdc++.so.6(+0xb8c80)[0x7f825b594c80]
/lib/x86_64-linux-gnu/libpthread.so.0(+0x76ba)[0x7f825f3e76ba]
/lib/x86_64-linux-gnu/libc.so.6(clone+0x6d)[0x7f825b00382d]
======= Memory map: ========
00400000-006a0000 r-xp 00000000 08:11 20056500                           /home/joachim/repositories/amunmt/build/amun
008a0000-008a8000 r--p 002a0000 08:11 20056500                           /home/joachim/repositories/amunmt/build/amun
008a8000-008a9000 rw-p 002a8000 08:11 20056500                           /home/joachim/repositories/amunmt/build/amun
008a9000-008b4000 rw-p 00000000 00:00 0 
00e04000-00eb9000 rw-p 00000000 00:00 0                                  [heap]
200000000-200100000 rw-s 1d7caf3000 00:06 553                            /dev/nvidiactl
200100000-200104000 rw-s 83799000 00:06 553                              /dev/nvidiactl
200104000-200120000 ---p 00000000 00:00 0 
200120000-200520000 rw-s 1b9c11d000 00:06 553                            /dev/nvidiactl
200520000-200524000 rw-s 6528b000 00:06 553                              /dev/nvidiactl
200524000-200540000 ---p 00000000 00:00 0 
200540000-200940000 rw-s 19102db000 00:06 553                            /dev/nvidiactl
200940000-200944000 rw-s 65142000 00:06 553                              /dev/nvidiactl
200944000-200960000 ---p 00000000 00:00 0 
200960000-200d60000 rw-s 1ae6b26000 00:06 553                            /dev/nvidiactl
200d60000-200e60000 rw-s 18abff8000 00:06 553                            /dev/nvidiactl
200e60000-200e64000 rw-s 1910878000 00:06 553                            /dev/nvidiactl
200e64000-200e80000 ---p 00000000 00:00 0 
200e80000-201280000 rw-s 1e29e1b000 00:06 553                            /dev/nvidiactl
201280000-201284000 rw-s 1e29e19000 00:06 553                            /dev/nvidiactl
201284000-2012a0000 ---p 00000000 00:00 0 
2012a0000-2012a4000 rw-s 1dea84a000 00:06 553                            /dev/nvidiactl
2012a4000-2012c0000 ---p 00000000 00:00 0 
2012c0000-2016c0000 rw-s 1aa6f07000 00:06 553                            /dev/nvidiactl
2016c0000-201ac0000 rw-s 1dea856000 00:06 553                            /dev/nvidiactl
```


