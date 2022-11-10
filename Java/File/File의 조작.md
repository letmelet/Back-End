
 

## File의 이동

### A위치에서 B위치로 이동하기
> String path = "C:\\A\\test.txt"; </br>
> File file = new File(path); </br>
>
> String newPath = "C:\\B\\test.txt"; </br>
> File newFile = new File(newPath); </br>
> file.renameTo(newFile); </br>
> // 만약 해당 위치에 같은 파일이 존재한다면 아무것도 하지않음.

### JAVA7 이상 Path, Files 사용 시
> Path oldPath = Paths.get("C:\\A\\test.txt"); </br>
> Path newPath = Paths.get("C:\\B\\test.txt"); </br>
> Files.move(oldPath, newPath); </br>

## File의 삭제
 
> String path = "C:\\A\\test.txt"; </br>
> File file = new File(path); </br>
>
> if(file.exists()) { </br>
> file.delete(); </br>
> } </br>

## File의 이름 변경

> String path = "C:\\A\\test.txt"; </br>
> File file = new File(path); </br>
> 
> String newPath = "C"\\A\\test2.txt"; </br>
> File newFile = new File(newPath); </br>
> file.renameTo(newFile); </br>
