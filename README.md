# cao-profile-registry

인터롭 생태계를 위한 CAO 프로필 패키지.

## 개요

이 저장소는 CAO(Coordination, Automation, Orchestration) 프로필 메타데이터만을 저장하는 **리프 레지스트리**입니다. CAO 런타임이 아니며, 에이전트 오케스트레이션 동작을 구성하는 프로필 정의를 저장합니다. 래퍼 도구는 이 레지스트리의 `manifest.json`을 사용하여 프로필을 검색하고 설치합니다.

## 디렉토리 구조

```
cao-profile-registry/
├── manifest.json              # 모든 프로필 항목이 포함된 레지스트리 매니페스트
├── schemas/
│   └── manifest.schema.json   # 매니페스트 유효성 검사를 위한 JSON 스키마
├── profiles/
│   └── <profile-name>/
│       ├── PROFILE.md         # 프로필 문서
│       └── metadata.json      # 프로필 메타데이터
├── README.md
└── .gitignore
```

## 사용 가능한 프로필

| 정규 ID | 이름 | 버전 | 설명 |
|---------|------|------|------|
| `cao-profile/org/default-cao@0.1.0` | default-cao | 0.1.0 | 표준 AI 에이전트 오케스트레이션을 위한 기본 CAO 프로필 |

## 매니페스트 형식

`manifest.json` 파일은 LeafManifest 구조를 따릅니다:

```json
{
  "registryType": "cao-profile",
  "namespace": "org",
  "version": "0.1.0",
  "channel": "experimental",
  "generatedAt": "2026-03-20T07:00:00Z",
  "items": [...]
}
```

## 새 프로필 추가 방법

1. `profiles/<profile-name>/` 아래에 디렉토리를 생성합니다
2. 프로필 문서가 담긴 `PROFILE.md`를 추가합니다
3. 프로필 메타데이터가 담긴 `metadata.json`을 추가합니다
4. `manifest.json`에 새 프로필 항목을 추가합니다
5. 변경 사항으로 PR을 생성합니다

## 정규 ID 형식

모든 프로필은 다음과 같은 정규 ID 형식을 사용합니다:

```
cao-profile/<namespace>/<name>@<version>
```

예시: `cao-profile/org/default-cao@0.1.0`

## 관련 저장소

- [`registry-hub`](https://github.com/skillinterop/registry-hub) — 리프 레지스트리를 통합하는 최상위 허브
- [`skill-registry`](https://github.com/skillinterop/skill-registry) — 스킬 리프 레지스트리
- [`reprogate-registry`](https://github.com/skillinterop/reprogate-registry) — ReproGate 리프 레지스트리

## 라이선스

MIT
