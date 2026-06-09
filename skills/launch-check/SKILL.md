---
name: release-readiness
description: 기능, 검증, 문서화가 배포 가능 수준인지 확인할 때 사용
---

# Goal
현재 브랜치가 최소 배포 가능 상태인지 점검한다.

# Required checks
- npm run lint
- npm run test
- npm run build
- README 최신화 여부
- 환경 변수 설명 여부
- 데이터 갱신 방법 문서화 여부

# Product checks
- 검색 가능
- 카테고리 필터 가능
- 거리/평점 정렬 가능
- 영업 종료 가게 기본 숨김
- 가게 링크 이동 가능

# Output
- release blocker
- nice to have
- ready / not ready 판정
