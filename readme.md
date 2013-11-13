# vagrant-berkshelfでRuby環境構築


## 前準備

- VirtualBoxのインストール

  - URL: https://www.virtualbox.org/wiki/Downloads

- Vagrantのインストール

  - URL: http://downloads.vagrantup.com/

- vagrant-berkshelfとvagrant-omnibusプラグインのインストール

  - vagrantセットアップ後、下記実行でインストール。

```
$ vagrant plugin install vagrant-berkshelf
$ vagrant plugin install vagrant-omnibus
```


## 使い方

- 下記コマンドでBOXのDLからレシピDL、VMセットアップまで自動実行します。

```
$ mkdir ruby_lab
$ cd ruby_lab
$ git clone https://github.com/tarVolcano/vagrant-berks_ruby_lab.git .
$ vagrant up
```


## 環境

- Vagrant 1.3.5

- Virtualbox (ホスト：WinXP=4.2.16/MacOS X 10.9=4.3.2)


## 実行により作成されるゲスト環境について

- ゲストOS:CentOS 6.4

- vmメモリ:640MB

- hostname:ruby-lab-vm

- IP:192.168.33.10、private_network

- vagrantBox名:centos-6.4

  - 上のboxがなければ、http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130731.box から自動DL

- vagrant-berkshelfでセットアップされるものは下記のとおり。

  - resolv.confに"options single-request-reopen"がなければ追加する。
  
  - yumのセットアップ。(yum-fastestmirrorインストール、yum update)
  
  - gitのセットアップ。
  
  - ruby2.0.0-p247とrbenvをセットアップ。
  
  - bundlerのインストール

