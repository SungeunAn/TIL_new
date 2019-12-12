## Azure

* Office365는 SaaS, Azure는 IaaS(VM)와 PaaS(Web App)이다.

---

### Storage

* Storage Account 만들어야 사용 가능하다.
* Networking 옵션을 통해 외부에서도 접근 가능하도록 만들 수 있다.
* Azure Storage Explorer를 통해 쉽게 Storage Account에 파일을 업/다운로드할 수 있다.

#### Types

* Blob Storage(Container) : Blob 데이터저장소
  컴퓨터 드라이브에서 '폴더'와 같은 역할

  ![image-20191211133206438](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191211133206438.png)

  * Blob : 이미지, 동영상 등 비정형 데이터를 담을 수 있는 객체
  * Page Blob(현재의 'Hot' 옵션) : 빈번한 액세스 환경에 적합하며 Azure VM의 디스크로 사용된다.
  * Block Blob(현재의 'cool' 옵션) : 가끔 액세스하는 환경에 적합하다.
  * Append Blob(현재 사용 X) : 추가 작업에 최적화되어 로그 정보 저장에 적합하다.

* Table Storage : 센서-측정값과 같이 Key-Value의 형태로 저장되는 저장소
  실시간 데이터 수집 등에 활용된다.

* Queue Storage : 알림 세팅을 할 때 사용하는 저장소

* File Storage : 파일 공유에 활용된다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    

#### 실습

##### Blob Storage(Container)

* Azure portal에서 업로드한 파일 경로 > Overview > URL을 통해 크롬에서 해당 파일에  엑세스할 수 있다. (익명공유를 한 경우만 해당)
  Azure Storage Explorer에서도 동일한 URL 확인 가능하다.

* Generate SAS 옵션 : 공유 기한, 읽기/쓰기 가능 여부 등 권한 부여 범위 결정

##### File Storage

* Storage Explorer에서 Connect to VM 을 통해 File Storage와 동기화 된 새 디스크를 생성할 수 있다.
  ![image-20191211145458189](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191211145458189.png)

  ![image-20191211145239804](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191211145239804.png)

---

### SQL

* 여러 명이 공유할 수 있고 데이터 양에 제한이 없는 DB 서버
* Window Server os에 설치 가능
  ![image-20191211171535484](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20191211171535484.png)

#### Azure SQL(PaaS/DBaaS)

* 사용자 DB만 사용 가능하며, 하위 서비스는 모두 MS가 관리한다.

#### SQL in an Azure VM(IaaS)

* VM에 SQL이 기본으로 깔려있는 상태
* 사용자 DB 뿐만이 아니라 시스템 DB까지 사용 가능하다.

#### SSMS(SQL Server Management Studio)

* Local, 원격 SQL 서버 관리 툴
* 원격 관리 시 TCP 1433 포트를 열어줘야 한다.
* Paas 및 Iaas SQL 서비스 모두 관리할 수 있다.
  (방화벽 등 일부 설정은 Azure Portal에서 변경)

---

### 기타

* [MS 모든 평가판 S/W 다운로드 URL](https://www.microsoft.com/ko-kr/evalcenter/)

* 100GB = 실제로는 약 98GB / 100GiB = 실제로 100GB 