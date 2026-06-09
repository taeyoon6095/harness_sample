---
name: qa-deadline-links
description: 영업시간, 링크, 누락 필드, 중복 가게를 검증할 때 사용
---

# Goal
정규화된 맛집 데이터의 신뢰성을 검증한다.

# Checks
- open_hours 파싱 실패 여부
- 현재 시각 기준 open_now 계산 정확성
- 필수 필드(name, address, category, open_hours, url) 누락 여부
- 중복 가게 존재 여부
- 깨진 링크 존재 여부

# Procedure
1. normalized 데이터 파일을 읽는다.
2. validate_hours.py 실행
3. validate_links.py 실행
4. dedupe_check.py 실행
5. 오류 수를 집계한다.
6. 치명도별로 결과를 정리한다.

# Severity
- P0: 앱을 깨뜨리는 구조적 데이터 오류
- P1: 링크 깨짐, 필수값 누락, 영업 여부 오판
- P2: 경미한 표시 불일치

# Output format
1. summary
2. P0/P1/P2 목록
3. 오류 개수 테이블
4. 바로 수정할 3개 항목
