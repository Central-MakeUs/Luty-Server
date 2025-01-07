# Luty(루티) API Server

Luty API Server는 **사용자 친화적인 API 서비스**를 제공하는 프로젝트입니다. 이 문서에서는 프로젝트의 브랜치 전략과 서버 운영 계획에 대해 안내합니다.

---

## 🛠️ 브랜치 전략

프로젝트는 다음과 같은 브랜치 전략을 사용하여 관리됩니다:

- **`main`**:  
  실제 서비스로 배포되는 안정적인 버전을 관리합니다.  
  이 브랜치에서 직접 작업하지 않습니다.

- **`dev`**:  
  다음 버전의 개발을 진행하는 브랜치입니다.  
  안정화 후 `main` 브랜치로 병합합니다.

- **`feat/{feat_name}`**:  
  새로운 기능을 개발하는 브랜치입니다.  
  기능 개발이 완료되면 `dev` 브랜치로 병합합니다.

- **`hotfix`**:  
  `main` 브랜치에서 발생한 긴급한 버그를 수정하는 브랜치입니다.  
  수정이 완료되면 `main` 브랜치와 `dev` 브랜치에 병합합니다.

---

## 🌐 서버 운영 계획

### 운영 방식
- **`main` 브랜치**  
  실제 서비스를 제공하는 서버에서 운영됩니다.  
  `main` 브랜치의 안정성은 최우선입니다.

- **`dev` 브랜치**  
  개발 중인 기능을 테스트할 수 있는 서버에서 운영됩니다.  
  새로운 기능은 먼저 `dev` 브랜치에서 검증한 후 `main` 브랜치에 병합됩니다.

### 배포 흐름
1. **개발**: 새로운 기능은 `feat/{feat_name}` 브랜치에서 개발을 진행합니다.
2. **테스트**: 기능 개발이 완료되면 `dev` 브랜치에 병합하여 테스트 서버에서 검증합니다.
3. **배포**: 검증이 완료된 버전은 `main` 브랜치로 병합하여 실제 서비스 서버에 배포합니다.

---

## 📄 프로젝트 기여 가이드
1. 새로운 기능 개발 시, `feat/{feat_name}` 브랜치를 생성하세요.
2. 작업 완료 후, `dev` 브랜치로 병합하기 위해 PR(Pull Request)을 생성하세요.
3. 버그 수정은 `hotfix` 브랜치를 사용하고, 완료 후 `main` 및 `dev`에 병합하세요.