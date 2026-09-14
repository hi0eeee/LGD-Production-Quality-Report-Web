## LGD-Production-Quality-Report-Web
<img width="493" height="398" alt="2026-09-14_171234" src="https://github.com/user-attachments/assets/4132eba4-def4-4a54-8323-f1e9af3089ce" />

**날짜: 09월 14일**

## 사용 라이브러리

* **Flask**

  * Python 기반 웹 서버 및 REST API 구현
  * 생산·품질 데이터 조회, 보고서 생성·저장 및 다운로드 기능 구현

* **Three.js**

  * 웹 브라우저에서 3D 패널 검사·이송 설비 구현
  * 카메라, 조명, 재질, 그림자 및 애니메이션 표현

* **OrbitControls**

  * 마우스를 이용한 3D 설비 회전 및 확대·축소 기능 구현

* **Cloudflared**

  * Google Colab에서 실행되는 Flask 서버를 외부에서 접속할 수 있도록 터널 생성

* **HTML / CSS / JavaScript**

  * 대시보드 화면 구성 및 디자인
  * 날짜·생산라인 필터링
  * 생산·품질 데이터 및 설비 이력 표시
  * 보고서 생성·수정·저장 기능 구현

* **Python**

  * 생산·품질 데이터 처리
  * JSON 데이터 저장
  * Flask 서버 실행 및 Cloudflared 연결 관리

## 설명

LG Display 생산·품질 업무를 이해하기 위해 제작한 **교육용 생산·품질 보고서 웹 서비스**입니다.

사용자는 조회할 **기간과 생산라인(A/B)**을 선택하여 생산 및 품질 데이터를 확인할 수 있습니다.

조회된 데이터를 기반으로 다음과 같은 정보를 확인할 수 있습니다.

* 목표 생산량 및 실제 생산량
* 생산 목표 달성률
* 검사 수량 및 불량 수량
* 불량률
* LOT별 생산·검사 기록
* 날짜별 불량률
* 생산라인별 설비 사건 기록
* 현재 모의 설비 상태

생산 달성률은 다음과 같이 계산합니다.

`생산 달성률 = 생산 수량 합계 ÷ 목표 수량 합계 × 100`

불량률은 다음과 같이 계산합니다.

`불량률 = 불량 수량 합계 ÷ 검사 수량 합계 × 100`

검사 수량이 없는 경우에는 불량률을 계산하지 않고 판단 불가 상태로 처리합니다.

또한 **Three.js**를 이용하여 패널 검사·이송 설비를 3D 형태로 구현하였습니다. 설비에는 컨베이어 롤러, 검사부, 검사 카메라, 패널, 상태등 등이 표현되어 있으며 마우스로 시점을 회전하거나 확대·축소할 수 있습니다.

조회한 데이터를 기반으로 **생산·품질 업무 보고서 초안**을 생성할 수 있으며, 사용자가 내용을 검토하고 수정한 뒤 저장할 수 있습니다.

보고서와 근거 데이터는 각각 **TXT와 JSON 형식으로 다운로드**할 수 있도록 구현하였습니다.

웹 서비스는 **Flask**를 이용하여 실행되며 Google Colab 환경에서 사용할 수 있습니다. 실행 시 사용 가능한 포트를 자동으로 탐색하고 **Cloudflared**를 이용해 외부 접속 URL을 생성합니다.

데이터 및 생성된 보고서는 JSON 파일을 이용하여 관리합니다.

## 주요 기능

1. 날짜 범위별 생산·품질 데이터 조회
2. 생산라인 A / B / 전체 필터링
3. 생산량 및 생산 목표 달성률 계산
4. 검사량 및 불량률 계산
5. LOT별 생산·품질 기록 표시
6. 날짜별 불량률 시각화
7. 설비 사건 이력 조회
8. Three.js 기반 3D 검사·이송 설비 구현
9. 생산·품질 업무 보고서 자동 초안 생성
10. 보고서 수정 및 검토 상태 저장
11. TXT 보고서 다운로드
12. JSON 근거 데이터 다운로드
13. Flask 웹 서버 실행
14. Cloudflared를 통한 외부 접속

## 실행 환경

* Google Colab
* Python 3
* Flask
* HTML / CSS / JavaScript
* Three.js
* Cloudflared

## 참고 문헌

* Flask Documentation
  https://flask.palletsprojects.com/

* Three.js Documentation
  https://threejs.org/docs/

* Three.js OrbitControls Documentation
  https://threejs.org/docs/#examples/en/controls/OrbitControls

* Cloudflare Tunnel Documentation
  https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/

* Python Documentation
  https://docs.python.org/3/

* jsDelivr CDN
  https://www.jsdelivr.com/

---

※ 본 프로젝트에서 사용된 생산량, 검사량, 불량량 및 설비 상태 등의 데이터는 **LG디스플레이 직무 이해를 위한 교육용 가상 데이터**입니다.
