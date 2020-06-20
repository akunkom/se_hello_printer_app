# Simple Flask App

Aplikacja Dydaktyczna wyświetlająca imię i wiadomość w różnych formatach dla zajęć
o Continuous Integration, Continuous Delivery i Continuous Deployment.

- W projekcie wykorzystamy virtual environment, dla utworzenia hermetycznego środowisko dla aplikacji:

  ```
  # tworzymy hermetyczne środowisko dla bibliotek aplikacji:
  $ python3 -m venv .venv

  # aktywowanie hermetycznego środowiska
  $ source .venv/bin/activate

  $ make deps

  $ pip install -r requirements.txt
  $ pip install -r test_requirements.txt

  # zobacz
  $ pip list
  ```

  Sprawdź: [tutorial venv](https://docs.python.org/3/tutorial/venv.html) oraz [biblioteki flask](http://flask.pocoo.org).

- Uruchamianie applikacji:

  ```
  # jako zwykły program
  $ python main.py

  # albo:
  $ PYTHONPATH=. FLASK_APP=hello_world flask run
  ```

- Uruchamianie testów (see: http://doc.pytest.org/en/latest/capture.html):

  ```
  $ PYTHONPATH=. py.test
  $ PYTHONPATH=. py.test --verbose -s

  (verbose określa poziom szczegółowości odpowiedzi)
  ```

- Aktywowanie hermetycznego środowiska dla aplikacji py:

  ```
  # deaktywacja
  $ deactivate
  ```
  ```
  ...
  # aktywacja
  $ source .venv/bin/activate
  ```

- Integracja z TravisCI:

  ```
  Plik .travis.yml wykonuje test dla projektu w pythonie (można specyfikować wersję)
  Budowanie projektu: https://docs.travis-ci.com/user/languages/python
  Logowanie na stronie https://travis-ci.org/ (dane GitHuba - projekt automatycznie wykrywany)

  ```

- Docker
  ```
  Komendy Dockera uruchamia się jako root:
  $ sudo su
  ...
  $ exit

  Ustawienie hasła w Settings TravisCI.
  ```

- Heroku  
    ```
    https://devcenter.heroku.com/articles/python-gunicorn
    ```

# Pomocnicze

## Ubuntu

- Instalacja dockera: [dockerce howto](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

Instalacja dla Ubuntu 18.04 (root):
```
$ apt-get update
$ apt-get install -qq apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
$ add-apt-repository 'deb [arch=amd64] https://download.docker.com/linux/ubuntu '$(lsb_release -cs)' stable'
$ apt-get update
$ apt-get install -qq docker-ce
```
### Centos

- Instalacja docker-a:

  ```
  $ yum remove docker \
        docker-common \
        container-selinux \
        docker-selinux \
        dnstall -y yum-utils

  $ yum-config-manager \
      --add-repo \
      https://download.docker.com/linux/centos/docker-ce.repo

  $ yum makecache fast
  $ yum install -y docker-ce
  $ systemctl start docker
  ```


  Status in Travis:
[![Build Status](https://travis-ci.org/akunkom/se_hello_printer_app.svg?branch=master)](https://travis-ci.org/akunkom/se_hello_printer_app)

 Status in StatusCake (Website Monitoring Reporting):
<a href="https://www.statuscake.com" title="Website Uptime Monitoring"><img src="https://app.statuscake.com/button/index.php?Track=hJ3BmgNeFM&Days=1&Design=2" /></a>
