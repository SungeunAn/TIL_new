## 시험 문제:1st_place_medal:

* 클라우드 서비스 : 네트워크를 통해 받는 모든 서비스
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

