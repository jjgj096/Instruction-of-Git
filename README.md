# Git/GitHub 학습하기
**URL** : [https://github.com/jjgj096/SE_YJH.git](https://github.com/jjgj096/SE_YJH.git)


## 1) Git과 GitHub란 무엇인가?

 * **Git** 
 
    소프트웨어 개발에서 소스코드를 효과적으로 관리할 수 있도록 하는 무료, 공개 소프트웨어.  
    분산형 **버전관리** 시스템으로, 컴퓨터 파일의 변경사항을 추적하고 관리해주는 시스템

* **GitHub** 

    git에서 진행되는 작업을 공유할 수 있는 **공간제공** 서비스(repository)

* **git과** **gitHub의** **관계** 

    Git이 **영상촬영** **앱**이라고 하면, GitHub는 영상을 저장하고 공유하는 **유튜브**라고 볼 수 있음.
    
 ## 2) Git 명령어
 
 이 파일은 오늘 진행할 가상 프로젝트를 수행하면서 쓰이는 중요한 **Git** **명령어**입니다.
 
 * [init](#init-명령어)
 * [config](#config-명령어)
 * [clone](#clone-명령어)
 * [add](#add-명령어)
 * [commit](#commit-명령어)
 * [push](#push-명령어)
 * [remote](#remote-명령어)
 * [status](#status-명령어)
 * [reset](#reset-명령어)
 * [checkout](#checkout-명령어)
 * [pull](#pull-명령어)
 * [log](#log-명령어)
 * [branch](#branch-명령어)
 * [merge](#merge-명령어)
 * [rebase](#rebase-명령어)
 * [tag](#tag-명령어)


## 3) 프로젝트 주제

이번 프로젝트는 Markdown을 사용한 Markdown 튜토리얼을 만드는 것입니다.

# 프로젝트 시작  

* ## GitHub repository 생성하기

![image](https://user-images.githubusercontent.com/81611401/117520852-67df6f80-afe5-11eb-8105-671d1986a602.png)


* ## init 명령어 
>$ git init

1. 관리하고 싶은 폴더를 만든 상태. (로컬 디스크 :C에 YJH 생성.)

2. 이 상태에서, git이 이 폴더를 관리할 수 있도록 빈 저장소를 만들고 싶음.

3. cd 명령어를 통해 해당 폴더로 이동 후, init 명령어를 통해 해결이 가능하다.

![image](https://user-images.githubusercontent.com/81611401/117520874-92c9c380-afe5-11eb-8c80-674b38fc9d6b.png)

4. 해당 명령어 실행 후, 디렉터리 파일에 .git 폴더가 생성된 것을 확인할 수 있다. 

   (숨김 파일 표시해야 보인다.) 이로써, Git을 통해 해당 폴더를 관리할 수 있다.

![image](https://user-images.githubusercontent.com/81611401/117520840-55653600-afe5-11eb-963c-048ef79a6925.png)



* ## config 명령어
>$ git config --global 설정이름 설정값

1. init 명령어를 통해, 디렉토리 폴더에 .git 폴더만 있는 상태.

2. git을 사용할 때, 사용자의 이름과 이메일주소를 등록하고 싶음. 

3. config 명령어를 통해 등록이 가능하다. (gitHub에 가입한 이름과 이메일주소와 동일하게 작성한다.)

![image](https://user-images.githubusercontent.com/81611401/117523813-39699080-aff5-11eb-9ee3-94e30e85f95f.png)

4. $ git config --list 라는 명령어를 사용하면 git의 설정을 볼 수 있다.

![image](https://user-images.githubusercontent.com/81611401/117530518-8ca10a80-b018-11eb-9ade-660a894136f3.png)
         
* ## clone 명령어
>$ git clone repository_link

1. 로컬 저장소와 원격 저장소인 gitHub repository가 연결되어 있지 않은 상태

2. 위의 상태에서, repository와 로컬 저장소를 연결하고 싶음.

3. clone 명령어를 사용하여 로컬 저장소에 복사본을 생성한다.

![image](https://user-images.githubusercontent.com/81611401/117523869-91a09280-aff5-11eb-803e-a512ed0f9411.png)

4. clone 명령어를 통해 디렉토리 폴더에는 SE_YJH라는 폴더가 생김을 확인할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117523888-b3017e80-aff5-11eb-879f-31375b9f0a6b.png)


* ## add 명령어
>$ git add 파일명

1. 원하는 프로젝트를 만들기 위해 디렉터리 파일이 변경 된 상태. 즉, 수정이 가해진 상태

![image](https://user-images.githubusercontent.com/81611401/117524002-71250800-aff6-11eb-8b55-b5dfa7730f69.png)

2. 변경된 디렉터리 파일을 로컬 저장소에 추가하고 싶음.

3. add 명령어를 통해 변경된 사항을 로컬 저장소에 추가할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117524022-9285f400-aff6-11eb-8a12-6bfa6f180609.png)

4. 이 에러는 맥을 쓰는 개발자와 윈도우를 쓰는 개발자가 git으로 협업할 때 발생하는 Whitespace 에러이다. 유닉스 시스템에서는 한 줄의 끝이 LF로 이루어지는 반면, 윈도우에서는 CRLF로 이루어지기 때문이다. 따라서 어느 쪽을 선택할지 git에게 혼란이 온 것이다. 이런 에러의 해결법은 간단하다. git의 "core.autocrlf" 라는 기능을 켜주는 것이다.  (명령어는 다음과 같다.) (필자는 실제로 맥과 윈도우를 사용.)
>$ git config --global core.autocrlf true


* ## commit 명령어
>$ git commit -m "commit message"

1. add 명령어를 통해 로컬 저장소에 변경 사항이 추가된 상태.

2. 소스코드나 문서의 내용을 수정했을 때, 수정내역을 기록하고 싶음.

3. commit 명령어를 통해 수정내역을 기록할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117524098-ff998980-aff6-11eb-97af-1c14eb3fabad.png)

4. 소스코드나 문서를 수정하였을 때, commit 명령어를 통해 수정내역을 기록하면 어느 지점에서 수정을 어떻게 했는지 파악하는데 큰 도움이 된다고 생각합니다. 

-m 옵션을 통해 "commit message" 에서 어떤 내용을 수정하였는지 기록할 수 있습니다.



* ## push 명령어
>$ git push

1. add, commit 명령어를 통해 파일을 추가하고, 수정내역을 기록한 상태. 아직 gitHub repository에는 파일이 없는 상태.

![image](https://user-images.githubusercontent.com/81611401/117524159-4edfba00-aff7-11eb-8962-98574b9b40e1.png)

2. 수정한 소스코드 또는 문서를 원격 저장소에 저장하고 싶음.

3. push 명령어를 통해 위의 상황을 해결할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117524185-6c148880-aff7-11eb-86eb-0e4cc682dc26.png)

>$ git remote add origin repository_link : 로컬 저장소와 원격 저장소를 연결해줌.
>
>$ git remote -v : 로컬 저장소와 연결된 원격 저장소를 모두 보여줌.
>
>$ git push origin master : master branch라는 원격 저장소에 push

4. push 명령어를 통해 수정한 소스코드 또는 문서가 원격 저장소에 있는 것을 볼 수 있음.

* ## status 명령어
>$ git status

1. 수정사항을 add 및 commit을 하지 않은 상태.

2. 현재 상태가 어떤지를 알고 싶음.

3. status 명령어를 통해 현재 파일의 상태가 어떤 상태인지 알 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117525084-b861c780-affb-11eb-8cf2-00b96327c713.png)

>20201866.md 파일의 수정사항이 add 및 commit 되지 않았음을 알려준다.

4. 이 상태에서 20201866.md 파일을 add 처리한다음, status 명령어를 사용하면 어떻게 될까?

![image](https://user-images.githubusercontent.com/81611401/117525182-fb239f80-affb-11eb-999e-ad4cc36828a4.png)

>20201866.md 파일의 수정사항이 add 처리 되었음을 알려준다.
>
>$ git add . : 모든 수정사항을 추가함을 의미하는 add 옵션.

* ## reset 명령어
>$ git reset

1. 위의 20201866.md 파일이 add 되어있는 상태.

2. 어떤 명령어를 사용해서 파일을 add 처리하기 전으로 돌아가고 싶음.(타임머신처럼)

3. reset 명령어를 통하여 특정 지점의 과거 커밋으로 이동할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117526158-2ad3a700-affe-11eb-95ae-deab17649696.png)

>reset 명령어를 통해 add 되어 있던 파일이 add 처리 되기 전 상태로 돌아간 것을 볼 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117526369-a08c4280-afff-11eb-9d90-686c6d4f873c.png)

>다시 add 및 commit, push를 통해 변경된 내용을 저장하면 원격 저장소 또한 내용이 수정된다.

* ## log 명령어
>$ git log 

1. 현재까지의 수정내역이 기억이 나지 않는 상태이고,

2. 파일 수정내역, 즉 커밋 히스토리를 알고 싶으면,

3. log 명령어를 통해 커밋 히스토리 로그를 알 수 있다.

![image](https://user-images.githubusercontent.com/81611401/117526440-29a37980-b000-11eb-8176-c995b9203865.png)

>노란색으로 표시되어 있는 문장은 해당 commit의 hash-value이다. 즉, 특정 커밋의 **주소값**이다.

### +) 여기서 reset --hard 명령어를 통해 특정 커밋으로 시간 여행을 할 수 있다.
>$ git reset hash-value --hard : 특정 커밋 이후의 시점이 모두 삭제된다.

(이 때, hash-value를 주소값 앞 6자리로 해도 무방하다.)

1. 위의 상태에서 두 번째 커밋으로 돌아가보겠다.

![image](https://user-images.githubusercontent.com/81611401/117526776-3de87600-b002-11eb-9738-51da7f72aac7.png)

> 두 번째 커밋 이후의 시점이 모두 삭제되었다는 것을 알 수 있다.

2. 이 상황에서 push를 하면 이와 같은 error가 발생한다. 

![image](https://user-images.githubusercontent.com/81611401/117526839-c7984380-b002-11eb-862b-a063c3f91b10.png)

3. 이 error는 $ git push -u origin +master 으로 해결한다.

![image](https://user-images.githubusercontent.com/81611401/117526914-147c1a00-b003-11eb-811f-98b3ca7bafa2.png)

> 이와 같이 해결 된 것을 볼 수 있고 더 분명하게 확인하고 싶으면 원격 저장소를 보면 된다.

![image](https://user-images.githubusercontent.com/81611401/117526952-37a6c980-b003-11eb-8121-000bc2a08b3b.png)

> 성공적으로 해결되었음을 확인한다.

* ## branch 명령어
>$ git branch option : git의 큰 장점 중 하나

1. 현재 branch는 master인 상태

2. branch를 추가함으로써 여러 개발자들이 동시에 다른 기능을 개발할 수 있도록 하고싶음.

3. branch 명령어를 통해 branch를 생성, 삭제, 조회, 변경 할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117527667-b8b48f80-b008-11eb-9080-933f21bd7442.png)

>$ git branch : 현재 HEAD를 조회
>
>* 되어 있는게 현재 내가 있는 branch이다.
>
>$ git branch name : name branch 생성
>
>$ git checkout name : HEAD를 name으로 변경
>
>위의 사진과 같이 debug branch가 생성되었고, checkout을 통해 HEAD가 바뀐 것을 확인할 수 있다.

4. 여러 개발 환경을 branch로 뻗어나가는 것은 git의 핵심이라 해도 과언이 아니라고 생각한다.

* ## merge 명령어
>$ git merge branch_name

![image](https://user-images.githubusercontent.com/81611401/117527774-75a6ec00-b009-11eb-8ec4-420de6c8c431.png)

1. 위의 branch 명령어로 인해, HEAD가 debug로 잡혀있고 commit이 debug에만 되어있는 상태이다.

2. 이 상황에서, 여러 브랜치를 한 HEAD에 묶고 싶음.

3. merge 명령어를 사용하여 이와 같은 문제 해결 가능.

![image](https://user-images.githubusercontent.com/81611401/117527847-e3ebae80-b009-11eb-8cd6-27a2badabd23.png)

>우선, checkout을 통해 HEAD를 master로 옮긴다.
>
>merge 명령어를 통해 debug branch의 내용을 master에 통합한다.
>
>결과: master와 debug branch가 한 HEAD에 묶여있는 것을 확인할 수 있다.

4. 하나의 branch에서 여러 branch로 뻗어나갈 때 merge 명령어를 통해 통합하는 것이 중요하다.

* ## rebase 명령어
>$ git rebase

1. 한 브랜치에서 다른 브랜치로 합치는 방법의 두 가지 중 하나. (다른 하나는 merge)

![image](https://user-images.githubusercontent.com/81611401/117530878-90359100-b01a-11eb-8a4e-028f7cf45aef.png)

2. rebase는 장점이 많지만 위험성이 많은 것 같다. 만약 이미 공개 저장소에 push한 커밋을 rebase한 경우에는 코드뿐만 아니라 협업 자체가 엉망이 되기 때문이다.

* ## tag 명령어
>$ git tag tag_name

1. 현재 HEAD에 tag를 달아서 가독성을 높이고 싶음.

2. tag 명령어를 사용하여 태그의 설정과 리스트를 확인할 수 있다.

![image](https://user-images.githubusercontent.com/81611401/117528210-ff57b900-b00b-11eb-8774-c2365e8f5917.png)

>HEAD에 tagtag이라는 tag가 붙은 것을 확인할 수 있다.


* ## checkout 명령어
>$ git checkout

1. 파일을 수정한 상태에서

2. 수정된 내용을 파일에 추가할지, 무시할지를 선택하고 싶음.

3. checkout 명령어를 통해 선택할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117528401-0206de00-b00d-11eb-8344-761ad2674a45.png)

>위의 사진과 같이 "checkout -> 체크아웃 문장입니다."를 작성한 상태에서 checkout 명령어 실행.

![image](https://user-images.githubusercontent.com/81611401/117528431-34184000-b00d-11eb-85d9-f31baafe3de6.png)

> add 및 commit이 되지 않은 파일이 checkout 명령어를 통해 checkout 문장 제거, push를 통해 확인해본다.

![image](https://user-images.githubusercontent.com/81611401/117528653-2dd69380-b00e-11eb-8cbd-b34341c0d0c7.png)

>checkout 수정내역이 버려진 것을 확인할 수 있다.

4. checkout 명령어를 통해 버려야하는 것을 빠르게 처리할 수 있는 이점이 있다는 것을 확인하였다.

* ## pull 명령어
>$ git pull

1. master branch에서 작업하는 상태

2. master branch에 해당하는 내용을 모두 가져오고 싶음

3. pull 명령어를 통해, 추적 중인 branch에 해당하는 정보를 가져올 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117529085-81e27780-b010-11eb-91ad-53092abfca7b.png)

>$ git pull repository_link branch : 원격 저장소에 등록된 최신 소스를 가져와 지정한 branch에 저장.

* ## remote 명령어
>$ git remote

1. 원격 저장소에 어떤 것이 등록되어 있는지 궁금한 상태이며 알고 싶음.

2. remote 명령어를 통해 어떤 것이 등록되어 있는지 확인할 수 있음.

![image](https://user-images.githubusercontent.com/81611401/117529140-e1408780-b010-11eb-9837-f0da25c22e0e.png)

>원격 저장소로 origin이 등록되어 있다는 것을 알려준다.

3. $ git remote show 저장소

![image](https://user-images.githubusercontent.com/81611401/117529172-1056f900-b011-11eb-9bea-d71457757167.png)

>해당 원격 저장소의 정보를 자세하게 확인할 수 있다.

4. remote 명령어는 해당 원격 저장소의 정보와 어떤 종류가 있는지 확인할 때 유용한 명령어임을 확인했다.

# 명령어 사용여부 확인표


명령어 | 사용 여부 | 링크
-------|----------|--------
init   |     O    |         
config |     O    |         
clone  |     O    |        
add    |     O    |       
commit |     O    |     
push   |     O    |
remote |     O    |
status |     O    |
reset  |     O    |
checkout|    O    |
pull   |     O    |
log    |     O    | 
branch |     O    |
merge  |     O    |
rebase |     O    |
tag    |     O    |
