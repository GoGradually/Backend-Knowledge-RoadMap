- 윈도우에선 my.ini
- 유일하게 존재하고 서버 구동시 찾아서 사용함

## 1. `my.cnf` 파일이란?

`my.cnf` 파일은 MySQL 서버와 클라이언트의 다양한 설정을 정의하는 구성 파일입니다. 이 파일을 통해 데이터베이스 서버의 동작 방식, 성능, 보안 설정 등을 관리할 수 있습니다.

## 2. 파일 위치

`my.cnf` 파일의 위치는 운영 체제와 MySQL 설치 방법에 따라 다를 수 있습니다. 일반적인 위치는 다음과 같습니다:

- **리눅스/유닉스:**
    - `/etc/my.cnf`
    - `/etc/mysql/my.cnf`
    - `~/.my.cnf` (사용자별 설정)
- **윈도우:**
    - `C:\ProgramData\MySQL\MySQL Server X.Y\my.ini`
    - `C:\Windows\my.ini`
- **macOS:**
    - `/usr/local/mysql/my.cnf`
    - `/etc/my.cnf`

## 3. 파일 구조 및 섹션

`my.cnf` 파일은 여러 섹션으로 나뉘며, 각 섹션은 대괄호 `[ ]`로 구분됩니다. 주요 섹션은 다음과 같습니다:

- `[mysqld]`: MySQL 서버 데몬 관련 설정
- `[client]`: 클라이언트 프로그램 관련 설정
- `[mysql]`: MySQL 커맨드 라인 클라이언트 관련 설정
- 기타 특정 프로그램이나 도구를 위한 섹션

### 예시:
```ini
[mysqld]
datadir=/var/lib/mysql
port=3306
socket=/var/run/mysqld/mysqld.sock
max_connections=200
innodb_buffer_pool_size=1G

[client]
port=3306
socket=/var/run/mysqld/mysqld.sock

[mysql]
no-auto-rehash

```

## 4. 주요 설정 항목

### `[mysqld]` 섹션

- **`datadir`**: 데이터베이스 파일이 저장되는 디렉토리 경로.
- **`port`**: MySQL 서버가 리스닝할 포트 번호 (기본값: 3306).
- **`socket`**: 로컬 연결을 위한 소켓 파일 경로.
- **`max_connections`**: 동시에 접속할 수 있는 최대 클라이언트 수.
- **`innodb_buffer_pool_size`**: InnoDB 스토리지 엔진의 버퍼 풀 크기 (성능에 큰 영향).

### `[client]` 섹션

- **`port`**: 클라이언트가 연결할 포트 번호.
- **`socket`**: 클라이언트가 사용할 소켓 파일 경로.

### `[mysql]` 섹션

- **`no-auto-rehash`**: 자동으로 테이블 및 컬럼 이름을 재해시하지 않음 (명령어 완성 속도 향상).

## 5. `my.cnf` 파일 편집 및 적용

1. **백업 생성**: 설정 파일을 수정하기 전에 기존 `my.cnf` 파일의 백업을 만들어 두는 것이 좋습니다.
    `sudo cp /etc/my.cnf /etc/my.cnf.backup`
    
2. **파일 편집**: 텍스트 편집기(예: `vim`, `nano`)를 사용하여 `my.cnf` 파일을 엽니다.
    `sudo vim /etc/my.cnf`
    
3. **설정 변경**: 원하는 설정을 추가하거나 수정합니다.
    
4. **MySQL 서버 재시작**: 설정 변경 사항을 적용하기 위해 MySQL 서버를 재시작합니다.
    `sudo systemctl restart mysqld # 또는 sudo service mysql restart`
    
5. **설정 확인**: MySQL 서버가 정상적으로 시작되었는지 확인합니다.
    `sudo systemctl status mysqld # 또는 sudo service mysql status`