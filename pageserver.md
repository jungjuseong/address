# PageServer 이관 목록

### 목차

1. CMS
2. CMS 외 개발
  - PDF Viewer
  - 비상 컨텐츠 제작
  - 인성교재 인증서버
3. CMS 자료 위치 & CMS 관련 기타
4. LG 노트북 자료/소스 현황
5. 기타

### 1. CMS

* CMS 정의/사용목적(매뉴얼 참고)

* CMS 시스템 구조 및 기능
  - 시스템 구조도, 매뉴얼 참고
  - 신버전 : Windows / 구버전 : Mac

* CMS 관련 계정/패스워드(신버전)
  - CMS 운용방법 PPT -> 장비 별 계정현황 참고

* 221.143.22.213 서버 (앱 실행 시 컨텐츠 다운로드하는 서버)
  - tomcat 위치 : /usr/local/apache-tomcat

* CMS 구버전(Mac서버) 구동 현황
  - URL (clbee.iptime.org:8080)
  - 설치 서버 (192.168.10.190) Mac 서버
  - tomcat 위치 => /usr/local/apache-tomcat-7.0.57
  - CMS 구버전 위치 => /usr/local/apache-tomcat-7.0.57/webapps/DocsBuilderCMS

* CMS 구버전(Mac서버) 계정
  - ID/PWD : clbeeserver/1234
  - root 계정 : root/1234
  - root 접속 필요 시 terminal에 ( sudo -i ) 입력 후 계정 입력

<hr>

## 1. CMS

### CMS 수정 필요사항

1. CMS > 템플릿 메뉴 : 템플릿 리스트 출력 리스트 order 방식 수정

  * 템플릿 등록 후 템플릿 수정에서 사용여부를 바꿔야 완료가 되는 템플릿 프로세스와, 완료된 템플릿들이 order 걸려서 출력되는 리스트 간의  충돌 => 템플릿 등록 후 해당 템플릿을 보고 싶은데, 리스트는 완료된 템플릿 기준으로 보여지고 방금 등록한 템플릿은 완료 전 상태여서 뒤로 밀리는 상황으로 인해 불편함이 느껴진다.

2. 각 메뉴들 url parameter 정리 필요 (참고문서 : 개발기능명세서)
    * 각 메뉴 안에서 url parameter를 맞추지 않은 경우들 있음(확인 필요함)
    * 회원관리/그룹관리는 정리한 상태

### CMS 향후 개발항목

1. 결재 프로세스 개발 -> 기획 필요
2. 퍼블리싱 작업
3. trial버전 라이선스 
    * 로그인은 필수 -> 로그인한 계정이 라이선스 없으면 자동적으로 trial버전 라이선스를 제공 (ex> 30일 무료)
    * 라이선스 관리 메뉴에 trial 버전 관리하는 내용 기획 필요
4. API 연계 개발
    * 타 시스템에서 API Call해서 CMS 기능이나 Data 접근(타 시스템과의 연계하고자는 목적)
5. epub3 내보내기 기능 -> 기획 필요
6. CMS 내 앱 갱신/새 버전 추가 시, 런처이미지 등록할 수 있는 기능
    * 이미지 파일 여러 개 등록 or 이미지 사이즈 조절 기능

7. 앱/콘텐츠/인앱콘텐츠 삭제 시, 파일도 삭제
    *  각각의 폴더 Naming및 구조가 달라서 고려해서 작업 진행 필요
8. 앱/콘텐츠/인앱콘텐츠 이전버전 되돌리기
    * 앱/콘텐츠/인앱콘텐츠 파일 관리 방식 재정리 필요(폴더 구조 등)
9. CMS 서버 이중화
    * 물리 서버, window OS, V3, 서버 이중화 케이블? 구입 필요
    * 서버 구입 및 필수 프로그램들 설치 후
    * CMS 시스템 구성 (tomcat, CMS, DB) => 설치 가이드 참고
    * Storage 연결 (tomcat -> CMS Data 영역 / DB data 영역)
    * 서버 이중화 연결
10. 221.143.22.213 서버 Upgrade?

* 10번 항목 관련 참고사항
    * windows에 FTP 서버 구성함(서비스 > Microsoft FTP Service 시작)
        - 서비스 메뉴 명령어 : services.msc
    * AppMaker의 213 요소들 제거(DownLoad URL만 수정 시 안됨 => 분석 필요)
    * 스토리지의 Android/iOS 2개 디렉토리 구조 분리(Android쪽 구조로 합쳐야 함)
        - 221.143.22.213 서버의 구조 참고 필요
        - 위치 : Volumes > Data > data > server > newcms > data > app …

### 2. PDF Viewer

- 약관 등의 PDF 문서를 보기 위해 사용
- 사용 기술 : JavaScript, Jquery (PDFJs 오픈소스 기반)
- 관련 업체 : KB 손해보험
=> 웹용 뷰어 + 앱(iOS / Android) 뷰어

* 뷰어 개발 관련 : 기오정 차장님
* KB 손해보험 관련 : 백지웅 과장님(iOS 앱), 현가람 대리(서식제작)

### 3. 인성교재 인증서버

- 유치원/초등학교 인성교육 목적의 인성교재 컨텐츠 사용과 관련하여 인성교재 앱 접속 인증을 위한 인증 서버
- 사용 기술 : jsp + spring + mysql
- 관련 업체 : 으뜸정보기술
        * 클비시스템 내에 인증서버 구축되어 있음

* 관련 : 이재호 대표님, 기오정 차장님
* 인성교재 인증서버 구동 현황
- URL: clbee.iptime.org:18080
- 관리자 계정 (“으뜸정보기술”에서도 알고 있음) (service/!1q2w3e4r)
- 설치 서버 (192.168.10.190) Mac 서버
- tomcat 위치 /usr/local/apache-tomcat-7.0.82
- 인성교재 인증서버 /usr/local/apache-tomcat-7.0.82/webapps/clbee_is
- tomcat manager url : http://clbee.iptime.org:18080/manager
        *  id : admin / pwd : vpdlwlqlfejCms2014 (페이지빌더Cms2014)

* 인성교재 인증서버 수정 이력

- 20180316(금)
- 각 계정들 패스워드 출력 요구
-  패스워드 암호화 모두 제거한 상태

향후 인성교재 인증서버 관련해서 작업한 이력은 별도로 관리 해주셔야 합니다.
