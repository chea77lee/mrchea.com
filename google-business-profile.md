# 구글 비즈니스 프로필 등록 키트 – 시드니이작가여행사

등록 주소: https://business.google.com/create (chea77lee@gmail.com 계정으로 로그인)
아래 값은 각 입력란에 그대로 복사해 넣으면 됩니다.

## 1. 기본 정보

| 항목 | 입력값 |
|---|---|
| 비즈니스 이름 | `시드니이작가여행사` (사이트·로고와 똑같이. 키워드를 덧붙이면 프로필 정지 사유가 돼요) |
| 기본 카테고리 | `Tour agency` (투어 에이전시) |
| 추가 카테고리 | `Tour operator`, `Travel agency`, `Sightseeing tour agency` |
| 매장 방문 가능? | **아니요** (사무실 주소 비공개 → 서비스 지역 비즈니스) |
| 서비스 지역 | `Sydney NSW`, `New South Wales`, `Australia` (최대 20개, 국가 단위도 가능) |
| 전화 | `+61 431 468 373` |
| 웹사이트 | `https://mrchea.com/` |
| WhatsApp (소셜 프로필 → WhatsApp) | `https://wa.me/61431468373` |
| 운영 시간 | 예: 월–일 07:00–21:00 (카톡 상담 가능 시간 기준으로 조정) |

> 주소는 인증용으로만 입력하고 고객에게는 숨겨집니다. 집 주소를 써도 공개되지 않아요.

## 2. 비즈니스 설명 (750자 이내)

한국어 (약 330자):
```
시드니 현지 한인 가이드 이채룡(시드니이작가)이 직접 안내하는 소규모 프라이빗 투어입니다. 2003년 호주에 와서 DFS·LG전자 호주법인을 거쳐 2019년부터 시드니에서 가이드로 일하고 있어요. 블루마운틴 트레킹, 헌터밸리 와이너리, 로열국립공원·울릉공 데이투어부터 시드니 러닝투어, 오페라하우스 인문학 투어, 골프·미식 컨시어지까지 준비되어 있습니다. 시드니–멜버른·골드코스트·태즈매니아·퍼스 로드트립, 울루루 아웃백, 뉴질랜드 남·북섬 콤보 일정도 인솔합니다. 일정과 가격은 mrchea.com에서 확인하고, 카카오톡 채널 '시드니이작가'로 편하게 상담하세요.
```

English (약 560자, 영어 검색용 — 하나만 쓴다면 한국어 권장):
```
Private and small-group tours in Sydney led by Korean-speaking local guide Chae-ryong Lee (Sydney Lee Writer). Day tours include Blue Mountains trekking, Hunter Valley wineries, Royal National Park & Wollongong, a Sydney sunrise running tour and an Opera House humanities tour, plus golf and food concierge. We also lead multi-day road trips from Sydney to Melbourne, the Gold Coast, Tasmania, Perth and Uluru, and Australia–New Zealand combo tours. See itineraries and prices at mrchea.com and chat with us on KakaoTalk.
```

## 3. 서비스(상품) 등록 – "서비스" 탭

데이투어: 블루마운틴 트레킹 · 헌터밸리 와이너리 · 로열국립공원&울릉공 · 시드니 러닝투어 · 오페라하우스 인문학 투어 · 시드니 수영/락풀 · 시드니 미식 컨시어지 · 시드니 골프 컨시어지
로드트립: 시드니–골드코스트 5일/10일 · 시드니–멜버른 6일/13일 · 시드니 힐링 5일 · 시드니–태즈매니아 7일 · 시드니–퍼스 8일 · 호주 횡단 퍼스 그랜드투어 18일 · 울루루 아웃백 18일
뉴질랜드 콤보: 시드니–오클랜드 북섬 6일 · 시드니–크라이스트처치 남섬 6일 · 시드니–퀸스타운 남섬 7일 · 뉴질랜드 남북섬 10일

각 서비스에 해당 상품 페이지 링크(`https://mrchea.com/tour/…/`)를 붙이면 클릭이 사이트로 바로 연결됩니다.

## 4. 사진 (등록 직후 최소 10장)

- 로고: `https://mrchea.com/img/brand_badge.png` (정사각)
- 커버: `https://mrchea.com/img/og-roof.jpg` (가로 16:9)
- 가이드 본인 사진 2–3장, 실제 투어 현장 사진 5장 이상 (AI 이미지는 정책 위반 소지 있으니 실사만)

## 5. 인증 (가장 중요)

서비스 지역 비즈니스는 보통 **동영상 인증**을 요구합니다. 한 번에 끊김 없이 촬영:
1. 현재 위치를 보여주는 거리 표지판/주변
2. 투어 차량 또는 장비(로고·명함·브로셔 등 브랜드가 보이는 것)
3. 사업 운영 증빙: ABN 서류, 예약 화면, 카톡 채널 관리자 화면 등

인증 후 반영까지 보통 며칠~최대 2주.

## 6. 등록 후 할 일

- [ ] Google Search Console에 `mrchea.com` 등록 (도메인 속성 → Cloudflare DNS TXT 레코드로 인증)
- [ ] 프로필의 "리뷰 받기" 링크 생성 → 투어 끝난 손님께 카톡으로 전송 (리뷰가 지역 노출 1순위 요소)
- [ ] 프로필 공유 링크(`https://g.page/r/…` 또는 maps 링크)를 받으면 사이트 JSON-LD `sameAs`에 추가하고 `telephone`도 넣기:
  ```json
  "telephone": "+61-431-468-373",
  "sameAs": [ ..., "https://maps.google.com/?cid=여기에_CID" ]
  ```
- [ ] 주 1회 "업데이트" 게시물: 인스타 올린 사진+캡션 재활용 (예: 러닝투어 세트)
