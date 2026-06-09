# 오늘 뭐 먹지

주변 맛집을 한눈에 볼 수 있는 웹서비스 하네스 엔지니어링 샘플입니다.

## 이런 분께 필요해요
- 점심 메뉴 고르기 귀찮은 분
- 특정 음식 종류로 빠르게 찾고 싶은 분
- 지금 문 연 곳만 보고 싶은 분

## 구조

```
CLAUDE.md       ← 작업 원칙
AGENTS.md       ← 전체 규칙 및 담당자 목록
PLAN.md         ← 작업 단계 및 걱정되는 것
agents/
  finder.md     ← 맛집 정보 출처 찾기
  collector.md  ← 정보 모아서 정리하기
  display.md    ← 화면에 보여주기
  checker.md    ← 잘 됐는지 확인하기
skills/
  new-source/   ← 새 출처 추가할 때
  screen-check/ ← 화면 점검할 때
  data-check/   ← 데이터 확인할 때
  launch-check/ ← 내보내기 전 최종 확인
evals/
  test_cases.json ← 정답 목록
```

## 담당자 실행 순서

```
1. finder     → 출처 목록 만들기
2. collector  ↘
               동시에 작업
3. display    ↗
4. checker    → 마지막에 전체 확인
```

## 기능
- 가게 카드 목록
- 가게명 / 주소 검색
- 종류 필터 (한식 / 중식 / 일식 / 양식 / 카페)
- 거리순 / 평점순 정렬
- 문 닫은 가게 기본 숨김
- 지금 영업 중 표시
