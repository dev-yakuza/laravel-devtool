## document
- [laravel-devtool使い方](#laravel-devtool使い方)
- [laravel-devtool 사용법](#laravel-devtool-사용법)
- [how to use laravel-devtool](#how-to-use-laravel-devtool)

## laravel-devtool使い方
Laradockとアンシブル(Ansible)を使って仮想マシン(guest system)にララベル(Laravel)開発環境を構成したレポジトリ(Repository)です。

このレポジトリ(Repository)は下記の内容でララベル(Laravel)の環境を作ります。
- nginx
- mysql
- phpmyadmin
- workspace
- ngrok

### laravel-devtool設定方法
このlaravel-devtoolのレポジトリ(Repository)を生成しながら作成したブログがあります。下記のブログを参考してlaravel-devtoolの設定を変更することができます。

- vagrantインストールや使い方: <a href="https://dev-yakuza.github.io/environment/vagrant-install-and-usage/" target="_blank">https://dev-yakuza.github.io/environment/vagrant-install-and-usage</a>
- アンシブルインストール: <a href="https://dev-yakuza.github.io/environment/install-ansible/" target="_blank">https://dev-yakuza.github.io/environment/install-ansible</a>
- アンシブルプレイブック: <a href="https://dev-yakuza.github.io/environment/ansible-playbook/" target="_blank">https://dev-yakuza.github.io/environment/ansible-playbook</a>
- アンシブル&ドッカー: <a href="https://dev-yakuza.github.io/environment/ansible-docker/" target="_blank">https://dev-yakuza.github.io/environment/ansible-docker</a>
- アンシブル&Laradock: <a href="https://dev-yakuza.github.io/environment/ansible-laradock/" target="_blank">https://dev-yakuza.github.io/environment/ansible-laradock</a>
- アンシブル&ララベル: <a href="https://dev-yakuza.github.io/environment/ansible-laravel/" target="_blank">https://dev-yakuza.github.io/environment/ansible-laravel</a>
- ngrok: <a href="https://dev-yakuza.github.io/environment/ngrok/" target="_blank">https://dev-yakuza.github.io/environment/ngrok</a>

### 環境準備
このlaravel-devtoolを使うためには```virtualbox```と```vagrant(v2.2.1以上)```をローカル(host system)にインストールする必要があります。

virtualboxとvagrantのインストール方法は下記のブログを参考してください。

- <a href="" target="_blank">https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage</a>

### 使い方
laravel-devtoolのレポジトリ(Repository)をコピー(clone)します。.

```bash
git clone https://github.com/dev-yakuza/laravel-devtool.git
```

下のvagrantコマンドで仮想マシン(guest system)を構成します。

```bash
# cd laravel-devtool
vagrant up
```

環境を構成するには結構時間がかかります。コーヒを一杯飲んできたらいいと思います。

新しララベル(Laravel)プロジェクトを生成します。

```bash
# vagrant ssh
cd /vagrant
composer create-project laravel/laravel app
```

既存のララベル(Laravel)プロジェクトがある方は```app```フォルダにプロジェクトをコピーして使ってください。

#### ngrok
外部で仮想環境(Guest System)へ接続するため```ngrok```を使えることができます。

```bash
# vagrant up
vagrant ssh
# sudo ansible-playbook /vagrant/ansible/playbook.yml --tags 'ngrok'
cd /vagrant/
./ngrok http -region=ap 80
```

上のようにngrokを実行したら下記のような画面が見えます。

```
Session Status                online
Session Expires               7 hours, 59 minutes
Version                       2.2.8
Region                        Asia Pacific (ap)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://cf354047.ap.ngrok.io -> localhost:80
Forwarding                    https://cf354047.ap.ngrok.io -> localhost:80
```

ここに見える```Forwarding```のURLを使ったら外部から仮装環境(Guest System)に接続できます。これはテスト、開発のためですので開発、テストする時だけ使ってください。

### 確認
ララベル(Laravel)プロジェクトは```localhost```で接続できます。phpmyadminは```localhost:8080```で接続できます。

もっと詳しく内容は下のブログを参考してください。

- アンシブル&ララベル: <a href="https://dev-yakuza.github.io/environment/ansible-laravel/" target="_blank">https://dev-yakuza.github.io/environment/ansible-laravel</a>


## laravel-devtool 사용법
Laradock과 앤서블(Ansible)을 이용하여 가상 머신(guest system)에 라라벨(Laravel) 개발 환경을 구성한 저장소(Repository)입니다.

이 저장소(Repository)는 아래에 내용으로 라라벨(Laravel) 환경을 구성합니다.
- nginx
- mysql
- phpmyadmin
- workspace
- ngrok

### laravel-devtool 설정 방법
laravel-devtool의 저장소(Repository)를 생성하고 구성하며 작성한 블로그가 있습니다. 아래에 블로그를 참고하여 원하는 구성으로 변경하실 수 있습니다.

- vagrant 설치 및 사용법: <a href="https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage/" target="_blank">https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage</a>
- 앤서블 설치: <a href="https://dev-yakuza.github.io/ko/environment/install-ansible/" target="_blank">https://dev-yakuza.github.io/ko/environment/install-ansible</a>
- 앤서블 플레이북: <a href="https://dev-yakuza.github.io/ko/environment/ansible-playbook/" target="_blank">https://dev-yakuza.github.io/ko/environment/ansible-playbook</a>
- 앤서블&도커: <a href="https://dev-yakuza.github.io/ko/environment/ansible-docker/" target="_blank">https://dev-yakuza.github.io/ko/environment/ansible-docker</a>
- 앤서블&라라독: <a href="https://dev-yakuza.github.io/ko/environment/ansible-laradock/" target="_blank">https://dev-yakuza.github.io/ko/environment/ansible-laradock</a>
- 앤서블&라라벨: <a href="https://dev-yakuza.github.io/ko/environment/ansible-laravel/" target="_blank">https://dev-yakuza.github.io/ko/environment/ansible-laravel</a>
- ngrok: <a href="https://dev-yakuza.github.io/ko/environment/ngrok/" target="_blank">https://dev-yakuza.github.io/ko/environment/ngrok</a>

### 환경 준비
laravel-devtool을 사용하기 위해서는 ```virtualbox```와 ```vagrant(v2.2.1이상)```를 로컬 머신(host system)에 설치하셔야 합니다.

virtualbox와 vagrant 설치 방법은 아래에 블로그를 참고하시기 바랍니다.

- <a href="https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage/" target="_blank">https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage</a>


### 사용 방법
laravel-devtool의 저장소(Repository)를 복사(clone)합니다.

```bash
git clone https://github.com/dev-yakuza/laravel-devtool.git
```

아래의 vagrant 명령어를 통해 가상 머신(guest system)을 구성합니다.

```bash
# cd laravel-devtool
vagrant up
```

환경을 구성하는데 상단한 시간이 걸립니다. 커피를 한잔 하고 오시면 좋을거 같네요.

새로운 라라벨(Laravel) 프로젝트를 생성합니다.

```bash
# vagrant ssh
cd /vagrant
composer create-project laravel/laravel app
```

기존에 라라벨(Laravel) 프로젝트를 가지고 계신 분들은 ```app``` 폴더에 프로젝트를 복사하여 사용하십시오.

#### ngrok
외부에서 가상 머신(Guest System)에 접근하기 위해 ```ngrok```를 사용하실 수 있습니다.

```bash
# vagrant up
vagrant ssh
# sudo ansible-playbook /vagrant/ansible/playbook.yml --tags 'ngrok'
cd /vagrant/
./ngrok http -region=ap 80
```

위와 같이 ngrok를 실행하면 아래와 같은 화면이 보입니다.

```
Session Status                online
Session Expires               7 hours, 59 minutes
Version                       2.2.8
Region                        Asia Pacific (ap)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://cf354047.ap.ngrok.io -> localhost:80
Forwarding                    https://cf354047.ap.ngrok.io -> localhost:80
```

여기서 보이는 ```Forwarding``` URL을 사용하여 외부에서 가상 환경(Guest System)에 접속이 가능합니다. 어디까지나 테스트용이므로 개발이나 테스트할 때에만 사용하시기 바랍니다.


### 확인
라라벨(Laravel) 프로젝트는 ```localhost```로 접근이 가능하며 phpmyadmin은 ```localhost:8080``` 접근이 가능합니다.

자세한 내용은 아래에 블로그를 참고해 주세요.

- 앤서블&라라벨: <a href="https://dev-yakuza.github.io/ko/environment/ansible-laravel/" target="_blank">https://dev-yakuza.github.io/ko/environment/ansible-laravel</a>


## how to use laravel-devtool
this repository makes Laravel development environment by using Laradock and Ansible.

this repository makes Laravel development environment by configured belows.
- nginx
- mysql
- phpmyadmin
- workspace
- ngrok

### laravel-devtool settings
we've written blogs while we were making laravel-devtool repository. if you want to change settings, see below blogs to get how to modify configurations.

- vagrant installation and usage: <a href="https://dev-yakuza.github.io/en/environment/vagrant-install-and-usage/" target="_blank">https://dev-yakuza.github.io/en/environment/vagrant-install-and-usage</a>
- Ansible installation: <a href="https://dev-yakuza.github.io/en/environment/install-ansible/" target="_blank">https://dev-yakuza.github.io/en/environment/install-ansible</a>
- Ansible Playbook: <a href="https://dev-yakuza.github.io/en/environment/ansible-playbook/" target="_blank">https://dev-yakuza.github.io/en/environment/ansible-playbook</a>
- Ansible&Docker: <a href="https://dev-yakuza.github.io/en/environment/ansible-docker/" target="_blank">https://dev-yakuza.github.io/en/environment/ansible-docker</a>
- Ansible&Laradock: <a href="https://dev-yakuza.github.io/en/environment/ansible-laradock/" target="_blank">https://dev-yakuza.github.io/en/environment/ansible-laradock</a>
- Ansible&Laravel: <a href="https://dev-yakuza.github.io/en/environment/ansible-laravel/" target="_blank">https://dev-yakuza.github.io/en/environment/ansible-laravel</a>
- ngrok: <a href="https://dev-yakuza.github.io/en/environment/ngrok/" target="_blank">https://dev-yakuza.github.io/en/environment/ngrok</a>

### prepare the environment
you need to install ```virtualbox``` and ```vagrant(upper than v2.2.1)``` at your local machine(host system) to use laravel-devtool repository.

if you don't know how to install virtualbox and vagrant, see below blog.

- <a href="https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage/" target="_blank">https://dev-yakuza.github.io/ko/environment/vagrant-install-and-usage</a>


### usage
clone laravel-devtool repository.

```bash
git clone https://github.com/dev-yakuza/laravel-devtool.git
```

execute below vagrant command to configure virtual machine(guest system)

```bash
# cd laravel-devtool
vagrant up
```

it takes long time to configure the environment. we recommend you to drink a cup of coffee.

create new Laravel project.

```bash
# vagrant ssh
cd /vagrant
composer create-project laravel/laravel app
```

if you already have Laravel project, copy your project to ```app``` folder.

#### ngrok
you can use ```ngrok`` to access Guest System from outside.

```bash
# vagrant up
vagrant ssh
# sudo ansible-playbook /vagrant/ansible/playbook.yml --tags 'ngrok'
cd /vagrant/
./ngrok http 80
```

if you execute above command, you can see below screen.

```
Session Status                online
Session Expires               7 hours, 59 minutes
Version                       2.2.8
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://69bd767c.ngrok.io -> localhost:80
Forwarding                    https://69bd767c.ngrok.io -> localhost:80
```

you can access Guest system by ```Forwarding``` URL in above screen. this is for developing and testing, so use it when you develop or test.

### check
you can see Laravel project to access ```localhost``` and see phpmyadmin to access ```localhost:8080```

if you want more details, check below blog.

- Ansible&Laravel: <a href="https://dev-yakuza.github.io/ko/environment/ansible-laravel/" target="_blank">https://dev-yakuza.github.io/ko/environment/ansible-laravel</a>
