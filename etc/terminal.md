# Terminal Command (git)

```zsh
pwd #현재 디렉토리까지 경로 출력

cd <foldername>     #디렉토리 이동
cd ..     #상위 디렉토리 이동
cd ~      #홈 디렉토리 이동

touch <filename>      #파일 생성
rm <filename>     #파일 삭제

mkdir <dirname>     #디렉토리 생성
rmdir <dirname>     #디렉토리 삭제 [비어있는 폴더]
rm -rf <dirname>      #디렉토리 포함 내부 파일 전체 삭제

cat <filename>      #파일 내용보기

ls      #현재 경로의 파일 및 디렉토리 조회
ls -a     #현재 경로의 숨김파일 및 디렉토리 포함 조회
ls -al      #숨김파일 및 디렉토리 포함 리스트 출력

vi <filename>     #파일 접근
        #a (입력모드)
        #i (입력모드)
        #ESC (입력모드 나가기)
        #:w (저장)
        #:q (닫기)
        #:wq (저장 및 닫기)
```

git 사용자 설정 git config —global user.name “<username>” git config —global user.email <useremail>

git init git status git add git commit
