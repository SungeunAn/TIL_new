## 시험 문제:1st_place_medal:

* 클라우드 서비스 :  네트워크를 통해 받는 모든 서비스
  웹 브라우저(IE, 크롬, ...)를 통해 클라우드 서비스를 받는다.
* 클라우드의 종류 : Public / Private / Hybrid 
  대표적 Public 벤더 : 아마존, MS, 구글
* 클라우드 컴퓨팅의 특징
  * 리소스가 가상화를 통해 풀링되어 있다 > 확장/축소 용이(Scalable/Elastic)
  * 자신이 원하는 서비스를 만들어서 사용(On-Demand Self Service)
  * 네트워크를 통해서 사용(Broad Network Access)
  * On-premise 환경보다 운영/관리 비용이 저렴
* 클라우드 서비스 모델의 종류
  * IaaS : 네트워크/서버/스토리지 장비 등 인프라 제공 (예 - Azure VM, VM에 SQL 기본으로 깔려있는 경우)
  * PaaS : Runtime까지의 개발환경까지 제공 (예 - Azure Web App, Azure DB Service)
  * SaaS : 완성된 클라우드 서비스를 제공 
    ![image-20191213095235162](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191213095235162.png)

* SLA : 서비스 가용 시간 비율
  * Azure Availability Zone
    SLA 99.99%,데이터 센터 단위로 복제
  * Azure Availability Set
    SLA 99.95%, 동일한 데이터 센터 내 렉 단위로 복제 
* 사설 IP 대역
  ![image-20191213102013456](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191213102013456.png)
  공인 IP도 사용 가능하나 해당 IP를 구매해야 하기 떄문에 잘 사용되지 않음
* DNS : 기본적으로 Azure에서 긴 DNS 이름을 매칭시켜 주지만, custom domain을 통해 원하는 DNS 명으로 변경 가능하다.
* VPN 터널링 기술의 종류
  * PPTP : 보안 문제로 사용 안함
  *  L2TP : 암호화 X > IPSEC과 연동해 암호하
  * SSTP : TCP 443 포트 활용해 자동으로 암호화
  * IKEv2 : 자동으로 암호화, 서버에서 자동으로 VPN 연결을 해주기 때문에 자주 끊기는 환경에 유리
* VPN의 종류
* 호스트 수 계산
* ping 해서 응답을 받기 위해서는 ICMP 프로토콜을 열어줘야 한다.
* wf.msc : 방화벽 설정 열기
* netstat -na : 현재 어떤 컴퓨터와 연결되어 있는지, 어떤 포트가 열려있는지 알 수 있음
* ipconfig /all : TCP/IP 확인
* ipconfig /displaydns : dns 정보 출력
* ipconfig /flushdns : dns 정보 삭제
* 포트 종류
  * Web Server : TCP 80
  * SQL : TCP 1433
  * RDP : TCP  3389
  * SSH(명령어를 통한 암호화 원격 관리) : TCP 22
  * SMB 3.0(고유폴더 설정) : TCP 445
* PowerShell/Azure CLI에서 Azure 관리 설정 순서
  1. Az 모듈/Azure CLI 설치
  2. Azure 계정 연결(로그인)
  3. Azure Subscription 확인
  4. Azure Subscription 선택
* NAT : Network Address Translation
  사설 IP에서도 네트워크 접근 가능하도록 공인 IP로 주소를 변환해 주는 것
* Load Balancer(L4) : 부하 분산 처리 기능
  한 데이터 센터 내 부하만 분산처리 가능
  다른 지역 간 부하 분산처리는 L7 단계
  * Probe : 각 분산 처리 장치의 건강상태 체크
* 인증(Authentication) : 인증 정보(Credential, ID & PW) 확인
* 허가(Authorization) : 인증된 사용자에게 권한을 부여하는 것
* Token : 인증된 사용자의 SID(고유 번호)가 할당되어 있음



## AAD

* Group : 여러 계정의 권한을 한 번에 관리하기 위해 묶어주는 것



## DNS

* DNS 설정 시 Storage는 IP로 매핑이 안된다.



## ACS (Azure Container Service)

### Docker

* 로컬의 개발 환경을 하나도 묶어서 다른 개발 환경으로 옮기더라도 동일하게 작동하도록 하는 기술
* H/W 위에 바로 Docker 엔진이 올라가 빠르게 실행 가능하다.
* 향후 상대적으로 용량이 큰 VM보다 Docker 개발 환경으로 전이될 전망
  ![image-20191213143305714](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191213143305714.png)
* 용어 :1st_place_medal:
  * Container = Docker
    Container는 메모리에서 실행중인 Docker
  * Docker Image : 실행 전 상태의 Docker
  * Dockerfile : 로컬에 저장되어 있으나 실행 전 상태의 Docker 파일
  * Docker Engine : Container를 실행시킬 수 있게 해주는 엔진
  * Docker Registry : Docker 이미지(Docker 실행 전 상태)를 저장하고 있는 저장소
    * [Public Registry](https://hub.docker.com/) : 모든 사람이 접근 가능 
    * Private Registry : 특정 사용자만 접근 가능

* docker-compose.yml 파일 : 실행 명령을 스크립트로 작성해서 다수의 Container 실행 자동화
* 명령어
  * docker login : docker registry에 로그인
  * docker pull : registry의 docker 이미지 내려받기
  * docker tag : 이미지 버전 정보
  * docker push : docker 파일 업로드
  * docker run : docker 다운 + container에서 실행
  * docker rmi :2nd_place_medal: : docker 이미지 삭제
  * docker rm :2nd_place_medal: : container 삭제
  * docker ps : docker 작동 여부 확인



## AKS (Azure Kubernetes Service)

* Container를 복사하거나 삭제해서 사용자 수요에 맞게 Ochestration(분산 처리) 하는 서비스
* VM보다 빠르게 조절 가능하다는 장점이 있다.
* 클러스터 : 여러 서버를 그루핑해서 하나의 서버에서 오류가 나더라도 다른 서버가 이를 대신해주도록 하는 것