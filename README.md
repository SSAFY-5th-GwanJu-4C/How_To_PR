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
  
# IntelliJ를 시작   
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
   
