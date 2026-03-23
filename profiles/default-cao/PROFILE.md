# default-cao

표준 AI 에이전트 오케스트레이션을 위한 기본 CAO 프로필.

## 개요

이 프로필은 CAO(Coordination, Automation, Orchestration) 워크플로우에 대한 기본 구성을 제공합니다. 특별한 커스터마이징 없이 AI 에이전트 조율을 위한 표준 설정을 정의합니다.

## 구성

| 설정 | 값 |
|------|-----|
| 대상 에이전트 | claude, generic |
| 오케스트레이션 모드 | sequential |

## 사용법

```yaml
profile: cao-profile/org/default-cao
```

## 호환성

- 래퍼 CLI: >=0.1.0
- CAO 런타임: >=0.1.0

## 라이선스

MIT
