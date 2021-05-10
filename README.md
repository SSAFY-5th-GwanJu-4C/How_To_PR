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
        
github 서비스에서 pull request를 보낸다.       
pull request는 github에서 제공하는 기능으로 코드리뷰 요청을 보낼 때 사용한다.     
      
pull request는 original 저장소의 브랜치(자신의 github 아이디)와      
앞 단계에서 생성한 브랜치 이름(앞 단계의 예에서는 step1)을 기준으로 한다.     
      
즉, 각자의 아이디에 맞게끔 Pr 을 날리면 된다.      
   
```
kwj1270 <= step1 
```
    
## 작업 설명 (브라우저에서)  
브라우저에서 github 저장소에 접근한다.
브랜치를 작업 브랜치로 변경한다(앞 단계의 예에서는 step1).
브랜치 오른쪽에 있는 `New pull request` 버튼을 클릭한다.
              
**pull request 보내기**        
1. 저장소의 브랜치를 자신의 github 계정 브랜치로 변경한다.
2. 현재 미션에서 작업한 내용을 입력하고 "Create pull request" 버튼을 클릭해 pull request를 보낸다.
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
 

