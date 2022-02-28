## TEST Title(ver. 1)
### Git 명령어

    1. git 초기화 
        $ git init
    2. status 확인
        $ git status
    3. config 목록 확인
        $ git config --list
    4. github의 username과 email 설정
        $ git config --global user.name  각자의username
        $ git config user.name

        $ git config --global user.email  각자의email
        $ git config user.email

    5. git add 
        $ git status 
        Untracked files:  README.md, index.html
        $ git add README.md
            untracked 상태의 파일을 staging area 로 정보를 기록함
            Changes to be committed:
                new file:   README.md
            Untracked files:
                index.html
        $ git rm --cached README.md
            staging area 있던 파일 정보를 untracked 상태로 변경하기
            Untracked files:  README.md, index.html

    6. git commit
        $ git commit -m '프로젝트설명파일추가'

        commit history 확인
        $ git log
        $ git log --oneline
        $ git log --pretty=format:"%H is by %an"

    7. git push
        원격저장소 url 설정
            $ git remote add origin https://github.com/myvega-2k/MyApp.git
        원격저장소 설정 확인
            $ git config remote.origin.url

        원격저장소에 업로드하기
            $ git push origin master

    8. 403오류(권한없음)가 발생하는 경우
        username과 email  설정초기화 
            $ git config --global --unset user.name
            $ git config --global --unset user.email

        인증 username과 email  설정
            $ git config credential.username myvega-2k
            $ git config credential.useremail vega2k_@daum.net

        username과 email  설정
            $ git config --global user.name myvega-2k
            $ git config --global user.email vega2k_@daum.net

    9. git clone
        $ git clone https://github.com/myvega-2k/MyApp .

    10. git pull
        $ git pull origin master 

## 파일의 4가지 상태
    
    1.untracked
    2. tracked : unmodified, modified, staged 

    tracked.txt 과 untracked.txt  2개의 파일을 생성
    tracked.txt 파일을 수정 add, commit
    tracked.txt 다시 수정하기
    push 을 한다면?? 바로 수정한 내용이 반영되지 않음
        $ git status
    modified:   tracked.txt

    modified 상태인 파일을 최신 커밋 버전으로 되돌리기
        $ git checkout -- tracked.txt
