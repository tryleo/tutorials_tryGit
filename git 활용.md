Git 사용법 (새 계정)


(출처) https://www.youtube.com/playlist?list=PLuHgQVnccGMCB06JE7zFIAOJtdcZBVrap
(날짜) 2016년 11월 25일
(위치) ~/dev/tutorials/mygitb
(Git) 계정, tryleo를 만들었음



git은 협업과 버전관리 도구이다.
github는 git의 버전을 저장해 주는 원격 관리소이다. 

협업: git과 github를 연결하여 여러 사람이 공동작업할 때는 개별 작업자는 git에서 다음의 순서를 지켜야 한다. 
일단, 작업 시작 시에는 협업자가 변경한 것이 있을 수 있으므로 먼저 pull하는 습관을 들이는 것이 좋다. 

다음 순서는 대단히 중요하다: 
pull -> work -> commit -> pull -> push

.pull: 일단, 원격에서 받아옴
.work: 로컬에서 작업을 수행
.commit: 작업을 로컬에 commit해서 버전을 만듬
.pull: 내가 작업하는 동안 협업자가 그동안 작업해서 원격에 변경이 있을 수 있으므로 다시 당겨옴. 내가 작업한 것과 당겨온 것을 병합하여 검토 후에 올려야 함.  
.push: 검토 결과를 다시 올림


여기서 저장소(repository), 원격저장소(remote repository), commit(작업한 것을 버전으로 반영), push(로컬->원격), pull(원격->로컬) 등의 용어 이해 필요함. 

자주 원격 저장소와 동기화해야 conflict 상황을 줄일 수 있다. 
같은 파일을 수정할 때는 conflict가 생겼다면 commit을 나중에 한 사람이 해결할 책임을 진다. 따라서, 협업 시에는 먼저, 자주 하는 것이 요구된다. 




되돌리기 4: Reset
여러번 commit했는데 중간쯤으로 되돌아가고 그 이후 작업은 무시하고 싶을 때,
임의 버전 위치의  마우스 클릭->Reset current branch to this commit->Hard discard all working 선택
그러면 뒤에 이루어진 commit는 모두 제거됨.

파일 수정과 파일 저장까지 했을 때, commit하기 직전에 수정한 것을 취소하려 하면, 
File status->Unstaged file->Discard file 선택

어떤 버전에 포커스를 두고 Reset current branch to this commit->Mixed~~를 선택하면 포커스 이후의 커밋을 제거하고 커밋의 마지막 상태만 언커밋 수정된 후, 언커밋 상태로 만들어 줌



되돌리기 5: Revert
Revert는 Reverse Commit로 커밋을 뒤돌아 가면서 차례로 제거할 수 있다. 그런데, 위 Reset은 아예 제거해 버리지만 혹시 나중에라도 사용할 가능성을 생각해서 제거 않고 남겨 놓는다:
버전 포커스 -> Reverse commit 

리버터를 하면 한 것도 하나의 버전처럼 쌓여 간다. 그리고, 하나씩 커밋의 역순으로 순차적으로 해야 한다. 


브렌치 2: 만들기
브렌치마크->뉴브렌치->”브렌치 name”->Specified commit->Pick->Create branch




원격저장소 3 : 원격 저장소 만들기
(출처) https://www.youtube.com/watch?v=YQHZ09_NShM&list=PLuHgQVnccGMCB06JE7zFIAOJtdcZBVrap&index=19

github를 원격 저장소로 선택하였다. 
id/ps를 tryleo/1******k로 함.  tofuny@네이버메일과 연결. 

.앞으로 github로 PUSH할 것은 tutorials_xxx의 네이밍으로 한다. 지금은 git 자체를 연습하므로 tutorials_git으로 하였다.
.푸쉬되는 파일명은 tryXXX.py로 한다. 따라서, 처음 올린 파일 명은 trySeaborn.py로 하였다. 

(위치) 내 컴의 작업 위치도 일관성을 기하기 위해 ~/dev/tutorials로 하고, 이 밑에 mygita, mygitb, mygitc의 3개의 폴더를 만들었다. 네이밍도 my(project name)(a)으로 하는 것이 어떨까 한다. 
(git) tutorials Group을 생성하고 이 그룹 밑에 git_a, git_b, git_c로 세개의 local repository를 만들었다.   네이밍은 위와 일치되게 (project name)_(a)

.폴더 ~/dev/tutorials/mygitc에 trySeaborn.py을 복사 후, 첫 커밋을 하고, 일부 수정 후, 재 커밋을 하였다. 
.Settings->Remote->Add에 들어가서 github에서 생성한 계정의 url을 넣었다. remote name: origin, url: 복사한 카피, 나머지는 공란으로 두고 OK.
.이렇게 하면 메인페이지->REMOTE에 origin이 생긴다. 이제 push로 올리면 된다. 
.PUSH를 누르고, id, ps를 넣으면 원격 저장소에 올라간다. github에 들어가서 확인해 보면, 마지막 수정(커밋)한 trySeaborn.py가 보인다. 화면 상단에 commits에 2회라고 보이는데 로컬에서 2번 커밋했기 떄문이다. 들어가서 확인해 보면 수정된 history를 확인할 수 있다. 간단한 설명문 추가도 여기서 가능하다. 

.로컬에서 branch를 만들어 추가로 푸쉬하였다. github에 2개의 브렌치가 생성되고 각각의 브렌치를 선택하여 확인 가능. 각 브렌치마다 커밋한 것이 달라져 있음. 

 




 






