# MCP Test Project Documentation

## 프로젝트 개요

이 프로젝트는 Next.js와 Supabase를 기반으로 한 애플리케이션으로, Model Context Protocol(MCP)을 활용하여 GitHub와 Supabase를 연동하는 테스트 프로젝트입니다.

## 시스템 아키텍처

이 프로젝트는 다음과 같은 구조로 구성되어 있습니다:

1. **프론트엔드**: Next.js (App Router)
2. **백엔드 서비스**: Supabase
3. **인증**: Supabase Auth
4. **디자인 시스템**: Tailwind CSS 및 shadcn/ui
5. **프로토콜 통합**: Model Context Protocol (MCP)

## 프로젝트 설정

### 초기 설정 단계

1. 프로젝트 GitHub 저장소 생성: `superhan-dev/mcp-test`
2. Next.js 프로젝트 초기화 (with Supabase)
3. VS Code MCP 설정 추가 (`.vscode/mcp.json`)
4. `.gitignore` 파일 설정

### 환경 변수 설정

`.env.local` 파일에 다음 환경 변수를 설정해야 합니다:

```
NEXT_PUBLIC_SUPABASE_URL=[Supabase 프로젝트 URL]
NEXT_PUBLIC_SUPABASE_ANON_KEY=[Supabase 프로젝트 ANON KEY]
```

## 주요 기능

1. **인증 시스템**: 회원가입, 로그인, 비밀번호 재설정
2. **보호된 페이지**: 로그인 상태에서만 접근 가능한 영역
3. **테마 지원**: 라이트/다크 모드 전환 기능

## MCP(Model Context Protocol) 통합

### MCP 설정

`.vscode/mcp.json` 파일을 통해 Supabase MCP 서버와 연동하였습니다:

```json
{
  "inputs": [
    {
      "type": "promptString",
      "id": "supabase-access-token",
      "description": "Supabase personal access token",
      "password": true
    }
  ],
  "servers": {
    "supabase": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@supabase/mcp-server-supabase@latest"],
      "env": {
        "SUPABASE_ACCESS_TOKEN": "${input:supabase-access-token}"
      }
    }
  }
}
```

### MCP 사용 방법

1. VS Code에서 Command Palette를 열고 (Ctrl+Shift+P)
2. "MCP: Connect to Server" 명령 선택
3. "supabase" 서버 선택
4. Supabase Access Token 입력
5. 연결 후 MCP 기능 사용

## 향후 개발 계획

YouTube 튜토리얼 [AI in Production with the Model Context Protocol](https://www.youtube.com/watch?v=wXXTz2eZIoM)을 바탕으로 다음과 같은 기능들을 추가할 예정입니다:

1. **MCP 통합 강화**:

   - 사용자 정의 MCP 서버 개발
   - 멀티 모델 지원 추가
   - 응답 형식 커스터마이징

2. **AI 기능 확장**:

   - 데이터베이스 스키마 자동 분석
   - 사용자 쿼리를 SQL로 변환
   - 코드 자동 생성 및 보완

3. **추가 개발 계획**:

   - 실시간 협업 기능
   - 쿼리 결과 시각화 도구
   - API 자동 문서화

4. **보안 강화**:
   - MCP 통신 암호화
   - 토큰 관리 개선
   - 권한 시스템 구현

## 참고 자료

1. [Next.js 공식 문서](https://nextjs.org/docs)
2. [Supabase 공식 문서](https://supabase.io/docs)
3. [Model Context Protocol 문서](https://modelcontextprotocol.github.io/docs)
4. [AI in Production with the Model Context Protocol](https://www.youtube.com/watch?v=wXXTz2eZIoM) - YouTube 튜토리얼
