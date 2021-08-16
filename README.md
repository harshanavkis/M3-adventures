# M3-adventures

## 9 August 2021

- On running below:
```
scons build/X86/gem5.opt build/X86/gem5.debug
```

- Get the following error:
```
scons: Reading SConscript files ...
Warning: Your compiler doesn't support incremental linking and lto at the same time, so lto is being disabled. To force lto on anyway, use the --force-lto option. That will disable partial linking.
Warning: Protocol buffer compiler (protoc) not found.
         Please install protobuf-compiler for tracing support.
Checking for C header file Python.h... yes
Checking for C library python2.7... yes
Checking for C library pthread... yes
Checking for C library dl... yes
Checking for C library util... yes
Checking for C library m... yes
Checking for accept(0,0,0) in C++ library None... yes
Checking for zlibVersion() in C++ library z... yes
Checking for C header file valgrind/valgrind.h... no
Checking for clock_nanosleep(0,0,NULL,NULL) in C library None... yes
Checking for timer_create(CLOCK_MONOTONIC, NULL, NULL) in C library None... no
Checking for timer_create(CLOCK_MONOTONIC, NULL, NULL) in C library rt... yes
Checking for C library tcmalloc... yes
Checking for char temp; backtrace_symbols_fd((void*)&temp, 0, 0) in C library None... yes
Checking for C header file fenv.h... yes
Checking for C header file png.h... yes
Checking for C header file linux/kvm.h... yes
Checking for C header file linux/if_tun.h... yes
Checking size of struct kvm_xsave ... yes
Checking for member exclude_host in struct perf_event_attr...yes
Checking whether __i386__ is declared... no
Checking whether __x86_64__ is declared... yes
Building in M3/hw/gem5/build/X86
Using saved variables file M3/hw/gem5/build/variables/X86
ImportError: cannot import name MemTraceProbe:
  File "M3/hw/gem5/SConstruct", line 1245:
    SConscript('src/SConscript', variant_dir = variant_path, exports = 'env')
  File "/usr/lib/scons/SCons/Script/SConscript.py", line 614:
    return method(*args, **kw)
  File "/usr/lib/scons/SCons/Script/SConscript.py", line 551:
    return _SConscript(self.fs, *files, **subst_kw)
  File "/usr/lib/scons/SCons/Script/SConscript.py", line 256:
    call_stack[-1].globals)
  File "/home/hvub/phd-projs/M3/hw/gem5/build/X86/SConscript", line 693:
    exec('from m5.objects import %s' % modname)
  File "<string>", line 1:
    None
  File "M3/hw/gem5/build/X86/SConscript", line 673:
    exec file(source.abspath, 'r') in mod.__dict__
  File "M3/hw/gem5/src/aladdin/gem5/HybridDatapath.py", line 2:
    from m5.objects import CommMonitor, Cache, MemTraceProbe

```

- following files seem to be missing from gem5: build/X86/gem5.opt, build/X86/gem5.debug

# 16 August 2021

- Solution for above gem5 build error:
  - https://github.com/harvard-acc/gem5-aladdin/issues/8

- boost dependancy
  -  `apt-get install libboost-all-dev `
