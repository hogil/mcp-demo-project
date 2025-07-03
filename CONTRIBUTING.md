# 🤝 기여 가이드 (Contributing Guide)

이 프로젝트에 기여해주셔서 감사합니다! 다음 가이드라인을 따라 기여해주시면 됩니다.

## 📋 기여 방법

### 1. 이슈 리포팅
버그를 발견하거나 새로운 기능을 제안하고 싶다면:

1. [Issues](https://github.com/hogil/mcp-demo-project/issues)에서 중복되는 이슈가 있는지 확인
2. 새로운 이슈 생성
3. 다음 정보 포함:
   - 문제 설명
   - 재현 단계
   - 예상 결과 vs 실제 결과
   - 환경 정보 (OS, Node.js 버전 등)

### 2. 풀 리퀘스트
코드 기여를 원한다면:

1. 이 저장소를 Fork
2. 새로운 브랜치 생성 (`git checkout -b feature/amazing-feature`)
3. 변경사항 커밋 (`git commit -m 'Add some amazing feature'`)
4. 브랜치에 Push (`git push origin feature/amazing-feature`)
5. Pull Request 생성

## 🔧 개발 환경 설정

### 필수 요구사항
- Node.js 16.0+
- npm 또는 yarn
- Git

### 로컬 설정
```bash
# 저장소 클론
git clone https://github.com/hogil/mcp-demo-project.git
cd mcp-demo-project

# 의존성 설치 (있다면)
npm install

# MCP 서버 테스트
npx @modelcontextprotocol/server-arxiv@latest
```

## 📝 코딩 스타일

### JSON 설정 파일
```json
{
  "들여쓰기": "2칸 스페이스",
  "따옴표": "쌍따옴표 사용",
  "끝에_쉼표": false,
  "키_정렬": "알파벳 순서"
}
```

### Markdown 문서
- 제목은 `#`, `##`, `###` 형태로 계층화
- 코드 블록은 언어 지정 (```json, ```bash 등)
- 이모지 적극 활용 🚀
- 한글과 영어 사이에 공백 추가

### 커밋 메시지
```
형태: 간단한 설명

더 자세한 설명 (선택사항)

예시:
add: ArXiv MCP 서버 설정 추가
fix: GitHub 토큰 인증 오류 수정
docs: 설치 가이드 업데이트
```

## 🧪 테스트

### MCP 서버 테스트
새로운 MCP 서버를 추가할 때:

1. **연결 테스트**
```bash
npx your-mcp-server@latest
```

2. **기능 테스트**
```
"새로운 MCP 서버 테스트해줘"
```

3. **에러 처리 테스트**
- 잘못된 API 키
- 네트워크 오류
- 타임아웃 상황

### 문서 테스트
- 링크가 모두 작동하는지 확인
- 설치 가이드를 따라 실제로 설치해보기
- 코드 예제가 정확한지 확인

## 📚 문서 기여

### 새로운 MCP 서버 추가
1. `configs/` 폴더에 설정 예제 추가
2. `examples/` 폴더에 사용 예시 추가
3. `models/` 폴더에 관련 모델 정보 추가
4. `README.md` 업데이트

### 번역
현재 한국어로 작성되어 있지만, 다른 언어 번역도 환영합니다:
- `README.en.md` (영어)
- `README.ja.md` (일본어)
- `README.zh.md` (중국어)

## 🐛 버그 수정

### 우선순위
1. **Critical**: 보안 취약점, 데이터 손실
2. **High**: 주요 기능 동작 안함
3. **Medium**: 일부 기능 오작동
4. **Low**: UI/UX 개선, 문서 오타

### 수정 프로세스
1. 이슈에서 버그 확인
2. 재현 가능한 테스트 케이스 작성
3. 수정 구현
4. 테스트 통과 확인
5. PR 생성

## ✨ 새로운 기능

### 기능 제안
새로운 기능을 제안할 때:

1. **문제 정의**: 어떤 문제를 해결하나요?
2. **해결책**: 어떻게 해결할 건가요?
3. **사용자 스토리**: 사용자가 어떻게 사용하나요?
4. **기술적 고려사항**: 구현 복잡도, 성능 영향 등

### 구현 가이드라인
- 기존 코드 스타일 유지
- 적절한 에러 처리
- 사용자 친화적인 메시지
- 문서화 포함

## 🔍 MCP 서버 기여

### 새로운 MCP 서버 추가
새로운 MCP 서버를 추가하려면:

1. **서버 정보**
   - 이름, 설명, 기능
   - 필요한 API 키
   - 설치 방법

2. **설정 예제**
```json
"your-server": {
  "command": "npx",
  "args": ["-y", "your-mcp-server@latest"],
  "env": {
    "API_KEY": "your_api_key_here"
  }
}
```

3. **사용 예시**
```
"your-server에서 데이터 검색해줘"
```

4. **테스트**
   - 연결 테스트
   - 기본 기능 테스트
   - 에러 상황 테스트

## 📊 성능 최적화

### 목표
- MCP 서버 응답 시간: < 2초
- 메모리 사용량: < 500MB
- 동시 연결: 10개 이상

### 측정 방법
```bash
# 응답 시간 측정
time npx your-mcp-server@latest

# 메모리 사용량 측정
ps aux | grep mcp
```

## 🛡️ 보안

### API 키 관리
- **절대 하드코딩 금지**
- 환경 변수 사용
- `.gitignore`에 키 파일 추가
- 예제에서는 `your_key_here` 사용

### 민감한 정보
- 개인 정보 제거
- 로그에서 토큰 마스킹
- HTTPS 사용 강제

## 🌟 좋은 기여 예시

### 문서 개선
- 설치 가이드 상세화
- 에러 해결 방법 추가
- 사용 예시 다양화

### 코드 개선
- 새로운 MCP 서버 지원
- 에러 처리 개선
- 성능 최적화

### 커뮤니티
- 이슈 답변
- 코드 리뷰
- 튜토리얼 작성

## 📞 문의

### 질문이 있다면:
1. [Issues](https://github.com/hogil/mcp-demo-project/issues)에서 질문
2. [Discussions](https://github.com/hogil/mcp-demo-project/discussions)에서 토론
3. 이메일: contribute@mcp-demo.com

### 빠른 답변을 위해:
- 구체적인 질문
- 관련 코드나 설정 포함
- 환경 정보 제공

---

## 🏆 기여자 인정

모든 기여자는 다음과 같이 인정받습니다:

1. **README.md**에 기여자 목록 추가
2. **CONTRIBUTORS.md** 파일에 상세 정보
3. **GitHub Contributors** 페이지에 자동 표시
4. **릴리즈 노트**에 감사 인사

### 기여 종류
- 💻 코드
- 📖 문서
- 🐛 버그 리포트
- 💡 아이디어
- 🤔 질문/토론
- 🎨 디자인
- 🌍 번역

---

**🎉 여러분의 기여를 기다리고 있습니다! 함께 더 나은 MCP 생태계를 만들어 가요! 🚀**