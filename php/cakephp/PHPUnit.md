# PHPUnit

インストール

- wget https://phar.phpunit.de/phpunit.phar
  - エラー: phar.phpunit.de の証明書は信用されません。
  - エラー: phar.phpunit.de の証明書の発行者が不明です。
  
  上記のエラーが出たので、

- wget https://phar.phpunit.de/phpunit.phar --no-check-certificate
  - `--no-check-certificate`(証明書の確認を行わない)

- chmod +x phpunit.phar

- sudo mv phpunit.phar /usr/local/bin/phpunit

- phpunit --version

## 注意

- phpunit --version

↑を実行した時に、PHPUnitがサポートしていないPHPのversionを使用していると以下の文言が出る。

`This version of PHPUnit is supported on PHP 5.6, PHP 7.0, and PHP 7.1.
You are using PHP 5.5.36 (/usr/bin/php).`

- wget https://phar.phpunit.de/phpunit.phar

↑は最新のPHPUnitを取得するので、PHP5.5(>=)の場合はPHPUnitは4.8系を使う(pharファイルはphpunit-4.8.27.phar)

インストール

- wget https://phar.phpunit.de/phpunit-4.8.27.phar --no-check-certificate

- chmod +x phpunit-4.8.27.phar

- sudo mv phpunit-4.8.27.phar /usr/local/bin/phpunit

## コマンドラインからのテスト実行

- ./app/Console/cake test core AllTests
  - コマンドラインからCakePHP全体のテストを行うコマンド

↑を実行すると`include(PHPUnit/Autoload.php): failed to open stream: No such file or directory in〜`というWarningが出てしまい、
`Please install PHPUnit framework v3.7`つまり、PHPUnit3.7をインストールするようにエラー文言が表示される。
