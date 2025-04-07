# search-java

✅Windows

#Powershell・管理者権限で実行

where.exe /r C:\ java.exe | Where-Object {$_ -notlike "*javapath*"} | ForEach-Object -Process {$_; & "$_" -version }​

##他のドライバーもある場合（D、E、F…）

where.exe /r D:\ java.exe | Where-Object {$_ -notlike "*javapath*"} | ForEach-Object -Process {$_; & "$_" -version }​

※RemainigScrptsをバインドできません。エラの場合

where.exe /r C:\ java.exe | Where-Object { $_ -notlike "*javaPath*" } | ForEach-Object { $regex = [regex]::new("java(\d+\.\d+\.\d+)") ; if (($match=$regex.Match($_ )).Success){$match.Groups[1].Value} else { $_ } }

✅Linux

#Root権限で実行

for JAVA in `find / -name java -type f | grep -v alternatives`; do echo "$JAVA"; $JAVA -version 2>&1 | head -3; done​

##コマンドが異となる場合

sh -c 'for JAVA in `find / -name java -type f | grep -v alternatives`; do echo "$JAVA"; $JAVA -version 2>&1 | head -3; done'​
