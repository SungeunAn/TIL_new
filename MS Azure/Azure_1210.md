## Azure

* **Shell** : 사용자로부터 명령을 받아 그것을 해석하고 실행하는 역할을 수행한다.

* **Cloud Shell** : Azure 포탈에서 사용할 수 있는 Shell (PowerShell/Bash)
  대량 작업 시 편리하다.

* **PowerShell** : Windows에서 사용 가능한 쉘로, 명령어('동사' + '-' + '명사'로 구성)가 길고 복잡하다.

  * get-command : 모든 명령어 출력
  * get-process : 작업관리자 내용을 출력
  * Azure를 Widows PowerShell에서 활용하기 위해서는 Az 모듈을 설치해야 한다.

* **PowerShell ISE** : PowerShell 명령을 스크립트화 할 수 있다.

* **PowerShell Module** : PowerShell 명령어들의 집합

* **Azure CLI** : Windows, MAC, LINUX에서 사용 가능한 쉘로, 명령어가 짧고 단순하다.

  ------------

* **Azure VNet(Virtual Network)** : 사설 IP를 기본으로 사용하며, 공인 IP를 사용하기 위해서는 해당 IP를 구매해야 한다.

* **Subnet Mask** : <u>29Bit 이하로</u> 설정
  X.X.X.0/24 VNet에서 호스트 1~3번 IP는 Azure에서 사용되는(예약된) IP이다. > 4~254까지만 할당 가능하며, Subnet Mask를 30Bit로 설정하면 Host 수가 최대 2개만 남으므로 29Bit 이하로 설정해야 한다.
  ![image-20191210152810584](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191210152810584.png)

  * Network Security Group : 방화벽 설정
  * MS-SQL : 1433 포트 / RDP : 3389 포트 / Web Service, http : 80번 포트 / https : 443 포트

----

* **Azure Load Balancer(L4)**`10979-5 p.9~`  : 부하를 분산시켜주는 장치
  특정 포트(주로 80 또는 443 포트)로 들어오는 패킷을 여러 VM으로 분산시켜준다.

  * Fronted IP Configuration : Client가 접속하는 IP
  * Backend Pool : 부하를 분산처리하는 Pool
  * Probe : Backend VM의 정상 작동 여부 판단
  * NAT Rule : 사설 IP를 공인 IP로 변환해 내보내기 위해 설정

  ![image-20191210154550131](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191210154550131.png)

  ![image-20191210155001716](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191210155001716.png)

* **Application Gateway(L7)**

---

* **VPN(Virtual Private Network)** : 외부와 내부 네트워크의 통로를 만들어서(터널링) 외부에서도 내부 네트워크에 접속할 수 있게 해준다.

* **터널링 기술의 종류**(하위로 갈수록 향상된 버전)

  * PPTP : 현재 안쓰임
  * L2TP/IPSec
  * SSTP : TCP 443 포트(SSL)만 열어주면 됨
  * IKEv2 : 세션을 서버에서 자동으로 접속해서 세션이 중간에 끊겨도 자동으로 연결됨

* **VPN의 종류** `중요!!`

  * P2S(Point to Site) : 컴퓨터 한 대가 네트워크에 접속
  * S2S(Site to Site) : 라우터 단에서 두 네트워크를 VPN을 통해 연결해 하나의 네트워크처럼 활용(예 - 본사, 지사 간 네트워크 연결)
    사용자 단에서 VPN 연결 할 필요가 없음
  * VNet2VNet : VNet과 VNet을 연결
    `VNet peering : 동일한 데이터 센터 내에 있는 VNet을 연결하는 것`
  * Express Route : 일반 라우터를 활용하지 않고 전용선을 통해 연결 > 속도가 매우 빠르다.

  ![image-20191210162640665](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191210162640665.png)

---

* **VM Availability** `중요!!` `10979-3 p.10` : 문제가 발생하더라도 서비스 유지할 수 있도록 하는 것
* **Availability Zone** : 데이터 센터를 복제해 문제 상황에 대비
  SLA(Service Level Agreement, 서비스 유지율) = 99.99%(1년에 약 5분 이하 서비스 중지 허용)
* **Availability Set** : 동일한 데이터 센터 내 Rack 단위로 복제해 문제 상황에 대비
  SLA = 99.95%
  Fault Domain : 복제해둘 Rack 개수
  Update Domain : 복제해둘 VM 개수
* Availability 구성하지 않은 Standalone VM의 SLA = 99.9%