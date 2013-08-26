lnmp-precise64-nginx-mysql-php5
=========================

[参考元](https://github.com/yandod/php5-nginx-vagrant-sample)

yandodさん作を基に私なりに、開発しやすい形に改変したものです。

yandodさん、この場を借りて感謝申し上げますw

<table>
<tr>
<th>OS</th>
<td>Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic x86_64)</td>
</tr>
<tr>
<th>PHP</th>
<td>PHP 5.3.10-1ubuntu3.6 with Suhosin-Patch</td>
</tr>
<tr>
<th>Nginx</th>
<td>1.1.19</td>
</tr>
<tr>
<th>MySQL</th>
<td>5.5.31-0ubuntu0.12.04.2 (Ubuntu)</td>
</tr>
</table>


## 使い方

### VirtualBoxをダウンロードしてインストール
VirtualBoxをセットアップしてください。
[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

### Vagrantをダウンロードしてインストール
最新版をインストールしてください。
[http://downloads.vagrantup.com/](http://downloads.vagrantup.com/)

### VagrantプラグインBerkshelfをインストール
<pre>
vagrant plugin install vagrant-berkshelf
</pre>

### このリポジトリをクローン
gitでクローンするか、ZIPなどでダウンロードしてください。
<pre>
git clone https://github.com/ruhenheim/lnmp-precise64-nginx-mysql-php5.git
</pre>

### ソースコードの準備
./sandbox/webapp以下に動作させたいPHPのソースなどを置く又はVagrantfileの設定を書き換えて任意のディレクトリを指します。これでソースコードが仮想マシン内に同期するのでローカルで編集できます。又は以下もありだと思います。
<pre>
rm -rf lnmp-precise64-nginx-mysql-php5/sandbox/webapp
git clone git://(自分の開発中のphpアプリのリポジトリ) lnmp-precise64-nginx-mysql-php5/sandbox/webapp
</pre>

### vagrantを起動
クローンしたリポジトリ内でvagrantを起動。初回のみOSのダウンロードに時間がかかります。
<pre>
cd lnmp-precise64-nginx-mysql-php5
vagrant up
</pre>

### 動作確認
http://(自分のIPアドレス):8080 にアクセスする。IPアドレスを変更する場合はVagrantfileを編集します。
またサーバ内にSSHしたい場合はvagrantコマンドを使います。

<pre>
vagrant ssh
</pre>

### 終了
vagrantコマンドで仮想マシンを終了、又は破棄出来ます。

一旦止めるだけの場合。
<pre>
vagrant halt
</pre>

データを破棄する場合。次回、<code>vagrant up</code>の際にはまっさらなマシンが作成される。
<pre>
vagrant destroy
</pre>

