---
title: "Git 사용해보기"
date: 2019-05-13 00:43:28 -0400
categories: jekyll update
---
## 1. Git 설치
 데비안 계열 : `sudo apt-get install git-all`  
 Fedora 배포판 : `sudo yum install git-all`  

## 2. 기본 설정
 1) 미리 캐치 저장되어 있을지 모를 계정정보 삭제  
 `git config --global user.email --unset credential.helper`  
 `git config --global user.name --unset credential.helper`  

 2) 이메일과 이름 등록  
 `git config --global user.email --"본인메일"`  
 `git config --global user.name --"본인이름아이디"`  

## 3. 초기화
 1) git을 사용할 폴더 생성하기  
   `mkdir abcdefg`  
   `cd abcdefg`  
 2) 해당 폴더를 git 초기화  
   `git init`  
   => `ls -A`로 확인해보면 .git 폴더가 생성되어 있음
   
## 4. 커밋
 1) 커밋할 목록 파일 추가  
   `vim abc.html`  // 아무렇게나 적어놓고  
   `git add abc.html`  
 2) 커밋하기  
  `git commit -m "메세지"`  
  
## 5. 상태확인  (안해도됨)
'''
 git status  
 git diff  
 git log  
 git shortlog  
 git show  
'''
 
## 6. 푸쉬
 `git remote add origin 저장소URL`  // 저장소URL은 https://github.com/~~~/~~~ .git을 의미  
 `git push origin master`  
 => 충돌이 발생한다면  `git push origin master -f`  
