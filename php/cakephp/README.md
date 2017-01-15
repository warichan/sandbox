# CakePHP初期セット
- Cakephpをインストールしたら、ディレクトリの配下にwho.phpを作成
- 作成したwho.phpに ``<?php echo `whoami`; ?>`` を記述
- ビルドインウェブサーバーを起動してブラウザでwho.phpにアクセスすると、CakePHPを動かしているユーザーが表示される
- ターミナルで`sudo chown -R CakePHPを動かしているユーザー名 CakePHPのディレクトリ名/app/tmp` を入力
- パスワードを入力

# 「'Security.salt'」と「'Security.cipherSeed'」を変更する
- app/Config/core.phpの「'Security.salt'」「'Security.cipherSeed'」を変更する必要がある(「'Security.salt'」は半角英数字、「'Security.cipherSeed'」には半角数字を入力/初期設定から変更する)

# DBの設定
- ターミナルでMysqlにrootでログインし、DBを作成
- ユーザを設定する
  - `grant all on DB名.* to ユーザー名@localhost identified by 'パスワード';`
- CakePHPのディレクトリapp/Config内のdatabase.php.defaultを複製してdatabase.phpを作成
- database.phpの末尾辺りのpublic $defaultの(host/login/password/database)の情報を修正

# cssが上手く反映されていない
-  app/View/Layouts/defaultの`echo $this->Html->css('cake.generic');`を`echo $this->Html->css('/app/webroot/css/cake.generic');`に修正
