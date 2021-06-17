# 사용법

## 설치

### [Server Setting](./server-setting.md)

### Lumen(메인서버)
> 기본적인 웹서버 설정 및 DB설정은 server-setting.md파일에 포함 되어 있습니다.

#### 설치
```
git clone https://github.com/miniyus/AutomaticPosting-Lumen.git  

```

#### 설정
```
APP_NAME=Lumen
APP_ENV=local
APP_KEY={your-app-key} // 자동 생성을 권장
APP_DEBUG=true
APP_URL=http://localhost
APP_TIMEZONE=Asia/Seoul
APP_PORT=8080

LOG_CHANNEL=stack
LOG_SLACK_WEBHOOK_URL=

DB_CONNECTION=mysql
DB_HOST={your-doamin-or-ip}
DB_PORT=3306
DB_DATABASE=stocks
DB_USERNAME={db-user}
DB_PASSWORD={db-pwd}

DB_WP_DATABASE=wordpress // worpress 데이터 베이스 이름 *고정

CACHE_DRIVER=file
QUEUE_CONNECTION=sync

OPEN_DART_API_KEY={open-dart-api-key} // opendart에서 부여해준 api key

// 윈도우즈 ssh 설정
SSH_WIN_PUB_KEY={ssh-public-key} // public key를 이용하여 ssh 통신을 할 경우 사용
SSH_WIN_PWD={your-windows-password} // password로 ssh통신을 할 경우 사용
SSH_WIN_PY_EXE="activate x86 && python \\your-python-directory\\main.py" // 윈도우즈에서 실행 시킬 cli command
SSH_WIN_HOST="{user-name}@{your-windows-server-ip-or-domain}"

// 워드 프레스 API를 사용하기 위한 계정과 패스워드
WORD_PRESS_ID={wordpress-id} 
WORD_PRESS_PWD={wordpress-pwd}
```

### Word Press

다운로드: https://ko.wordpress.org/download/

설치가 완료되면, apache를 통해 document root만 설정 해주고
나머지는 웹페이지에서 설정 가능합니다.

### windows server
> 기본적인 개발 환경 설정은 server-setting.md파일에 포함 되어 있습니다.

#### 설치
```
git clone https://github.com/miniyus/AutomaticPosting-Python.git

# 해당 프로젝트의 repository폴더로 이동합니다.
cd ./repository

# 해당 프로젝트의 참조 repository입니다.
git clone https://github.com/miniyus/AutomaticPosting-koapy.git

# anaconda 설치 후
activate x86

# koapy를 먼저 설치해야 의존성 에러가 나오지 않습니다.
# 추 후 koapy설치 없이, git clone 만으로 설치가 가능하게 수정할 예정입니다.
pip install koapy

# 받은 repository에서
cd ./repository/koapy

# 수동으로 install
# pip install koapy는 단지 의존성 해결을 위한 동작이며, 아래의 명령을 실행하지 않으면, 업종별 데이터를 불러올 수 없습니다.
python setup.py install
```

### 스케줄링

- 스케줄링은 crontab을 기반으로 하여, Lumen에서 관리해줍니다.

```
# 1. 다운 받은 Lumen 폴더로 이동합니다.

pwd # 현재 절대 경로를 알아야 합니다.

crontab -l # crontab 리스트 체크

crontab # crontab 설정

* * * * * cd /{pwd를 통해 얻은 절대경로} && php artisan schedule:run >> /dev/null 2>&1
```

