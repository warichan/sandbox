# PHPUnit

## PHP Archive(pear)を使ったインストール

※以下のようにpearを使ったインストールが一般的らしいが、
Pearから最新のPHPUnit（バージョン4.x）をダウンロードすると、CakePHPからPHPUnitを認識するために必要なファイルが解凍されない問題が発生するので、
Composerを使ってインストールするのがよい。

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

## PHP Archive(pear)を使ったインストール(PHPUnitのversion指定)

- wget https://phar.phpunit.de/phpunit-4.8.27.phar --no-check-certificate

- chmod +x phpunit-4.8.27.phar

- sudo mv phpunit-4.8.27.phar /usr/local/bin/phpunit

## コマンドラインからのテスト実行

- ./app/Console/cake test core AllTests
  - コマンドラインからCakePHP全体のテストを行うコマンド

↑を実行すると`include(PHPUnit/Autoload.php): failed to open stream: No such file or directory in〜`というWarningが出てしまい、
`Please install PHPUnit framework v3.7`つまり、PHPUnit3.7をインストールするようにエラー文言が表示される。

ーーーーーーーーーー

## Composerを使ったインストール

- `cd app/Vendor`
  - PHPUnitをインストールしたいフォルダへ移動
  
- `vi composer.json`
  - ↑で作ったcomposer.jsonに以下を記述
  
```php
{
  "name": "phpunit",
　　  "description": "PHPUnit",
　　  "require": {
　　　    "phpunit/phpunit": "3.7.*"
　　  },
　　  "config": {
　　　    "vendor-dir": "app/Vendor/PHPUnit"
　　  }
　}
 ```
- `wget http://getcomposer.org/composer.phar`
  - composerをダウンロード

- `　php composer.phar install`
  - app/Vendor配下にPHPUnitディレクトリが作成される

- `require_once ROOT . DS . 'app' . DS . 'Vendor' . DS . 'PHPUnit' . DS . 'autoload.php';`
  - CakePHP側でPHPUnitを読み込んでいるパスを書き換える(app/Config/bootstrap.php)
