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
