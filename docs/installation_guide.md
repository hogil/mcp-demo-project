# 🛠️ MCP 설치 및 설정 가이드

이 가이드는 MCP (Model Context Protocol) 서버들을 설치하고 설정하는 방법을 단계별로 설명합니다.

## 📋 사전 요구사항

### 필수 소프트웨어:
- **Node.js** 16.0 이상
- **npm** 또는 **yarn**
- **Git**
- **Cursor** 또는 **Claude Desktop**

### 권장 사양:
- **OS**: Windows 10/11, macOS 12+, Ubuntu 20.04+
- **RAM**: 8GB 이상
- **Storage**: 2GB 여유 공간

## 🔧 1. 기본 환경 설정

### Node.js 설치 확인
```bash
# 버전 확인
node --version  # v16.0.0 이상이어야 함
npm --version   # 8.0.0 이상 권장
```

### npx 설치 (필요시)
```bash
npm install -g npx
```

## ⚙️ 2. Cursor 설정

### 2.1 설정 파일 위치
- **Windows**: `%USERPROFILE%\.cursor\mcp.json`
- **macOS**: `~/.cursor/mcp.json`
- **Linux**: `~/.cursor/mcp.json`

### 2.2 설정 파일 생성
```bash
# Windows
cd %USERPROFILE%\.cursor
copy NUL mcp.json

# macOS/Linux
mkdir -p ~/.cursor
touch ~/.cursor/mcp.json
```

### 2.3 기본 설정 적용
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem@latest",
        "C:/Users/YOUR_USERNAME",
        "D:/project"
      ]
    },
    "memory": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-memory@latest"
      ]
    }
  }
}
```

## 🖥️ 3. Claude Desktop 설정

### 3.1 설정 파일 위치
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Linux**: `~/.config/claude/claude_desktop_config.json`

### 3.2 설정 파일 생성
```bash
# Windows
md "%APPDATA%\Claude"
echo {} > "%APPDATA%\Claude\claude_desktop_config.json"

# macOS
mkdir -p "~/Library/Application Support/Claude"
echo '{}' > "~/Library/Application Support/Claude/claude_desktop_config.json"

# Linux
mkdir -p ~/.config/claude
echo '{}' > ~/.config/claude/claude_desktop_config.json
```

## 📚 4. 논문 검색 MCP 서버 설치

### 4.1 ArXiv 서버
```bash
# 테스트 설치
npx @modelcontextprotocol/server-arxiv@latest

# 설정에 추가
"arxiv": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-arxiv@latest"]
}
```

### 4.2 Semantic Scholar 서버
```bash
# 테스트 설치
npx @modelcontextprotocol/server-semantic-scholar@latest

# 설정에 추가
"semantic-scholar": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-semantic-scholar@latest"]
}
```

### 4.3 Papers with Code 서버
```bash
# 테스트 설치
npx @smithery/cli@latest run @hbg/mcp-paperswithcode

# 설정에 추가
"paperswithcode": {
  "command": "npx",
  "args": [
    "-y",
    "@smithery/cli@latest",
    "run",
    "@hbg/mcp-paperswithcode"
  ]
}
```

### 4.4 OpenAlex (Paper Search) 서버
```bash
# 테스트 설치
npx @smithery/cli@latest run @openags/paper-search-mcp

# 설정에 추가
"paper-search": {
  "command": "npx",
  "args": [
    "-y",
    "@smithery/cli@latest",
    "run",
    "@openags/paper-search-mcp"
  ]
}
```

## 🔑 5. API 키 설정

### 5.1 GitHub Personal Access Token
1. GitHub.com → Settings → Developer settings → Personal access tokens
2. "Generate new token" 클릭
3. 권한 선택: `repo`, `user`, `workflow`
4. 토큰 복사하여 설정에 추가:

```json
"github": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-github@latest"],
  "env": {
    "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token_here"
  }
}
```

### 5.2 Hugging Face API Key
1. HuggingFace.co → Settings → Access Tokens
2. "New token" 클릭
3. 권한 선택: `read`, `inference`
4. 토큰 복사하여 설정에 추가:

```json
"huggingface": {
  "command": "npx",
  "args": [
    "-y",
    "@smithery/cli@latest",
    "run",
    "@shreyaskarnik/huggingface-mcp-server"
  ],
  "env": {
    "HUGGINGFACE_API_KEY": "hf_your_token_here"
  }
}
```

### 5.3 기타 API 키들
```json
"exa-search": {
  "env": {
    "EXA_API_KEY": "your_exa_key_here"
  }
},
"mem0": {
  "env": {
    "MEM0_API_KEY": "your_mem0_key_here"
  }
}
```

## ✅ 6. 설치 확인

### 6.1 클라이언트 재시작
1. Cursor 또는 Claude Desktop 완전 종료
2. 재시작
3. MCP 서버 연결 확인

### 6.2 연결 테스트
```
# 각 서버별 테스트 명령어
"filesystem에서 현재 디렉토리 파일 목록 보여줘"
"arxiv에서 transformer 논문 검색해줘"
"github에서 내 리포지토리 목록 보여줘"
"memory에 이 대화 저장해줘"
```

### 6.3 로그 확인
```bash
# Windows
type "%APPDATA%\Claude\logs\mcp.log"

# macOS/Linux
tail -f ~/.config/claude/logs/mcp.log
```

## 🔧 7. 문제 해결

### 7.1 자주 발생하는 오류들

#### "Command not found" 오류
```bash
# npx 재설치
npm install -g npx

# 캐시 정리
npm cache clean --force
```

#### "Permission denied" 오류
```bash
# Windows: 관리자 권한으로 실행
# macOS/Linux: sudo 사용 또는 권한 변경
chmod +x ~/.cursor/mcp.json
```

#### "Connection timeout" 오류
```bash
# 방화벽 설정 확인
# 프록시 설정 확인
npm config get proxy
npm config get https-proxy
```

### 7.2 로그 분석

#### 성공적인 연결 로그:
```
[info] [arxiv] Server connected successfully
[info] [semantic-scholar] Tools loaded: search, get_paper
[info] [github] Authentication successful
```

#### 실패 로그 예시:
```
[error] [arxiv] Connection failed: timeout
[warn] [github] Invalid token or insufficient permissions
[error] [paperswithcode] Package not found
```

### 7.3 성능 최적화

#### 메모리 사용량 줄이기:
```json
{
  "mcpServers": {
    // 사용하지 않는 서버는 주석 처리
    // "puppeteer": { ... },
    
    // 필수 서버만 활성화
    "filesystem": { ... },
    "memory": { ... },
    "arxiv": { ... }
  }
}
```

#### 응답 속도 개선:
```json
{
  "timeout": 30000,  // 30초 타임아웃
  "retries": 3,       // 3회 재시도
  "cache": true       // 캐시 활성화
}
```

## 🔄 8. 업데이트 및 유지보수

### 8.1 MCP 서버 업데이트
```bash
# 전체 업데이트
npm update -g @modelcontextprotocol/*
npm update -g @smithery/cli

# 개별 업데이트
npx @modelcontextprotocol/server-arxiv@latest
```

### 8.2 설정 백업
```bash
# Windows
copy "%USERPROFILE%\.cursor\mcp.json" "mcp_backup.json"
copy "%APPDATA%\Claude\claude_desktop_config.json" "claude_backup.json"

# macOS/Linux
cp ~/.cursor/mcp.json mcp_backup.json
cp "~/Library/Application Support/Claude/claude_desktop_config.json" claude_backup.json
```

### 8.3 정기 점검
- **주간**: 로그 파일 확인
- **월간**: MCP 서버 업데이트
- **분기**: 설정 파일 백업

---

## 📞 지원 및 문의

### 공식 문서:
- [MCP Specification](https://modelcontextprotocol.io/)
- [Anthropic MCP Guide](https://docs.anthropic.com/claude/docs/mcp)

### 커뮤니티:
- [GitHub Issues](https://github.com/hogil/mcp-demo-project/issues)
- [Discord Community](https://discord.gg/mcp)

### 이메일 지원:
- 기술 지원: support@mcp-demo.com
- 일반 문의: info@mcp-demo.com

---

✅ **설치 완료 후 [README.md](../README.md)의 사용 예시를 참고하여 MCP를 활용해보세요!**