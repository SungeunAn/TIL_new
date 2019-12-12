## Azure

* [Internic](www.internic.org) : 전 세계 도메인을 관리하는 단체

  웹페이지를 갖고 싶다면 도메인 관리 업체에 등록해야 한다.

* **VM은 IaaS이며, Web App은 PaaS(OS와 IIS(Web Server)까지 구축되어 있음)이다.**

* **SSO(Single Sign On)** : 단일 아이디와 패스워드로 여러 서비스에 로그인 가능한 것으로, Azure AD가 이것을 가능하게 해준다.

* slot : 일종의 서비스 복사본으로, slot에서 서비스를 개발하거나 변경한 뒤 swap을 통해 실시간으로 업데이트 할 수 있다. > 업데이트를 위한 서비스 중지가 불필요하다.

* **Scale Up** : 메모리 용량 등 서버 장치의 성능을 높여주는 것 

* **Scale Out** : 동일한 서버를 복사해 성능을 확장하는 것 (분산처리) <-> Scale In

* 일정한 조건을 충족했을 때 자동으로 Scale Out/In 되도록 설정할 수 있다.

* Web App(PaaS 환경)은 Scale Up/Out 모두 가능하다.

* VM(IaaS 환경)은 Scale Up 확장은 가능하나 Scale Out은 불가능하다.
  Virtual Machine Scale Set을 통하면 가능하다.

  * Load Balancing Options에서 Application Gateway는 L7 장비, Load Balancer는 L4 장비에 적용된다. (???)

* VM Scale Networking (???)

  * Inbound Rule : VM으로 들어오는 포트에 대한 규칙이다.
  * Outbound Rule : VM에서 나가는 포트에 대한 규칙이며, 거의 사용되지 않는다.

* IIS (Internet Information Server, MS의 Web Server)

  * Web Server : 클라이언트가 정보를 요청하면 Web Server에서 요청한 웹사이트나 정보를 제공한다.
  * FTP Server
  * SMTP Server

* Apache (Linux/Unix의 Web Server)

* NGINX (Linux/Unix의 Web Server) : Apache보다 보안도 강하며 더 빠르다.

* **ARM(Azure Resource Manager) : 서비스를 하나하나 분리해놓은 것으로, 리소스 그룹을 기반으로 한다.**

  **Classic과는 달리 Tagging을 통해 서비스를 쉽게 분류하고 적용할 수 있다.** (교재 F 1-13 참고)
  **Git에 다양한 [ARM 템플릿](https://github.com/Azure/azure-quickstart-templates/tree/master/)이 있으며, 쉽게 검색해 적용하거나 배포할 수 있다.**
  **특정 사용자에게 특정 권한을 주고 관리하도록 하는 기능(RBAC, Rule Based Access Control)을  완전하게 지원한다.** 

* **Classic : ARM의 고전 버전으로, 제한된 RBAC을 지원한다.** (교재 F 1-13 참고)

* Wordpress : 오픈소스 설치형 블로그로, 전 세계 웹사이트의 2~30%를 차지할 정도로 널리 이용된다.
  Azure에서 Wordpress 웹페이지를 만들고 개발할 수 있다.



## MS Visual Studio

* Azure Tool 설치하면 Azure와 연동해서  개발 가능하다.
* Python, C 등의 언어도 바로 다운받아 사용 가능하다.
