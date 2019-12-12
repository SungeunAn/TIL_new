## 기타

* net use `중요!!` : 공유 폴더를 디스크에 할당

```bash
net use x: \\70.12.113.130\PPTShare
```

* MFA : 다단계 인증



## Azure

### AAD (Azure Active Directory)

* MS의 Directory 서비스
  X.500 : Directory 서비스의 표준
  * Domain : Directory 서비스가 작동하는 범위로, 하나의 보안 단위이다.
    * SSO(Single Sign On) & 관리 중앙화(GPO) : DC(Domain Controller)에서 여러 물리적 컴퓨터를 그루핑해 인증(ID & PW) 및 허가(권한 범위) 설정 공유
    * 동일한 Domain 내 컴퓨터 끼리는 인증이 필요치 않음
    * 중/대규모 네트워크 환경에서 사용
  * Work Group : 각 시스템의 보안 단위로 Domain과 상반되는 개념이다.
    * 소규모 네트워크 환경에서 사용(20대 미만)
    * 각자의 시스템에서 인증 처리
* Global Administrator : Azure와 MS 모든 서비스에 대한 권한을 가지는 directory role
* Subscription은 하나의 Directory에만 적용 가능하나, 하나의 Directory에는 여러 개의 Subscription을 적용할 수 있다.

#### Service Types

* AD DS (Active Directory Domain Service) : 가장 기본이 되는 서비스
  AD DS를 통해 DC 생성

* AD LDS (Active Directory Lightweight Domain Service)

* AD CS (Active Directory Certification Service) : 인증서 배포

* AD RMS (Active Directory Right Management Service)

* AD FS (Active Directory Federation Service) : A Domain 내에서 B Domain 내에 접근하고자 할 때 A 에 대한 인증만으로 B에 접근할 수 있게 해줌

#### Security Descriptors(보안 서술자)

* SACL : 폴더 접근/변경에 대한 기록
* DACL(ACL) : 폴더 접근에 대한 권한 할당 내역
  ![image-20191212104648417](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191212104648417.png)

### DNS (Domain Name System)

* FQDN(Host{www} + Domain Name{naver.com})을 DNS Server를 통해 IP 주소로 변환해 서비스의 위치를 검색하는 것
  DNS Server IP를 설정하지 않으면 IP 주소는 인식하나 FQDN 주소는 인식하지 못한다.
* DNS Zone 추가 후 발행되는 Name Server를 도메인 상에 등록하면 해당 도메인과 연결된다.
* Record
  * SOA : 권한의 시작
  * NS : Name Server 지정
  * A : Host Name > IPv4 주소로 매핑
  * CNAME : Host Name > 다른 Host Name으로 매핑
  * SVR : 서비스의 위치 정보를 알려줌
  * PTR : IP 주소 > Host Name으로 매핑
  * AAAA :  Host Name > IPv6 주소로 매핑