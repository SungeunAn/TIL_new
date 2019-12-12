## cmd 명령어

* `>` : redirection

* `bcdboot F:\windows` : F:의 windows 파일에 boot파일 생성
* `dir` : 현재 디렉토리 내 파일 목록 보기



## 클라우드 서비스

* **대표적 벤더** : 아마존, MS Azure, 구글
  이 중 아마존과 구글은 Public 서비스만 제공하며, MS Azure는 Public과 Private 서비스 모두 제공한다.
* **정의** : 네트워크를 활용하는 모든 서비스
* **조건**
  1. Scalable/Elastic : 사용자 수에 따라 확장/축소가 가능해야 한다.
  2. Service : 서비스를 기반으로 한다.
  3. Internet Tech : 인터넷 기술을 기반으로 한다.
* **특징**
  1. 자신이 원하는 서비스를 만들어서 사용한다.
  2. 네트워크를 통해 사용한다.
  3. 데이터 센터의 리소스들이 풀링되어 있다.
     * 리소스 : Server, Network, Storage
     * 풀링 : 가상화를 통해 각각의 서버를 하나로 추상화 하는 것
  4. On-premise 환경보다 운영관리 비용이 저렴하다.
     * On-premise : IT 분야를 직접 개발/운영하여 cloud와는 상반되는 개념
* **종류**
  1. Public : 벤더들이 글로벌하게 활용하는 클라우드 서비스
  2. Private : 한 회사 내에서 활용하는 클라우드 서비스
  3. Hybrid : Public과 Private를 필요에 따라 구분해 활용



## IT 환경의 변화

* **변천 과정** : 메인 프레임 > PC, 클라이언트 서버 > 웹 > 클라우드
* **역할** : 소통과 협업의 매개
* **패러다임의 변화** : 각자 IT 서비스를 개발하기 보다는 전문 기업에서 개발한 IT 서비스를 가져다 쓰는 방향으로 변화하고 있다.

| 기존 | 물질 | 소유 | 독점 |
| :--: | :--: | :--: | :--: |
| 현재 | 의미 | 사용 | 공유 |



## 가상화 머신

* **가상화 머신(VM, Virtual Machine)** : Hyper-V 환경에 설치된 os
* **Host os** : H/W에 직접 설치된 os
* **VHD 부팅** : 본래 한 H/W에는 하나의 os가 고정되어 있으나, 가상화로 이를 해제하여 VM을 Host os로 구현하는 것을 말한다.
* **TCP/IP** : 장비들끼리 통신하기 위한 통신규약(protocol)의 일종으로, 모든 os에 기본적으로 탑재되어 있다.
  4가지 값(IP, Subnet Mask, Gateway, DNS) 값을 설정해줘야 한다.
  1. Dynamic Configuration : 4가지 값을 자동으로 구성, IP를 DHCP 서버에서 자동으로 받아와 유동적이다.
     Client os에 적용된다.
  2. Static Configuration : 4가지 값을 수동으로 부여한다.
     Server os에 적용된다.
     * Server os : 서버 H/W에 os 설치해서 CPU, RAM, HDD, LAN 등을 인식할 수 있게 한 것을 뜻한다.
* UNC 경로 : 네트워크 공유 폴더 접근 시 사용하는 경로의 이름
  1. \\\컴퓨터이름\공유이름
  2. \\\IP주소\공유이름
  3. \\\DNS\공유이름