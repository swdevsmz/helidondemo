クイックガイド(HelidonMP)
https://helidon.io/docs/latest/#/guides/03_quickstart-mp

管理者コマンドプロンプトでchocolateyをインストール
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

mvnのインストール
```
choco install -y maven
```

mvnコマンドでプロジェクト作成
```
mvn archetype:generate -DinteractiveMode=false ^
-DarchetypeGroupId=io.helidon.archetypes ^
-DarchetypeArtifactId=helidon-quickstart-mp ^
-DarchetypeVersion=1.4.0 ^
-DgroupId=io.helidon.examples ^
-DartifactId=helidon-quickstart-mp ^
-Dpackage=io.helidon.examples.quickstart.mp
```

アーキタイプは、現在のディレクトリ（たとえば、helidon-quickstart-mp）にMavenプロジェクトを生成します。このディレクトリに移動します。
```
cd helidon-quickstart-mp
```

アプリケーションを構築する
```
mvn package
```

アプリケーションを実行する
```
java -jar target/helidon-quickstart-mp.jar
```