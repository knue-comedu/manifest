# How to download KNUE OnlineJudge 

## install repo

```bash
mkdir ~/bin
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
PATH=~/bin:$PATH
```

## python test

python이 이미 설치되어 있음에도 python을 찾을 수 없다는 오류가 발생하면 심볼릭 링크를 생성해준다.

```bash
sudo ln -s /usr/bin/python3 /usr/bin/python
```

참고: [https://codechacha.com/ko/change-python-version/](https://codechacha.com/ko/change-python-version/)

## repo sync

```bash
repo init -u https://github.com/knue-comedu/manifest
repo sync
```

sync 완료 시 KNUE OnlineJudge의 모든 소스가 다운로드 될 것이다.
