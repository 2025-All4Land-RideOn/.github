# 🚲 스마트 자전거 지도 플랫폼: [RideOn](https://www.saessakbori.site)

## 1. 개발 기간

- **기획:** 2025.09.01 ~ 2025.09.23  
- **개발:** 2025.09.24 ~ 2025.12.12

## 2. 서비스 개요

**첫째**, RideOn은 대여·결제 중심 자전거 서비스의 한계를 문제로 정의하고, 길찾기·경사도·편의시설 정보를 핵심으로 하는 지도 중심 자전거 플랫폼을 목표로 합니다.

**둘째**, 자전거 라이딩에 영향을 주는 경사도·날씨 정보를 위치 데이터와 함께 분석하여, 라이딩 환경을 지도에서 한눈에 파악할 수 있도록 합니다.

**셋째**, 모든 정보를 하나의 지도 화면에 통합하여, 사용자가 즉시 판단하고 활용할 수 있는 직관적인 라이딩 경험을 제공합니다.

## 3. 주요 기능

| 구분 | 기능 설명 |
|------|------------|
| 자전거 대여소 조회 | 자전거 대여소 위치 조회 및 카테고리 선택/해제, 목록 기반 탐색 기능 제공 |
| 편의시설 정보 제공 | 대여소, 수리점, 공공화장실, 음수대 등 편의시설 위치 및 상세 정보 제공 |
| 추천 자전거 코스 | 거리, 소요시간, 난이도 기준 자전거 코스 탐색 기능 제공 |
| 자전거 길찾기 | 지도에서 출발지와 도착지를 선택하면 OSRM 기반 최적 자전거 경로를 계산하고 지도에 시각화 |
| 경사도 분석 | Open Elevation API를 활용하여 경로 구간별 고도 값을 수집하고 경사도 정보 제공 |
| 등고선 레이어 | DEM 기반 등고선 데이터를 지도 레이어로 제공하여 지형 형태 시각화 |
| 음영기복도 레이어 | DEM 기반 음영기복도(Hillshade)를 통해 지형의 고저 차이를 직관적으로 표현 |
| 날씨 정보 조회 | 기상청 API를 활용한 현재 날씨 정보 제공 |
| 지도 레이어 전환 | 기본 지도(OSM), 행정구역, 등고선, 음영기복도 등 지도 레이어 선택 및 전환 기능 |
| 현재 위치 및 좌표 정보 | 현재 위치 표시 및 지도 영역의 좌표·범위 정보 실시간 확인 기능 |
| AI 문의 기능 ‘라온이’ | 사용자의 질문에 대해 서비스 이용 및 기능 안내를 제공하는 AI 기반 문의 기능 |
| 북마크 | 자주 사용하는 대여소 및 편의시설을 즐겨찾기로 저장 |

## 4. 기술 스택 및 구조

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

## 5. 사용한 공공데이터

| 구분 | 데이터 수량 |
|------|-------------|
| 대여소 (station) | 1,482 |
| 화장실 (toilet) | 4,585 |
| 편의시설 (facility) | 1,129 |
| 음수대 (drinking_fountain) | 1,685 |

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
