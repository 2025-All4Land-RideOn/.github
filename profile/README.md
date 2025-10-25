# 🚲 스마트 자전거 지도 플랫폼: [RideOn](https://www.saessakbori.site)

## 🗓️ 1. 개발 기간

- **기획:** 2025.09.01 ~ 2025.09.23  
- **개발:** 2025.09.24 ~ 2025.11.xx

## 📖 2. 서비스 개요

1. **공공데이터 기반 자전거 지도 플랫폼**  
   └ 자전거 대여소, 수리점, 화장실, 음수대 등 공공데이터를 통합하여 지도 표시

2. **벡터·래스터 공간정보 융합 처리**  
   └ **벡터(Vector)**: 대여소 및 편의시설 위치(POI) 시각화  
   └ **래스터(Raster)**: DEM·기온 등 환경 데이터로 경사도·날씨 분석  

3. **지도 중심 사용자 경험(UX) 강화**  
   └ 경로 탐색, 추천 코스, 편의시설 정보를 한 화면에서 직관적으로 제공  

4. **대여·결제 중심 서비스와의 차별화**  
   └ 결제보다는 **길찾기·코스 탐색·편의시설 시각화 중심**으로 기능 확장
   
## 🧩 3. 주요 기능

| 구분 | 기능 설명 |
|------|------------|
| 🗺️ **자전거 대여소 조회** | 카테고리별 선택/해제, 필터링, 목록 및 검색 기능 제공 |
| 🧰 **편의시설 정보** | 대여소·수리점·공공화장실·음수대 등 POI(Point of Interest) 위치 및 상세 정보 제공 |
| 🛤️ **추천 자전거 코스** | 거리·소요시간·난이도별 자전거 코스 탐색 및 사용자 평점 제공 |
| 🧭 **자전거 길찾기** | 지도에서 출발지와 도착지를 클릭하면 OSRM(Open Source Routing Machine)기반 최적 경로 탐색 및 시각화 |
| 🌡️ **날씨·온도 히트맵** | OpenWeatherMap API 기반 실시간 온도 분포 시각화 |
| ⛰️ **고도·경사도 분석** | DEM(수치표고모델) 기반 구간별 경사도 시각화 (초록/노랑/빨강 그라데이션 표시) |
| 🌞 **일조량 분석** | 시간대별 그림자(그늘) 구간을 시뮬레이션하여 코스별 일조량 비교 |
| 🚻 **편의시설 접근성 히트맵** | 화장실·음수대 등 편의시설 접근성을 반경(2~3km) 기반으로 시각화 |
| 🔥 **이용자 밀집도 히트맵** | 라이더 이동 로그 기반 구간별 이용 밀집도 시각화 (사고다발지역 분석 가능) |
| 💬 **문의 / Q&A** | 사용자가 질문 시 챗봇 형태로 응답 제공 |
| 🔖 **북마크** | 자주 이용하는 대여소·편의시설을 즐겨찾기로 저장 |

## ⚙️ 4. 기술 스택 및 구조

| 구분 | 기술 |
|------|------|
| **Frontend** | React, OpenLayers, Vite, WebGL |
| **Backend** | Spring Boot, PostgreSQL(PostGIS), Swagger |
| **API** | OSRM(Open Source Routing Machine), OpenWeatherMap, 기상청 API |
| **Data Source** | 공공데이터포털 자전거 대여소 및 편의시설 데이터 |
| **Deployment** | Nginx, Docker, AWS EC2, Vercel, Cloudflare |

- **OpenLayers + WebGL 렌더링**으로 수천 개의 벡터 데이터를 부드럽게 시각화  
- **PostGIS**를 이용해 출발·도착지 및 waypoint 기준 반경 내 편의시설 검색  
- **OSRM 경로 API**를 통해 실시간 자전거 길찾기 및 GeoJSON 기반 Polyline 렌더링

## 🧠 5. 사용한 공공데이터

| 구분 | 데이터 수량 |
|------|-------------|
| 🚲 대여소 (station) | 1,482 |
| 🚻 화장실 (toilet) | 4,585 |
| 🏪 편의시설 (facility) | 1,129 |
| 🚰 음수대 (drinking_fountain) | 1,685 |

## 🌐 6. 서비스 및 문서 자료 모음

| 링크 | 설명 |
|------|------|
| [🚲 RideOn (서비스 메인)](https://www.saessakbori.site) | Frontend 배포 URL |
| [📘 RideOn API Docs (API 문서)](https://api.saessakbori.site/rideon/docs) | Backend Swagger 문서 |
| [🧭 RideOn Notion (프로젝트 문서)](https://www.notion.so/269661ef461580818cd7fefc26e88926) | 기획 및 회의록 관리 |
| [🎨 RideOn Figma (UI/UX 디자인)](https://www.figma.com/design/AzxO7twZlOLPr0hIdqBPal/%EC%83%88%EC%8B%B9%EB%B3%B4%EB%A6%AC?node-id=22-296&p=f&t=5g8FcqEsFJtWj6WG-0) | 서비스 디자인 시안 |
| [🗂️ RideOn ERD (데이터베이스 구조)](https://app.diagrams.net/#H2025-All4Land-RideOn%2FERD%2Fmain%2FSessakBoriERD.drawio%23%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D) | DB 구조 및 관계 다이어그램 |
| [💻 RideOn GitHub Repository (저장소)](https://github.com/2025-All4Land-RideOn) | 프로젝트 원본 코드 저장소 |

## 📍 7. 향후 확장 계획

| 항목 | 설명 |
|------|------|
| 🤖 **AI 추천 경로 시스템 및 AI 문의 접수** | 날씨·경사도·일조량·편의시설 접근성을 종합 분석하여 개인 맞춤형 코스 추천 및 AI 자동 응답 기능 추가 예정 |
| 🧭 **모바일 네비게이션 모드** | 실시간 이동 경로 안내 및 음성 내비게이션 지원 |
| 🔑 **소셜 로그인 및 북마크 기능 강화** | 카카오·네이버 로그인 안정화 및 개인화된 즐겨찾기 데이터 저장 |
| 🗺️ **전국 행정구역 확장** | 서울 외 지역(수도권 및 주요 광역시)까지 데이터 확대 및 행정구역 레이어 표시 |
  
## 👀 8. 기여자
<div align="center">
<table>
<tbody>
<tr>
<td align="center" style="padding: 20px;">
  <a href="https://github.com/MinSang22Kim" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/129925473?v=4" alt="김민상" width="120" height="120" style="max-width: 100%;">
  </a>
</td>
<td align="center" style="padding: 20px;">
  <a href="https://github.com/skarndfuf1" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/85174279?v=4" alt="남궁렬" width="120" height="120" style="max-width: 100%;">
  </a>
</td>
<td align="center" style="padding: 20px;">
  <a href="https://github.com/boeun02" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/93779288?v=4" alt="박보은" width="120" height="120" style="max-width: 100%;">
  </a>
</td>
<td align="center" style="padding: 20px;">
  <a href="https://github.com/shinubin" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/100883938?v=4" alt="신유빈" width="120" height="120" style="max-width: 100%;">
  </a>
</td>
<td align="center" style="padding: 20px;">
  <a href="https://github.com/dlgustj206" target="_blank" rel="noopener noreferrer nofollow">
    <img src="https://avatars.githubusercontent.com/u/104957240?v=4" alt="이현서" width="120" height="120" style="max-width: 100%;">
  </a>
</td>
</tr>
<tr>
<td align="center"><b>김민상</b></td>
<td align="center"><b>남궁렬</b></td>
<td align="center"><b>박보은</b></td>
<td align="center"><b>신유빈</b></td>
<td align="center"><b>이현서</b></td>
</tr>
</tbody>
</table>
</div>
