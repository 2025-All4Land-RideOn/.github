# 🚲 스마트 자전거 통합 지도 플랫폼: [RideOn](https://www.saessakbori.site)

## 1. 개발 기간

- **기획:** 2025.09.01 ~ 2025.09.23  
- **개발:** 2025.09.24 ~ 2025.12.12

## 2. 서비스 개요

RideOn은 **대여·결제 중심으로 구성된 기존 자전거 서비스의 한계**를 문제로 정의하고, 길찾기·경사도·편의시설 정보를 핵심으로 제공하는 지도 중심 자전거 플랫폼을 목표로 기획되었습니다.

자전거 라이딩에 영향을 주는 경사도와 날씨 정보를 위치 데이터와 함께 분석하고, 대여소·음수대·공공화장실 등 **편의시설 정보를 하나의 지도 화면에 통합하여 라이딩 환경을 한눈에 파악하고 즉시 판단할 수 있는 직관적인 라이딩 경험을 제공**합니다.

## 3. 주요 기능

주요 기능의 실제 동작은  
👉 [RideOn 시연 영상 바로 보기](https://www.youtube.com/watch?v=l5gHjiKMxwA)에서 확인할 수 있습니다.

| 구분 | 기능 설명 |
|------|------------|
| 자전거 대여소 조회 | 자전거 대여소 위치 조회 및 카테고리 선택/해제, 목록 기반 탐색 기능 제공 |
| 편의시설 정보 제공 | 대여소, 수리점, 공공화장실, 음수대 등 편의시설 위치 및 상세 정보 제공 |
| 추천 자전거 코스 | 거리, 소요시간, 난이도 기준 자전거 코스 탐색 기능 제공 |
| 자전거 길찾기 | 지도에서 출발지와 도착지를 선택하면 OSRM 기반 최적 자전거 경로를 계산하고 지도에 시각화 |
| 경사도 분석 | Open Elevation API를 활용하여 경로 구간별 고도 값을 수집하고 경사도 정보 제공 |
| 지형 레이어 | DEM 기반 등고선 및 음영기복도(Hillshade)를 지도 레이어로 제공하여 지형의 고저 차이를 시각화 |
| 기본 지도 레이어 전환 | OpenStreetMap, Mapbox 위성, Mapbox 3D, VWorld 기본지도·위성지도·하이브리드 지도 간 전환 기능 |
| 행정구역 레이어 | 시·군·구 등 행정구역 경계를 별도의 레이어로 제공하여 지도 위에 표시 |
| 반경 분석 기능 | 현재 위치를 기준으로 1km, 3km, 5km 반경 원을 생성하여 주변 편의시설 접근 범위 시각화 |
| 날씨 레이어 | 기상청 API를 활용하여 기온, 강수, 풍속 정보를 지도 레이어 형태로 제공 |
| 현재 위치 및 좌표 정보 | 현재 위치 표시 및 지도 영역의 좌표·범위 정보 실시간 확인 기능 |
| AI 문의 기능 ‘라온이’ | 사용자의 질문에 대해 서비스 이용 및 기능 안내를 제공하는 AI 기반 문의 기능 |
| 북마크 | 자주 사용하는 대여소 및 편의시설을 즐겨찾기로 저장 |

## 4. 기술 스택 및 구조

| 구분 | 기술 |
|------|------|
| **Frontend** | React, OpenLayers, CesiumJS, Vite, WebGL |
| **Backend** | Spring Boot, PostgreSQL, PostGIS, GeoServer, Swagger |
| **API** | OSRM API, Open Elevation API, 기상청 API |
| **Data Source** | 공공데이터포털 자전거 대여소 및 편의시설 데이터, DEM(수치표고모델) |
| **Deployment** | Nginx, Docker, AWS EC2, Vercel, Cloudflare, GitHub Actions (CI/CD) |

## 5. 사용한 공공데이터

| 구분 | 데이터 정보 |
|------|-------------|
| 대여소 (station) | 1,482개 |
| 화장실 (toilet) | 4,585개 |
| 편의시설 (facility) | 1,129개 |
| 음수대 (drinking_fountain) | 1,685개 |
| 수치표고모델 (DEM) | 구간별 고도 분석용 래스터 데이터 |

## 6. 서비스 및 문서 자료 모음

| 링크 | 설명 |
|------|------|
| [🚲 RideOn (서비스 메인)](https://www.saessakbori.site) | Frontend 배포 URL |
| [📘 RideOn API Docs (API 문서)](https://api.saessakbori.site/rideon/docs) | Backend Swagger 문서 |
| [🧭 RideOn Notion (프로젝트 문서)](https://www.notion.so/269661ef461580818cd7fefc26e88926) | 기획 및 회의록 관리 |
| [🎨 RideOn Figma (UI/UX 디자인)](https://www.figma.com/design/AzxO7twZlOLPr0hIdqBPal/%EC%83%88%EC%8B%B9%EB%B3%B4%EB%A6%AC?node-id=22-296&p=f&t=5g8FcqEsFJtWj6WG-0) | 서비스 디자인 시안 |
| [🗂️ RideOn ERD (데이터베이스 구조)](https://app.diagrams.net/#H2025-All4Land-RideOn%2FERD%2Fmain%2FSessakBoriERD.drawio%23%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D) | DB 구조 및 관계 다이어그램 |
| [💻 RideOn GitHub Repository (저장소)](https://github.com/2025-All4Land-RideOn) | 프로젝트 원본 코드 저장소 |
  
## 7. 기여자

<table>
<tbody>
<tr>
<td style="padding: 20px;">
  <a href="https://github.com/MinSang22Kim" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/129925473?v=4" alt="김민상" width="135" height="145">
  </a>
</td>
<td style="padding: 20px;">
  <a href="https://github.com/skarndfuf1" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/85174279?v=4" alt="남궁렬" width="135" height="145">
  </a>
</td>
<td style="padding: 20px;">
  <a href="https://github.com/boeun02" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/93779288?v=4" alt="박보은" width="135" height="145">
  </a>
</td>
<td style="padding: 20px;">
  <a href="https://github.com/shinubin" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/100883938?v=4" alt="신유빈" width="135" height="145">
  </a>
</td>
<td style="padding: 20px;">
  <a href="https://github.com/dlgustj206" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/104957240?v=4" alt="이현서" width="135" height="145">
  </a>
</td>
</tr>
<tr>
<td><b>김민상</b></td>
<td><b>남궁렬</b></td>
<td><b>박보은</b></td>
<td><b>신유빈</b></td>
<td><b>이현서</b></td>
</tr>
</tbody>
</table>
