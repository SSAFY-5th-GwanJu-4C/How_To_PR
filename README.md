# 환경 설정하기 
## 포크하기 
프로젝트를 자신의 계정으로 fork한다.    
저장소 우측 상단의 fork 버튼을 활용한다.
  
[사진]()  
    
fork를 완료한 후의 상태는 다음과 같다.
      
[사진]()  
  
## 클론하기   
clone 은 github.com에 존재하는 저장소를 자신의 노트북 또는 PC로 복사하는 과정이다.  
fork한 저장소를 자신의 컴퓨터로 clone한 후 디렉토리로 이동하도록 하자.   

    
**터미널에서 다음 명령을 입력한다.**  
```terminal
git clone -b {본인_아이디} --single-branch https://github.com/{본인_아이디}/{저장소 아이디}
``` 
* ex) `git clone -b kwj1270 --single-branch https://github.com/kwj1270/ssafy-java-racingcar`
   
clone을 완료한 후의 상태는 다음과 같다.   
  
[사진]()  
  
# IntelliJ 시작   
## 기능 구현을 위한 브랜치 생성   
git은 서로 다른 작업을 하기 위한 별도의 공간을 생성할 때 브랜치를 생성할 수 있다.   
   
브랜치를 생성하는 이유는 실무에서 프로젝트를 진행할 때와 같은 방법으로 기능을 구현하고,    
리뷰하는 경험을 전달하기 위함이다.   
     
**터미널에서 다음 명령을 입력해 브랜치를 생성한다.**
```terminal
git checkout -b 브랜치이름
````
* ex) `git checkout -b step1`
브랜치를 생성한 후의 상태는 다음과 같다.

[사진]()   

     
## 기능 구현 
미션 요구사항을 파악해 기능을 구현한다.    
   
**기능 구현 후 `add` -> `commit`**    
기능 구현을 완료한 후 로컬 저장소에 변경된 부분을 반영하기 위해 `add`, `commit` 명령을 사용한다. 
     
```git 
git status // 변경된 파일 확인
git add .(또는 -A) // 변경된 전체 파일을 한번에 반영
git commit -m "메시지" // 작업한 내용을 메시지에 기록
```   
기능 구현을 완료하고 add, commit 명령을 실행한 후의 상태는 다음과 같다.
  
[사진]()  
    
## 본인 원격 저장소에 올리기 
로컬에서 commit 명령을 실행하면 로컬 저장소에만 반영되고,         
원격 github.com의 저장소에는 반영되지는 않는다.  
       
```git   
git push origin 브랜치이름 (remote별칭인데, 클론하면 대부분 origin이다.)   
```
* ex) `git push origin step1`
     
push 명령을 실행한 후의 상태는 다음과 같다.   
  
[사진]()   
   
# 코드 리뷰 받기 
pull request를 통해 코드 리뷰 요청을 한 후 피드백을 받고, 피드백을 반영하는 과정을 다룬다.   
        
github 서비스에서 `pull request`를 보낸다.       
`pull request`는 `github`에서 제공하는 기능으로 코드리뷰 요청을 보낼 때 사용한다.     
      
`pull request`는 `original` 저장소의 브랜치(자신의 github 아이디)와      
앞 단계에서 생성한 브랜치 이름(앞 단계의 예에서는 step1)을 기준으로 한다.     
        
즉, 각자의 아이디에 맞게끔 Pr 을 날리면 된다.        
   
```
kwj1270 <= step1 
```
    
## 작업 설명 (브라우저에서)  
브라우저에서 `github` 저장소에 접근한다.   
브랜치를 작업 브랜치로 변경한다(앞 단계의 예에서는 step1).   
브랜치 오른쪽에 있는 `New pull request` 버튼을 클릭한다.   
                 
**pull request 보내기**           
1. 저장소의 브랜치를 자신의 `github` 계정 브랜치로 변경한다.     
2. 현재 미션에서 작업한 내용을 입력하고 `"Create pull request"` 버튼을 클릭해 `pull request`를 보낸다.   
3. `pull request` 브랜치 변경    
            
`pull request`를 보낸 후 리뷰어에게 리뷰 요청을 한다. **(단톡방에 리뷰 요청 메시지 보내주세요)**           
              
`pull request`에 대해 **승인이 되지 않고 수정 요청 피드백을 받으면 피드백 받은 내용을 반영한다.**          
만약, `pull request`가 **승인이 되어 저장소에 `merge` 된다면 아래 다음 단계의 설명을 보면된다.**          
     
피드백을 받았다면 **피드백을 반영한 후 `add, commit, push` 명령을 실행한다.**           
참고로, `add, commit, push` 만 한다면 `pull request` 요청은 다시 안 보내도 된다.    
  
```git
git status // 변경된 파일 확인
git add -A(또는 .) // 변경된 전체 파일을 한번에 반영
git commit -m "메시지" // 작업한 내용을 메시지에 기록
git push origin 브랜치이름
```
* `ex) git push origin step1`  
     
몇 번의 피드백을 주고 받은 후 승인이 되어 저장소에 `merge`된다면 아래 단계를 진행한다.        
          
# merge 이후에는     
`merge`를 완료했다는 통보를 받으면 브랜치 변경 및 작업 브랜치 삭제(option)한다.      
`merge`를 완료했다는 통보를 받으면 해당 스텝은 완료한 상태가 된다     
            
현재 미션을 완료했기 때문에 **미션을 진행한 브랜치를 삭제하고**        
다음 미션을 위한 **새로운 브랜치를 생성해야 한다.**    
         
```  
git checkout 본인_아이디  
git branch -D 삭제할_브랜치이름  
```
        
통합(merge)한 저장소와 동기화하기 위해 저장소 추가`(최초 한번만)`     
계정 브랜치에서 다음 미션을 이어서 진행하기 위해 브랜치를 생성하려고 한다.     
            
그런데 로컬 PC의 현재 상태는 최신 코드가 아니기 때문에 미션을 이어서 진행할 수 없다.    
따라서 **저장소에 merge된 코드와 동기화하는 작업을 진행해야 한다.**      
  
```
git remote add {저장소_별칭} base_저장소_url
```   
* ex) `git remote add upstream https://github.com/ssafy-java-racingcar.git`

위와 같이 next-step 저장소를 추가한 후   
아래와 같이 전체 remote 저장소 목록을 본다.
  
```git  
git remote -v
git remote add 명령은 최초 1회만 진행하면 된다.
add upstream
```
  
저장소에서 자기 브랜치 가져오기(또는 갱신하기)    
앞 단계의 remote add 명령은 로컬 PC에서 저장소에 접근할 수 있도록 이름을 부여한 것이다.      
앞 단계의 예제는 upstream이라는 이름을 부여했다.   
     
앞 단계에서 저장소에 이름을 부여했다면      
이번 단계는 fetch 명령으로 동기화하고 싶은 저장소의 브랜치를 가져오기 해야 한다.   

```git
git fetch upstream {본인_아이디}
```
* `ex) git fetch upstream kwj1270`  
     
`fetch` 명령을 실행한 후 `git branch -a` 명령을 실행하면    
`remotes/upstream/kwj1270`와 같은 브랜치가 생성된 것을 확인할 수 있다.   
       
저장소 브랜치와 동기화하기   
현재 상태는 저장소 브랜치를 가져오기는 했지만        
아직까지 로컬 저장소에 최신 버전의 코드가 반영된 것은 아니다.     
       
`rebase` 명령을 실행해 저장소와 로컬 저장소의 브랜치를 동기화한다.   

```git
git rebase upstream/본인_아이디
```  
     
* `ex) git rebase upstream/kwj1270`
       
## 새로운 미션을 진행하기 위한 브랜치 생성   
지금까지 과정을 통해 새로운 작업을 시작하기 위한 준비 작업을 마쳤다.  
다음 단계는 맨 위의 코드리뷰 요청 checkout 명령으로 새로운 브랜치를 생성한다.

```java
git checkout -b 브랜치이름
```
* ex) `git checkout -b step2`   
       
다음 단계를 진행하기 위한 모든 준비 작업은 마쳤다.   
지금부터 다음 단계에 도전하면 된다.      
다음 단계의 도전이 끝나면 코드리뷰 요청 단계를 반복하면 된다.     
온라인 코드리뷰를 통해 프로그래밍을 즐기는 개발자가 되기를 기대해 본다.   
     
# FAQ     
* PR에서 충돌이 발생하는데 어떻게 해결하면 좋을까요?   
* 저장소와 rebase를 하지 않은 상태에서 브랜치를 생성했더니 충돌이 발생하고 있다.       
* 충돌을 해결하려면 어떻게 해야 하나요?  

```
git checkout 본인_아이디(예: git checkout kwj1270) 명령을 실행해 계정 브랜치로 이동한다.
git reset --hard upstream/본인_아이디(예: git reset --hard upstream/kwj1270)
git checkout 기능_브랜치(예: git checkout step2)
git merge 본인_아이디(예: git merge kwj1270)
```    
위 명령을 실행하면 충돌이 발생할 것이다.      
충돌을 해결한 후 `add, commit, push`를 진행하면 `PR` 충돌이 해결되어 리뷰 요청을 할 수 있다.   
   
