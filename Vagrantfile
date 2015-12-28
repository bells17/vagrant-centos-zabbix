# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos65-x86_64"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"
  config.vm.synced_folder "./", "/vagrant", create:true, :mount_options => ["dmode=777,fmode=777"]

  config.vm.define "zabbix" do |zabbix|
    zabbix.vm.hostname = "zabbix"
    zabbix.vm.network :private_network, ip: "192.168.84.11"
  end

  config.vm.define "client" do |client|
    client.vm.hostname = "client"
    client.vm.network :private_network, ip: "192.168.84.12"
  end

end


=begin
MySQL:
http://yoku0825.blogspot.jp/2015/06/centos-66mysql-57yum.html

root@localhost: 8OptO<MP!/mv

http://qiita.com/hnakamur/items/f3243235793d57a341df
でrootのパスワードを初期化する
SET PASSWORD FOR root@localhost=PASSWORD('8OptO<MP!/mv');

utf-8
http://qiita.com/YusukeHigaki/items/2cab311d2a559a543e3a

zabbixテーブル作成

Zabbix:
なにも考えずに
https://www.zabbix.com/documentation/2.4/manual/installation/install_from_packages#red_hat_enterprise_linux_centos
の
Zabbix 2.4 for RHEL6:
から実行


~httpd の restartまで完了したら↓へアクセス
http://192.168.84.11/zabbix

設定が終わると
http://192.168.84.11/zabbix/dashboard.php
からログイン可能
admin/zabbix
がデフォ

日本語化:
ココらへんみて頑張った

http://sechiro.hatenablog.com/entry/2013/08/27/Zabbix_2.0_%E3%81%AE%E3%82%B0%E3%83%A9%E3%83%95%E3%81%AE%E6%96%87%E5%AD%97%E5%8C%96%E3%81%91%E3%82%92%E7%9B%B4%E3%81%99%E3%80%81%E3%80%8Calternatives%E3%80%8D%E3%81%A7%E3%81%AE%E6%97%A5%E6%9C%AC
http://time-complexity.blogspot.jp/2013/12/zabbix2.2.0-install-server.html
http://kakakakakku.hatenablog.com/entry/2013/12/05/165339

監視設定:
https://blog.apar.jp/zabbix/1046/

---

Agent:
基本
http://qiita.com/yuppi/items/bbc84a6b16eec731f2ad
http://tech-sketch.jp/2014/05/%E3%83%95%E3%83%AA%E3%83%BC%E3%81%A7%E4%BD%BF%E3%81%88%E3%82%8B%E7%B5%B1%E5%90%88%E7%9B%A3%E8%A6%96%E3%81%AE%E9%AC%BC%E3%80%81zabbix%E3%81%A7%E3%83%8A%E3%82%A6%E3%81%84%E7%9B%A3%E8%A6%96%E3%82%92-2.html


=end
