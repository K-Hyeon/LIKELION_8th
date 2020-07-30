## 자주쓰는 Git 명령어
#### * git init : git 저장소를 초기화
#### * git add. : 폴더에 변경된 모든 파일 staging area에 올리기
#### * git commit -m "커밋에 대한 설명" : 유사시 돌아갈 수 있는 저장소의 체크 포인트 생성
#### * git remote add origin http://원격저장소주소.git : 원격 저장소(remote repository)와 로컬 저장소를 연결


##### Branch : 한 Repository 내에서 용도에 따라 저장소를 나누는 것 
######        (협업하는 개발자별 브랜치, 제품 출시 브랜치, 기능을 개발하는 브랜치 등)
#### * git branch 브랜치 명 : 새로운 브랜치를 생성
#### * git cheakout 브랜치 명 : 해당 브랜치로 이동
#### * git push origin 브랜치 : 원격 저장소의 특정 브랜치에 프로젝트 저장
#### * git pull origin 브랜치 : 원격 저장소의 특정 브랜치에서 변경사항 Pull 해오기
#### * git clone http://원격저장소주소.git : 원격 저장소에 있는 파일 전체 복사
#### * git status : git 저장소의 상태를 확인


## Github를 이용한 협업
#### 1. 원격 저장소 생성(Github repository 생성)
#### 2. 팀원을 Collaborator로 추가
####  : Settings → Manage access → Invite a collaborator 
#### 3. 초기 프로젝트 Push
#### 4. 팀원들의 로컬에 프로젝트 Pull
##### git clone http://원격저장소주소.git 활용
#### 5. 팀원들 각자의 브랜치를 생성하여 작업
##### git branch 이름
#### 6. 브랜치에 작업한 내용을 Push
###### git cheakout 이름
###### 코드 수정
###### Git add .
###### Git status : 수정내역 확인
###### git commit에 수정 내용 이름을 붙여줌
###### Git push origin 브랜치
###### 변경된 코드가 적용됨
###### Git Status
#### 7. Master와 merge 하기 전 pull request (전체 코드에 적용하기 전 팀원들이 확인)
##### pull request → new pull request → 마스터 브랜치(기존의 브랜치?)와 자기브랜치 차이점를 볼 수 있음
##### Create Pull Request
#### 8. Pull request 확인 후 Master와 merge
##### 팀장이 Pull request 확인 후 승인
##### Merge pull request → confirm merge (확인)
##### Repository master commit이 변경사항이 적용된걸 확인

## Fork를 이용한 협업
#### 1. 작업하고 싶은 Repository fork 해오기
##### Reposotory 오른쪽 위의 fork 버튼
#### 2. 자신의 로컬에서 작업
###### cd fork 
###### git clone url
###### code .
######  비주얼 코드에서 코드 수정
##### git status (수정 사항 확인 가능)
#### 3. 변경사항을 자신의 브랜치에 Push
###### git add . (변경사항 저장)
###### git commit -m "id change" 
###### git checkout -b 저장하고자하는 이름 
###### git push origin 저장하고자하는 이름 
#### 4. 원본 레포지토리 소유자에게 Pull request 요청
#### 5. 소유자가 pull request를 승인하여 merge하면 자동으로 collaborator 추가
