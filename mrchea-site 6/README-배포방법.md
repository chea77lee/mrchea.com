# mrchea.com 새 사이트 폴더 (홈 + 상품 21개 페이지)

## 1. Cloudflare에 올리기
1. Cloudflare 대시보드 → Workers & Pages → mrchea.com을 서비스 중인 프로젝트를 엽니다.
2. Pages 프로젝트라면 "새 배포(Create deployment / Upload assets)"에서 이 폴더 전체(index.html, tour, en, img, assets, sitemap.xml, robots.txt, _headers, _redirects)를 올립니다.
3. 배포 후 아래 주소가 열리는지 확인합니다.
   - https://mrchea.com/
   - https://mrchea.com/tour/blue-mountains-trekking-day-tour/
   - https://mrchea.com/sitemap.xml (주소 22개가 보여야 합니다)

## 2. 네이버 서치어드바이저
1. searchadvisor.naver.com → 사이트 등록 → https://mrchea.com
2. 소유확인(HTML 태그): 발급된 메타태그를 index.html의 `<head>` 안 주석 부분에 붙여 넣고 다시 배포한 뒤 "소유확인"을 누릅니다.
3. 요청 → 사이트맵 제출: https://mrchea.com/sitemap.xml
4. 요청 → 웹 페이지 수집: 상품 페이지 주소를 하나씩 넣어 색인을 앞당깁니다.

## 3. 블로그 연결
`블로그-링크표.md`의 링크를 블로그 글 CTA에 그대로 붙이세요. 글마다 utm_campaign 값이 달라서 어느 글에서 방문이 왔는지 알 수 있습니다.

## 4. 내용 수정
가격·일정·설명은 각 `tour/…/index.html` 안에 들어 있습니다. 문구를 바꾸고 싶으면 알려주시면 다시 빌드해 드립니다.

## 5. 짧은 주소 (_redirects)
- 블로그 글에는 긴 utm 주소 대신 짧은 주소를 쓰세요. 예: mrchea.com/bm (블루마운틴), mrchea.com/hv (헌터밸리), mrchea.com/p1 ~ /p21, mrchea.com/kakao
- 누르면 utm이 붙은 상품 페이지로 자동 이동하므로 유입 추적도 그대로 됩니다. 전체 목록은 `블로그-링크표.md`에 있어요.
- 배포 후 브라우저에서 mrchea.com/bm 을 열어 상품 페이지로 이동하는지 꼭 확인하세요. 404가 나오면 알려 주세요.

## 6. 영어판 (/en/) — 2026-10-08 추가
- 영어 홈: mrchea.com/en/ · 영어 상품 21개 전체: mrchea.com/en/tour/…/ (한국어판과 같은 주소 앞에 /en 만 붙습니다)
- 영어판 문의는 카카오톡 대신 WhatsApp(+61 431 468 373). 짧은 주소: mrchea.com/whatsapp
- 모든 페이지 상단에 언어 전환 버튼(EN / 한국어)이 있습니다.
- 배포할 때 `en` 폴더도 함께 올리세요. sitemap.xml 주소는 44개가 보여야 합니다.
- 영어판 브랜드명은 mrchea.com, 가이드 이름은 Mr Chea 로 통일했습니다.
- 한국어 홈의 '내 손으로 짜는 여행' 섹션(AI 일정 빌더·공항 픽업·항공권·호텔)은 chea.travelmartnz.com 으로 연결됩니다. (트래블마트가 한국어 전용이라 영어판에는 넣지 않았습니다.)

## 7. 프라이빗 투어 SEO 업데이트 — 2026-10-12
- 새 페이지: mrchea.com/private-tour/ (한국어) · mrchea.com/en/private-tour/ (영어)
  - 노리는 검색어: 시드니 프라이빗 투어 · 한국어 가이드 / Sydney private tour · Korean & English speaking guide
- 한·영 홈: 제목·설명을 "프라이빗 투어 · 한국어(영어) 가이드" 중심으로 변경, 데이투어 섹션에 프라이빗 안내 링크 추가
- 모든 페이지 상단 메뉴에 "프라이빗 투어 / Private tours" 추가
- 투어 페이지 42개: 제목·설명에 키워드 추가, FAQ에 "프라이빗 진행 가능?"(데이투어), "안내 언어?"(전체) 질문 추가
- sitemap.xml 주소는 이제 46개가 보여야 합니다.
- 배포 후 Google Search Console에서 sitemap 다시 제출 + 두 새 주소 "색인 생성 요청"
