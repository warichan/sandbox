# 命名規則
## Model
テーブル名を単数形にしたもの

※postsテーブルであれば、Model名は__Post__となる

## View(フォルダ)
コントローラ名を複数形にしたもの

※コントローラ名は元々複数形なので、同じと考えてOK

## View(ファイル)
コントローラのアクション名.ctp

※PostsControllerのindexアクションであれば、__Posts__フォルダに__index.ctp__ファイルを作成する

## Controller
関連させるモデル名を複数形にしたもの

※Postモデルであれば__PostsController__となる

----------

# 拡張
## Model
```
<?php
  class モデル名 extends AppModel{
  
  }
?>
```

## Controller
```
<?php
  class コントローラ名　extends AppController{
  
  }
?>
```

----------

# タイトル
viewファイルに以下を設定する
```
<?php $this->assign('title', 'タイトルに表示する文字'); ?>
```
-----------

# scaffold
## scaffoldを実行した際に、作成されるアクション
- index
- view
- edit
- add
- delete

----------

# Helper
## FormHelper
echo $this->Form->create('モデル名');

echo $this->Form->input('カラム名', array('label'=>'表示する文字'));

echo $this->Form->input('カラム名', array('label'=>'表示する文字'));

echo $this->Form->end('表示する文字');

※array('label'=>'表示する文字')を指定しないと、カラム名がそのまま表示される。


----------

## link
echo $this->Html->link('表示する文字',array('action'=>'リンク先のアクション名'));
