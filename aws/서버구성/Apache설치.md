## Apache 서버 설치하기

centos 사용

- AWS 접속 후 aws에서 인스턴스 구성을 완료하고 ssh로 접속(putty 등)

> 아파치 설치 
> sudo yum install httpd

> sudo yum install httpd-devel // 아파치, 톰캣 연동시 mod_jk 사용하려면 설치

아파치 설정 파일은 /etc/httpd 아래에 있음

> sudo service httpd start 로 실행후 public ip로 접속해보면 아파치 테스트화면이 뜨면 아파치 설치 성공
