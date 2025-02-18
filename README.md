
# ELK STACK 모니터링 시스템 구축 

# 구성 목표 

Git action / Ansible 을 이용하여 ELK Stack 을 구축 하는 것을 목적으로 한다.

Elastic Search / Logstash / Kibana / Filebeat 사용 예정

# 구성 순서도 

1. GitHub Actions 설정

● .github/workflows/gitaction-check.yaml에서 GitHub Actions 설정

● inventory.ini에서 대상 서버의 Ansible 인벤토리 설정

● GitHub Actions 실행 시 Self-Hosted Runner를 이용하여 가상 서버와 연결

● Ansible 플레이북 구성

2. playbook/elasticsearch.yml: Elasticsearch 설치 및 설정

●playbook/kibana.yml: Kibana 설치 및 설정

●playbook/logstash.yml: Logstash 및 Filebeat 설치 및 설정

●Nginx 웹 서버 배포 및 로그 수집 설정 포함

3. 서버 연결 및 배포

●Ansible을 통해 각 서비스 배포 시 SSH 연결 사용

●Ansible 전용 계정(ansible)을 활용하여 원격 서버에 접근

●방화벽 및 디렉토리 설정


4. 각 서비스에 필요한 방화벽 규칙 추가

●Elasticsearch, Logstash, Kibana 관련 디렉토리 생성 및 권한 설정 포함

●로그 수집 및 확인

5. 웹 서버(Nginx) 로그를 Logstash로 전송

●Logstash에서 Elasticsearch로 로그 전달

●Kibana를 통해 수집된 웹 서버 로그 시각화 및 확인

●결과 검증

●웹 서버(Nginx)에 접속하여 로그가 정상적으로 수집되는지 확인

●Kibana에서 Logstash를 통해 수집된 웹 서버 접근 로그 조회


#주의사항

#각각의 연결은 SSH 연결을 사용하며, 이때 ansible은 ansible 계정을 사용하기 이 문제를 주의할 필요가 있다.

#각 서비스의 배포 파일에는 서비스에 대한 방화벽 설정을 열어줘야 하며, 각 서비스에 필요한 디렉토리를 만드는 명령어가 yml 파일안에 있어야 하는 경우도 있음


# 결과

아래와 같이 본인 PC로 웹서버 (Logstash-Nginx) 서버에 접근할 경우 kibana에서 해당 LOG를 확인하여 WEB서버에 대한 접근을 확인할 수 있었다.


![image](https://github.com/user-attachments/assets/8e7fb332-6924-4714-a349-3c2c36d0a625)
