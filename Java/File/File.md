
## JAVA의 FILE


### FILE 객체 생성하기 

1. FILE의 경로변수 생성 : 경로가 어디까지냐에 따라 파일또는 디렉토리로 사용가능

> String path = "C:\\TEST\\fileTest.txt";  // 파일  </br> 
> String path = "C:\\Test";  // 디렉토리

2. FILE의 객체 생성하기

> File file = new File(path);  


### File의 메서드 (directory 포함)

- file.exists() : 파일이 존재하는가? 
- file.isFile() : 파일인가?
- file.isDirectory() : 디렉토리인가?
- file.isHidden() : 숨김파일인가?
- file.getName() : 파일의 이름 가져오기
- file.lastModified() : 파일의 수정된 날짜
- file.canRead() : 읽기가능 파일인가?
- file.canWrite() : 쓰기가능 파일인가?
- file.length() : 파일의 크기
- file.getPath() : 파일의 상대경로
- file.getAbsolutePath() : 파일의 절대경로
- file.canExecute() : 접근가능한 파일인가?

