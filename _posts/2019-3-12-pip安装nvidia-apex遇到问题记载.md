---
bg: "tools.jpg"
layout: post
title:  "anaconda下使用pip安装apex报错"
crawlertitle: "anaconda下使用pip安装apex报错"
summary: "anaconda下使用pip安装apex报错"
date:   2018-3-12 12:55:29 +0800
categories: posts
tags: ['python']
author: haohhxx
---

anaconda下使用pip安装apex报错
```
    C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\x86_amd64\cl.exe /c /nologo /Ox /W3 /GL /DNDEBUG /MD -DNO_BF_ASM -Icrypt_blowfish-1.2/ -Ie:\envir\64\anaconda3\include -Ie:\envir\64\anaconda3\include "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\INCLUDE" "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\ATLMFC\INCLUDE" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\NETFXSDK\4.6.1\include\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt" /Tccrypt_blowfish-1.2/crypt_blowfish.c /Fobuild\temp.win-amd64-3.6\Release\crypt_blowfish-1.2/crypt_blowfish.obj
    crypt_blowfish.c
    crypt_blowfish-1.2/crypt_blowfish.c(898): warning C4244: “=”: 从“unsigned long”转换到“char”，可能丢失数据
    C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\x86_amd64\cl.exe /c /nologo /Ox /W3 /GL /DNDEBUG /MD -DNO_BF_ASM -Icrypt_blowfish-1.2/ -Ie:\envir\64\anaconda3\include -Ie:\envir\64\anaconda3\include "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\INCLUDE" "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\ATLMFC\INCLUDE" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\NETFXSDK\4.6.1\include\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt" /Tccrypt_blowfish-1.2/crypt_gensalt.c /Fobuild\temp.win-amd64-3.6\Release\crypt_blowfish-1.2/crypt_gensalt.obj
    crypt_gensalt.c
    C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\x86_amd64\cl.exe /c /nologo /Ox /W3 /GL /DNDEBUG /MD -DNO_BF_ASM -Icrypt_blowfish-1.2/ -Ie:\envir\64\anaconda3\include -Ie:\envir\64\anaconda3\include "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\INCLUDE" "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\ATLMFC\INCLUDE" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\NETFXSDK\4.6.1\include\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt" /Tccrypt_blowfish-1.2/wrapper.c /Fobuild\temp.win-amd64-3.6\Release\crypt_blowfish-1.2/wrapper.obj
    wrapper.c
    crypt_blowfish-1.2/wrapper.c(245): warning C4996: 'strdup': The POSIX name for this item is deprecated. Instead, use the ISO C and C++ conformant name: _strdup. See online help for details.
    C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\ucrt\string.h(536): note: 参见“strdup”的声明
    C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\x86_amd64\cl.exe /c /nologo /Ox /W3 /GL /DNDEBUG /MD -DNO_BF_ASM -Icrypt_blowfish-1.2/ -Ie:\envir\64\anaconda3\include -Ie:\envir\64\anaconda3\include "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\INCLUDE" "-IC:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\ATLMFC\INCLUDE" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\ucrt" "-IC:\Program Files (x86)\Windows Kits\NETFXSDK\4.6.1\include\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\shared" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um" "-IC:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt" /Tccryptacular/bcrypt/_bcrypt.c /Fobuild\temp.win-amd64-3.6\Release\cryptacular/bcrypt/_bcrypt.obj
    _bcrypt.c
    cryptacular/bcrypt/_bcrypt.c(80): warning C4244: “函数”: 从“const Py_ssize_t”转换到“int”，可能丢失数据
    C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\x86_amd64\link.exe /nologo /INCREMENTAL:NO /LTCG /DLL /MANIFEST:EMBED,ID=2 /MANIFESTUAC:NO /LIBPATH:e:\envir\64\anaconda3\libs /LIBPATH:e:\envir\64\anaconda3\PCbuild\amd64 "/LIBPATH:C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\LIB\amd64" "/LIBPATH:C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\ATLMFC\LIB\amd64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.17134.0\ucrt\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\NETFXSDK\4.6.1\lib\um\x64" "/LIBPATH:C:\Program Files (x86)\Windows Kits\10\lib\10.0.17134.0\um\x64" /EXPORT:PyInit__bcrypt build\temp.win-amd64-3.6\Release\crypt_blowfish-1.2/crypt_blowfish.obj build\temp.win-amd64-3.6\Release\crypt_blowfish-1.2/crypt_gensalt.obj build\temp.win-amd64-3.6\Release\crypt_blowfish-1.2/wrapper.obj build\temp.win-amd64-3.6\Release\cryptacular/bcrypt/_bcrypt.obj /OUT:build\lib.win-amd64-3.6\cryptacular\bcrypt\_bcrypt.cp36-win_amd64.pyd /IMPLIB:build\temp.win-amd64-3.6\Release\crypt_blowfish-1.2\_bcrypt.cp36-win_amd64.lib
      正在创建库 build\temp.win-amd64-3.6\Release\crypt_blowfish-1.2\_bcrypt.cp36-win_amd64.lib 和对象 build\temp.win-amd64-3.6\Release\crypt_blowfish-1.2\_bcrypt.cp36-win_amd64.exp
    正在生成代码
    已完成代码的生成
    LINK : fatal error LNK1158: 无法运行“rc.exe”
    error: command 'C:\\Program Files (x86)\\Microsoft Visual Studio 14.0\\VC\\BIN\\x86_amd64\\link.exe' failed with exit status 1158

    ----------------------------------------
Command "e:\envir\64\anaconda3\python.exe -u -c "import setuptools, tokenize;__file__='C:\\Users\\haohhxx\\AppData\\Local\\Temp\\pip-install-t76t_f6l\\cryptacular\\setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" install --record C:\Users\haohhxx\AppData\Local\Temp\pip-record-vd5h1roo\install-record.txt --single-version-externally-managed --compile" failed with error code 1 in C:\Users\haohhxx\AppData\Local\Temp\pip-install-t76t_f6l\cryptacular\

```

原因是环境混乱，没有正确的使用VS编译环境，改用VS2017开发人员cmd 运行命令后正常安装。


