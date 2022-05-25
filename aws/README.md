ec2에

AMAZON LiNUX2 로 apache web server-> tomcat으로 서버 구성하기

원하는데로 aws에서 인스턴스 구성후 ssh로 접속(putty 등)

centos 사용

아파치 설치
sudo yum install httpd

sudo yum install httpd-devel  // 아파치, 톰캣 연동시 mod_jk 사용하려면 설치

아파치 설정 파일은 /etc/httpd 아래에 있음

sudo service httpd start 로 실행후 public ip로 접속해보면 아파치 테스트화면이 뜨면 아파치 설치 성공
