AnsibleMemo
===========

Ansibleのメモ

LANGをja_JP.UTF-8に書き換える
```
- name: 言語をja_JP.UTF-8に変更
  lineinfile: dest=/etc/sysconfig/i18n
              regexp='^LANG='
              line='LANG=\"ja_JP.UTF-8\"'
```

接続先ホストを初期化した時、
```
FAILED: Host key for server [ホスト名] does not match!
```
と怒られた時の対処

```
# ホストキーの確認
ssh-keygen -F [ホスト名]

# ホストキーの削除
ssh-keygen -R [ホスト名]

# 削除されたことの確認
ssh-keygen -F [ホスト名]
```

VagrantMemo
===========

Vagrantのメモ

VMの停止
```
vagrant halt [VM名]
```

VMの起動
```
vagrant up [VM名]
```

saharaプラグイン(サンドボックス対応)のインストール
```
vagrant plugin install sahara
```

インストール済みプラグインの確認
```
vagrant plugin list
```

saharaの使い方
```
# サンドボックスモードの開始
vagrant sandbox on [VM名]

# サンドボックスモードの終了(≒コミット)
vagrant sandbox off [VM名]

# 変更をコミット
vagrant sandbox commit [VM名]

# 変更をロールバック
vagrant sandbox rollback [VM名]
```

[VM名]を指定しないとすべてのVMに対して、操作を行う(っぽい)

「"sandbox off"するとコミットしていない内容は削除される」という説明は嘘。  
正しくは、「"sandbox onした時のスナップショット"が削除され、コミットしていない内容はそのまま残る」
