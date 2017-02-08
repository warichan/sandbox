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


## FormHelper
echo $this->Form->create('モデル名');

echo $this->Form->input('カラム名', array('label'=>'表示する文字'));

echo $this->Form->input('カラム名', array('label'=>'表示する文字'));

echo $this->Form->end('表示する文字');

※array('label'=>'表示する文字')を指定しないと、カラム名がそのまま表示される。
