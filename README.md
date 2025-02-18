
# ELK STACK 구성 

# 실습 계획안 

Git action / Ansible 을 이용하여 ELK Stack 을 구축 하는 것을 목적으로 한다.
Elastic Search / Logstash / Kibana / Filebeat 사용 예정

git action 구성 / (가상서버를 사용할 예정이기에) Self-Hosted Runner을 사용하여 가상서버와 연결

ansible을 이용하여 Nginx 웹서버,Logstash, kiabana 배포 및 웹서버에 대한 로그 수집

#Gitaction 관련 설정 YML파일 위치 - .github/workflows gitaction-check.yaml/inventory.ini 참조

#Ansibl 배포 관련 설정 YML파일 위치 - playbook elasticsearch.yml/kibana.yml/logstash.yml 참조

#주의사항

#각각의 연결은 SSH 연결을 사용하며, 이때 ansible은 ansible 계정을 사용하기 이 문제를 주의할 필요가 있다.

#각 서비스의 배포 파일에는 서비스에 대한 방화벽 설정을 열어줘야 하며, 각 서비스에 필요한 디렉토리를 만드는 명령어가 yml 파일안에 있어야 하는 경우도 있음


# 결과
아래와 같이 본인 PC로 웹서버 (Logstash-Nginx) 서버에 접근할 경우 kibana 웹 UI를 통해 해당 접근에 대해 확인할 수 있었다.


![image](https://github.com/user-attachments/assets/8e7fb332-6924-4714-a349-3c2c36d0a625)
