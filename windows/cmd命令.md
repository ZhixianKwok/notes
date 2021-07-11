#### C 盘清理命令

```bat
@echo off
    echo 正在清除系统垃圾文件，请稍等……
    del /f /s /q %systemdrive%\*.tmp
    del /f /s /q %systemdrive%\*._mp
    del /f /s /q %systemdrive%\*.log
    del /f /s /q %systemdrive%\*.gid
    del /f /s /q %systemdrive%\*.chk
    del /f /s /q %systemdrive%\*.old
    del /f /s /q %systemdrive%\recycled\*.*
    del /f /s /q %windir%\*.bak
    del /f /s /q %windir%\prefetch\*.*
    rd /s /q %windir%\temp & md %windir%\temp
    del /f /q %userprofile%\COOKIES s\*.*
    del /f /q %userprofile%\recent\*.*
    del /f /s /q "%userprofile%\Local Settings\Temporary Internet Files\*.*"
    del /f /s /q "%userprofile%\Local Settings\Temp\*.*"
    del /f /s /q "%userprofile%\recent\*.*"
    sfc /purgecache ‘清理系统盘无用文件
    defrag %systemdrive% -b ‘优化预读信息
    echo 清除系统LJ完成！
exit
```

#### 映射磁盘挂载命令

```bat
net use X: \\10.228.177.100\xxx "pass" /u:"username"
net use Y: \\10.228.177.99\xxx "pass" /u:"username"
net use U: \\10.228.177.99\xxx "pass" /u:"username"
net use T: \\10.228.177.100\xxx "pass" /u:"username"
net use W: \\10.228.177.112\xxx "pass" /u:"username"
```

#### 进程重启命令

```bat
@echo off
    tasklist|find "ncl.exe"
    taskkill /F /im frontpg.exe
    ::判断程序是否启动，如果启动则杀死，在启动，否则启动
    if %errorlevel%==0 (taskkill /f /t /im ncl.exe) else (echo 关闭原始程序,启动新程序,请勿关闭该程序)
    set d=%date:~0,10%
    set t=%time:~0,8%
    echo %d% %t%
    ping 127.0.0.1>nul

    cd /d C:\cygwin\bin
    bash --login   -i -c "ncl xxx.ncl"
exit
```

#### 系统时间调度控制

```bat
@echo off
    :Again
    if "11:00:00" == ?"%time:~0,8%" (
        echo "Called000000000000000",?
        ping 127.0.0.1 -n 2
        goto Again
    ) else (?
        if "16:00:00" == ?"%time:~0,8%" (
        echo "Called11111111111111",?
        ping 127.0.0.1 -n 2
        goto Again
        ) else (?
            if "13:55:00" == ?"%time:~0,8%" (
                echo "Called22222222222222",?
                ping 127.0.0.1 -n 2
                goto Again
            ) else (
                echo "Waiting Call",
                echo %time:~0,8%,
                ping 127.0.0.1 -n 2
                goto Again
            )
        )
    )
```

#### 间隔固定时间重启程序

```bat
@echo off
    set INTERVAL=3600
    :Again
    echo start server
    taskkill /f /t /im demo.exe
    C:
    cd C:\Users\Denison\Desktop\Demo
    start demo.exe
    timeout %INTERVAL%
    goto Again
```

#### 清理 n 天前的文件

```bat
@echo off
    set SrcDir=E:\Desktop\DebugData\clearpathtest
    set DaysAgo=1
    forfiles /p %SrcDir%  /d -%DaysAgo% /c "cmd /c del /f /q /a @path && rd /s /q @path"
```
