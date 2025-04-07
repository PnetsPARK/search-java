# search-java

✅Windows

#Powershell・管理者権限で実行

#where.exe /r C:\ java.exe | Where-Object {$_ -notlike "*javapath*"} | ForEach-Object -Process {$_; & "$_" -version }

##他のドライバーもある場合（D、E、F…）

#where.exe /r D:\ java.exe | Where-Object {$_ -notlike "*javapath*"} | ForEach-Object -Process {$__; & "$__" -version }​

✅Linux

#Root権限で実行

for JAVA in `find / -name java -type f | grep -v alternatives`; do echo "$JAVA"; $JAVA -version 2>&1 | head -3; done​

##コマンドが異となる場合

sh -c 'for JAVA in `find / -name java -type f | grep -v alternatives`; do echo "$JAVA"; $JAVA -version 2>&1 | head -3; done'​
