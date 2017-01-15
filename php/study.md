# CakePHP初期セット
- Cakephpをインストールしたら、ディレクトリの配下にwho.phpを作成
- 作成したwho.phpに<?php echo `whoami`; ?>を記述
- ビルドインウェブサーバーを起動してブラウザでwho.phpにアクセスすると、CakePHPを動かしているユーザーが表示される
- ターミナルでsudo chown -R CakePHPを動かしているユーザー名 CakePHPのディレクトリ名/app/tmp を入力
- パスワードを入力

# DBの設定
- ターミナルでMysqlにrootでログインし、DBを作成
- ユーザを設定する(grant all on DB名.* to ユーザー名@localhost identified by 'パスワード';)
- CakePHPのディレクトリapp/Config内のdatabase.php.defaultを複製してdatabase.phpを作成
- database.phpの末尾辺りのpublic $defaultの(host/login/password/database)の情報を修正

# cssが上手く反映されていない
-  app/View/Layouts/defaultのecho $this->Html->css('cake.generic');をecho $this->Html->css('/app/webroot/css/cake.generic');に修正
