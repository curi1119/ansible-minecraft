# macaron-ansible

ansible configs for minecraft on EC2 AmazonLinux2

## Vagrant (on local test)

### テストコマンドサンプル

```
# VM起動
$ vagrant init
$ vagrant up


# vagrant-rootへコマンド実行
$ ansible vagrant-root -i hosts/vagrant -v -m ping
$ ansible vagrant-root -i hosts/vagrant -v -a "cat /etc/system-release"
```

### Playbook実行

```
# OSの基本設定実行 ユーザ作成、ロケール,タイムゾーン設定、suders設定など）
$ ansible-playbook ./build-common.yml -i hosts/inventory -v

# Mincraft Setup
$ ansible-playbook ./build-minecraft.yml -i hosts/inventory -v

# UPDATE
$ ansible-playbook ./update-minecraft.yml -i hosts/inventory -v
```
