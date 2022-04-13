# How to download KNUE OnlineJudge 

## Download KNUE-OJ

### Using repo

1. install repo

```bash
mkdir ~/bin
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
PATH=~/bin:$PATH
```

2. python test

```bash
python
```

python이 이미 설치되어 있음에도 python을 찾을 수 없다는 오류가 발생하면 심볼릭 링크를 생성해준다.

```bash
sudo ln -s /usr/bin/python3 /usr/bin/python
```

참고: [https://codechacha.com/ko/change-python-version/](https://codechacha.com/ko/change-python-version/)

3. repo sync

```bash
repo init -u https://github.com/knue-comedu/manifest
repo sync
```

sync 완료 시 KNUE OnlineJudge의 모든 소스가 다운로드 될 것이다.

### Using git clone

1. Enter following command

```bash
mkdir knue-oj
cd knue-oj

git clone https://github.com/knue-comedu/Judger
git clone https://github.com/knue-comedu/JudgeServer
git clone https://github.com/knue-comedu/OnlineJudgeFE
git clone https://github.com/knue-comedu/OnlineJudgeBE
git clone https://github.com/knue-comedu/OnlineJudgeDeploy

cp OnlineJudgeDeploy/docker-compose.yml docker-compose.yml
```

## Front-End build and docker-compose run

1. move OnlineJudgeFE and npm build

```bash
cd OnlineJudgeFE

npm install
npm run build:dll
npm run build

cd ..
```

2. docker-compose up

```bash
docker-compose up -d --build
```

## 참고

Judger JudgeServer OnlineJudgeBE OnlineJudgeFE 폴더와 docker-compose.yml 파일이 한 폴더 안에 함께 있어야 한다.

```bash
$ tree -L 1

├── JudgeServer  
├── Judger  
├── OnlineJudgeBE  
├── OnlineJudgeDeploy  
├── OnlineJudgeFE  
└── docker-compose.yml
```