---
name: source-intake
description: 새로운 맛집 데이터 소스를 추가하고 표준 스키마로 정규화할 때 사용
---

# Goal
새로운 플랫폼의 맛집 데이터를 파싱하여 표준 스키마로 변환한다.

# Standard schema
- name
- category
- address
- distance_m
- rating
- open_hours
- open_now
- phone
- url
- source_name
- source_fetched_at
- raw_hours

# Procedure
1. 소스 페이지 구조를 파악한다.
2. 반복 항목 selector를 찾는다.
3. 각 항목에서 필요한 필드를 추출한다.
4. 영업시간을 HH:MM 형식으로 정규화한다.
5. 표준 스키마로 매핑한다.
6. name + address 기준으로 중복 후보를 계산한다.
7. 샘플 5건을 JSON으로 출력한다.
8. 누락 필드와 파싱 실패 reason을 정리한다.

# Quality bar
- 필수 필드 누락 비율이 10%를 넘으면 parser를 미완료로 본다.
- open_hours 파싱 실패 건이 있으면 원문을 raw_hours에 보존한다.
- url은 절대경로로 정규화한다.

# Deliverables
- parser file
- 샘플 출력 5건
- 실패 케이스 목록
