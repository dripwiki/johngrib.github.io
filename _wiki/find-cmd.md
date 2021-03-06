---
layout  : wiki
title   : find 명령어
summary : walk a file hierarchy
date    : 2019-01-13 17:52:34 +0900
updated : 2020-01-25 21:38:02 +0900
tag     : bash command
toc     : true
public  : true
parent  : [[command-line]]
latex   : false
---
* TOC
{:toc}

## Examples
### 찾기
```sh
 # 현재 디렉토리와 그 하위 디렉토리 전체에서 이름이 "README.md"인 파일을 찾는다.
find . -name 'README.md'

 # 현재 디렉토리와 그 하위 디렉토리 전체에서 이름에 "test"가 들어가는 파일을 찾는다.
find . -name '*test*'

 # 디스크 전체를 뒤져 파일을 찾는다. 에러는 무시한다.
find / -name 'lostfile.txt' 2>/dev/null

 # 사이즈가 1mb 이상인 파일을 찾는다.
find . -size +1024

 # 사이즈가 100 MB 이상인 파일을 모두 찾아 사이즈가 큰 순서대로 정렬한다
find ~/Documents/ -size +100M -ls | sort -k7nr
```

### 삭제
```sh
 # 하위 경로의 빈 디렉토리를 모두 찾아 삭제한다.
find . -type d -empty -delete

 # 하위 경로의 빈 파일을 모두 찾아 삭제한다.
find . -type f -empty -delete
```

### exec 활용
```sh
 # 하위 경로의 CRLF 를 사용하는 모든 파일을 찾는다.
find . -not -type d -exec file '{}' ';' | grep CRLF

 # 이름이 *.temp 인 디렉토리, 파일을 찾아 모두 삭제한다.
find . -name '*.temp' -exec rm -rf {} \;

 # 모든 java 파일에서 중괄호가 없는 if 문이 있는 파일 목록을 출력한다
find . -name "*.java" -exec ag "^\s*if[^{]*$" -l {} \;
```

