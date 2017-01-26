## FormHelper
echo $this->Form->create('モデル名');

echo $this->Form->input('カラム名', array('label'=>'表示する文字'));

echo $this->Form->input('カラム名', array('label'=>'表示する文字'));

echo $this->Form->end('表示する文字');

※array('label'=>'表示する文字')を指定しないと、カラム名がそのまま表示される。
