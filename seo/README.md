# mrchea.com 구글 노출 전략: "시드니 프라이빗 투어 / 한국어·영어 가이드"

점검일: 2026-10-12 (라이브 사이트 기준)

## 1. 현재 상태 진단

**잘 되어 있는 것**
- 페이지 44개(한/영 각 22개)가 sitemap.xml에 모두 등록됨, robots.txt 정상
- hreflang(ko/en), canonical, OG 태그 모두 있음
- TravelAgency·TouristTrip 구조화 데이터 있음
- Cloudflare 호스팅이라 속도가 빠름

**핵심 문제: 노출시키고 싶은 검색어가 사이트에 없음**

| 검색어 | 한국어 홈 | 영어 홈 |
|---|---|---|
| 프라이빗 / private | 0회 | 1회 |
| 한국어 가이드 / Korean-speaking | 0회 | 0회 |
| 영어 가이드 / English-speaking | 0회 | 0회 |

구글은 페이지에 없는 단어로는 그 페이지를 거의 보여주지 않습니다. 지금 사이트는
"시드니 한인 가이드 투어"로는 잡힐 수 있지만, "시드니 프라이빗 투어"나
"Korean speaking guide Sydney"로 검색하면 비교할 대상조차 되지 않습니다.

그 밖의 문제:
- Google Search Console 인증 태그가 없어서 구글이 사이트를 언제, 어떤 검색어로 보여주는지 알 수 없음
- 투어 페이지의 FAQ에 FAQPage 구조화 데이터가 없음
- 한국어 홈 구조화 데이터에 전화번호와 `availableLanguage`가 빠져 있음 (영어 홈에는 있음)

## 2. 전략: 세 축

1. **키워드 전용 랜딩페이지**: 검색어마다 그 검색어를 정면으로 다루는 페이지를 하나씩 둡니다.
2. **기존 페이지에 키워드 심기**: 홈 title·description·첫 문단에 "프라이빗", "한국어 가이드", "private", "Korean & English speaking"을 넣습니다.
3. **구글 쪽 신호**: Search Console, Google 비즈니스 프로필(지도), 외부 링크와 리뷰.

"시드니 프라이빗 투어" 같은 검색은 구글 지도 결과(로컬 팩)가 맨 위에 뜨는 경우가 많습니다.
**Google 비즈니스 프로필 + 리뷰가 웹사이트만큼 중요합니다.** 프로필 문구와 상품 21개는
`claude/wizardly-gauss-1e1k7d` 브랜치에 이미 준비되어 있습니다.

## 3. 실행 체크리스트 (순서대로)

### STEP 1: 랜딩페이지 2개 업로드 ✅ 파일 완성
| 파일 | 올릴 주소 | 노리는 검색어 |
|---|---|---|
| `site/private-tour/index.html` | https://mrchea.com/private-tour/ | 시드니 프라이빗 투어, 시드니 한국어 가이드, 시드니 단독 투어 |
| `site/en/private-tour/index.html` | https://mrchea.com/en/private-tour/ | Sydney private tour, Korean speaking guide Sydney, English and Korean speaking tour guide |

- 기존 사이트의 `/assets/style.css`와 `/img/`를 그대로 씁니다. 사이트 소스 폴더의 같은 위치에 복사해서 배포하면 됩니다.
- 둘 다 FAQPage·Service·BreadcrumbList 구조화 데이터가 들어 있습니다.
- ⚠️ 확인 필요: "모든 투어가 일행 단독(프라이빗)으로 진행된다", "영어로도 진행 가능"이라고 썼습니다. 사실과 다르면 알려주세요. 바로 고치겠습니다.

### STEP 2: sitemap.xml에 4줄 추가
```xml
  <url><loc>https://mrchea.com/private-tour/</loc><lastmod>2026-10-12</lastmod><changefreq>monthly</changefreq><priority>0.9</priority></url>
  <url><loc>https://mrchea.com/en/private-tour/</loc><lastmod>2026-10-12</lastmod><changefreq>monthly</changefreq><priority>0.9</priority></url>
```

### STEP 3: 홈페이지 수정 (`index.html`, `en/index.html`)

**한국어 홈 `<title>` / description**
```html
<title>시드니 프라이빗 투어 · 한국어 가이드 이채룡 | 시드니이작가여행사</title>
<meta name="description" content="시드니 한인 가이드 이채룡이 한국어로 직접 안내하는 프라이빗 데이투어·호주 로드트립·뉴질랜드 콤보 21가지. 우리 일행만, 호텔 픽업, 일정 맞춤. 카카오톡 상담.">
```
og:title, og:description도 같은 문구로 바꿔 주세요.

**영어 홈 `<title>` / description**
```html
<title>Sydney Private Tours with a Korean &amp; English Speaking Guide | Mr Chea</title>
<meta name="description" content="Private Sydney day tours and Australian road trips for your group only, led by Mr Chea, a bilingual Korean and English speaking local guide. Hotel pick-up, flexible itineraries. Message on WhatsApp.">
```

**본문에 내부 링크 한 줄** (히어로 문단 아래 또는 데이투어 섹션 제목 아래)
```html
<!-- 한국어 홈 -->
<p class="note">모든 투어는 <a href="/private-tour/">우리 일행만 함께하는 프라이빗 투어</a>로, 한국어 가이드가 직접 안내합니다.</p>
<!-- 영어 홈 -->
<p class="note">Every tour runs as a <a href="/en/private-tour/">private tour for your group only</a>, guided in English and Korean.</p>
```
홈에서 랜딩페이지로 링크가 있어야 구글이 그 페이지를 중요하게 봅니다.

**한국어 홈 구조화 데이터 보강**: 기존 TravelAgency JSON에 아래 항목을 추가합니다.
```json
"telephone": "+61431468373",
"availableLanguage": ["Korean", "English"],
"knowsLanguage": ["ko", "en"],
"alternateName": ["Mr Chea", "mrchea.com", "시드니이작가"]
```

### STEP 4: 투어 페이지 22개에 FAQPage 구조화 데이터 추가
각 투어 페이지에 이미 FAQ(`<details>`)가 있으므로, 같은 내용을 FAQPage JSON-LD로도 넣습니다.
사이트를 생성하는 스크립트에 한 번만 추가하면 됩니다. 투어 페이지 `<title>`에도
"프라이빗" 또는 "Private"를 넣는 것을 권장합니다. 예:
`시드니 러닝 투어 · 프라이빗 한국어 가이드 | 시드니이작가여행사`

### STEP 5: Google Search Console 등록 (사장님이 직접, 10분)
1. https://search.google.com/search-console 에서 chea77lee@gmail.com으로 로그인
2. "도메인" 방식으로 `mrchea.com` 추가 → Cloudflare DNS에 TXT 레코드 추가 (Cloudflare는 자동 연결 버튼을 제공합니다)
3. Sitemaps 메뉴에서 `https://mrchea.com/sitemap.xml` 제출
4. URL 검사에 `https://mrchea.com/private-tour/`, `https://mrchea.com/en/private-tour/` 입력 → "색인 생성 요청"
5. 네이버 서치어드바이저도 같은 방식으로 등록 (홈 `<head>`에 자리만 만들어 둔 메타태그가 있습니다)

### STEP 6: Google 비즈니스 프로필 (가장 효과가 큼)
- `claude/wizardly-gauss-1e1k7d` 브랜치의 `google-business-profile.md`(한), `google-business-profile-en.md`(영), 상품 21개 문구 사용
- 카테고리: 기본 **Tour operator**, 추가 **Tour agency**, **Sightseeing tour agency**
- 웹사이트 링크: `https://mrchea.com/private-tour/`
- 서비스 지역: 시드니 / 언어 속성에 한국어·영어 표시
- **리뷰가 순위를 좌우합니다**: 투어가 끝날 때마다 리뷰 링크를 카톡·왓츠앱으로 보내세요. 리뷰에 "프라이빗", "한국어 가이드" 같은 말이 자연스럽게 들어가면 효과가 더 큽니다. 리뷰를 써 달라고 할 수는 있지만, 대가를 주거나 문구를 정해 주면 안 됩니다.

### STEP 7: 외부 링크와 꾸준한 콘텐츠 (매달)
- 네이버 블로그·인스타·유튜브 글마다 `mrchea.com/private-tour/` 링크
- 마이리얼트립, KKday(리스팅 패키지는 `claude/happy-euler-tstcmq` 브랜치에 있음), Klook, GetYourGuide, Tripadvisor 프로필에 웹사이트 링크
- 영어 블로그 글 월 1~2개를 `/en/` 아래에 추가. 예: "Is a private tour in Sydney worth it?", "Blue Mountains private tour vs group tour"

## 4. 기대 일정
- 1~2주: 새 페이지 색인 (Search Console에서 확인)
- 1~3개월: "시드니 프라이빗 투어 한국어" 같은 긴 검색어부터 노출 시작
- 3~6개월: 리뷰가 쌓이면 지도 결과와 짧은 검색어에서 순위 상승

## 5. 다음에 같이 할 일
- [ ] 사이트 소스(생성 스크립트) 위치 공유 → STEP 3, 4를 직접 코드로 반영
- [ ] Search Console 연결 후 2주 뒤 실제 검색어 데이터를 보고 페이지 문구 조정
- [ ] 영어 블로그 글 첫 편 작성
