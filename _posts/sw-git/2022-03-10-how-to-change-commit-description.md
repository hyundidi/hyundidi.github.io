---
title:  "Git Commit 내용 수정"
excerpt: "잔디가 안심어지면 commit 내용을 확인하자"

categories:
  - Git
tags:
  - [Git, Github]

toc: true
toc_sticky: true
 
date: 2022-03-11
last_modified_at: 2022-03-11
---

ps 기록 열심히 commit하는데 왜 잔디가 안 심어져서 슬펐다. 
잔디내놔🌱  
잔디보는 맛에 commit하는건데 왜 그럴까.🤔

## github 잔디 탈모🌳

두둥 

git에 설정된 이메일과 commit의 author 정보가 다르면 잔디가 심어지지 않는다는 걸 알게 되었다!

두둥

git 사이트 우상단 프로필 > settings > email의 정보와 
로컬저장소에서의 email정보가 같아야한다.  
`git config --list`로 확인가능하다. 확인 후 q로 빠져나오기

정보가 다른경우
`git config --global user.email "이메일"`로 새로 설정하면 된다.  
이름바꿀 땐 `git config --global user.name "이름"`
- global옵션 넣으면 모든 repo에서 해당 정보로 바뀌었던듯...

그렇다면 지난 commit은 어떡하지?

## commit 정보 수정

1. `git log` 지난 commit 확인. 
    짧게 보려면 `git log --oneline`
2. 가장 최신 n개 commit을 수정하려면 `git rebase -i HEAD~n`
3. pick ~~ <== 수정할 commit만 골라서 "pick"을 "edit"으로 바꾸고 저장하고 나오기.
4. `git commit --amend` 하고 vi편집기에서 직접 수정하거나
`git commit --amend --author="이름<이메일>"` 입력 후 저장하기
5. 커밋 수정이 완료되었다면 `git rebase --continue`
6. 이렇게 수정할 commit마다 반복
7. 이미 commit이 push되어서 remote에 반영된경우 강제로 푸시하는 수 밖에 없다.`git push -f` 하자. 다만 나 혼자 쓰는 레포가 아니라면.. 신중히 생각하자.
    ~~push해도 다른사람 로그에서는 적용이 안된다했던거 같은데..확인필요~~


push후 다시 github들어가면 잔디가 심어져있다🪴