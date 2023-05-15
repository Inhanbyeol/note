# Terminal Command

### Print Working Directory

- 현재 디렉토리까지 경로 출력

```console
pwd
```

<br>

### Change Directory

- 디렉토리 이동

```console
cd <dirname>
```

- 상위 디렉토리 이동

```console
cd ..
```

- 홈 디렉토리 이동

```console
cd ~
```

<br>

### Create

- 파일 생성

```console
touch <filename>
```

- 디렉토리 생성

```console
mkdir <dirname>
```

<br>

### REMOVE

- 파일 삭제

```console
rm <filename>
```

- 디렉토리 포함 내부 파일 전체 삭제

```console
rm -rf <dirname>
```

- 디렉토리 삭제 [비어있는 폴더]

```console
rmdir <dirname>
```

<br>

### Concatenate

- 파일 내용보기

```console
cat <filename>
```

<br>

### List

- 현재 경로의 파일 및 디렉토리 조회

```console
ls
```

- 현재 경로의 숨김파일 및 디렉토리 포함 조회

```console
ls -a
```

- 숨김파일 및 디렉토리 포함 리스트 출력

```console
ls -al
```

<br>

### Vi

- 문서 편집

```console
vi <filename>
        #a (입력모드)
        #i (입력모드)
        #ESC (입력모드 나가기)
        #:w (저장)
        #:q (닫기)
        #:wq (저장 및 닫기)
```
