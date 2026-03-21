# EVM(이더리움 가상 머신) MCP(모델 컨텍스트 프로토콜) Server

60개 이상의 EVM(이더리움 가상 머신) 호환 네트워크에서 블록체인 서비스를 제공하는 포괄적인 MCP(모델 컨텍스트 프로토콜) 서버입니다. 이 서버는 AI(인공지능) 에이전트가 22개의 도구와 10개의 AI(인공지능) 가이드 프롬프트를 통해 단일 인터페이스로 Ethereum, Optimism, Arbitrum, Base, Polygon 및 기타 여러 EVM(이더리움 가상 머신) 체인과 상호 작용할 수 있도록 합니다.

## 📋 목차 (Contents)

- [개요 (Overview)](https://www.google.com/search?q=%23🔭-개요)
- [주요 기능 (Features)](https://www.google.com/search?q=%23✨-주요-기능)
- [지원 네트워크 (Supported Networks)](https://www.google.com/search?q=%23🌐-지원-네트워크)
- [사전 요구 사항 (Prerequisites)](https://www.google.com/search?q=%23🛠️-사전-요구-사항)
- [설치 (Installation)](https://www.google.com/search?q=%23📦-설치)
- [구성 (Configuration)](https://www.google.com/search?q=%23⚙️-구성)
  - [환경 변수 (Environment Variables)](https://www.google.com/search?q=%23환경-변수)
  - [서버 구성 (Server Configuration)](https://www.google.com/search?q=%23서버-구성)
- [사용법 (Usage)](https://www.google.com/search?q=%23🚀-사용법)
- [API 참조 (API Reference)](https://www.google.com/search?q=%23📚-api응용-프로그램-프로그래밍-인터페이스-참조)
  - [도구 (Tools)](https://www.google.com/search?q=%23도구)
  - [프롬프트 (Prompts)](https://www.google.com/search?q=%23프롬프트)
  - [리소스 (Resources)](https://www.google.com/search?q=%23리소스)
- [보안 고려 사항 (Security Considerations)](https://www.google.com/search?q=%23🔒-보안-고려-사항)
- [프로젝트 구조 (Project Structure)](https://www.google.com/search?q=%23📁-프로젝트-구조)
- [개발 (Development)](https://www.google.com/search?q=%23🛠️-개발)
- [라이선스 (License)](https://www.google.com/search?q=%23📄-라이선스)

## 🔭 개요

MCP(모델 컨텍스트 프로토콜) EVM(이더리움 가상 머신) 서버는 MCP(모델 컨텍스트 프로토콜)를 활용하여 AI(인공지능) 에이전트에게 블록체인 서비스를 제공합니다. 다음과 같은 다양한 서비스를 지원합니다:

- 블록체인 상태 읽기 (잔고, 트랜잭션, 블록 등)
- 블록 탐색기에서 **자동으로 ABI(응용 프로그램 이진 인터페이스)를 가져와** 스마트 컨트랙트와 상호 작용
- 토큰 전송 (네이티브, ERC20, ERC721, ERC1155)
- 토큰 메타데이터 및 잔고 조회
- 60개 이상의 EVM(이더리움 가상 머신) 네트워크(메인넷 34개 + 테스트넷 26개)에서 체인별 서비스 제공
- 모든 주소 매개변수에 대한 **ENS(이더리움 네임 서비스) 이름 확인** (주소 대신 'vitalik.eth'와 같이 사람이 읽을 수 있는 이름 사용)
- 복잡한 워크플로우를 안내하는 **AI(인공지능) 친화적인 프롬프트**

모든 서비스는 MCP(모델 컨텍스트 프로토콜) 도구, 리소스 및 프롬프트의 일관된 인터페이스를 통해 노출되므로, AI(인공지능) 에이전트가 블록체인 기능을 쉽게 발견하고 사용할 수 있습니다. **Ethereum 주소를 허용하는 모든 도구는 ENS(이더리움 네임 서비스) 이름도 지원**하며, 백그라운드에서 자동으로 주소로 변환합니다. 서버에는 지능형 ABI(응용 프로그램 이진 인터페이스) 가져오기 기능이 포함되어 있어 사전에 컨트랙트 ABI(응용 프로그램 이진 인터페이스)를 알 필요가 없습니다.

## ✨ 주요 기능

## 블록체인 데이터 접근 (Blockchain Data Access)

- 60개 이상의 EVM(이더리움 가상 머신) 호환 네트워크(메인넷 34개 + 테스트넷 26개)에 대한 **다중 체인 지원**
- blockNumber, chainId 및 RPC(원격 프로시저 호출)를 포함한 **체인 정보**
- 번호, 해시 또는 최신 상태를 통한 **블록 데이터** 접근
- 디코딩된 로그가 포함된 **트랜잭션 세부 정보** 및 영수증
- 네이티브 토큰 및 모든 토큰 표준에 대한 **주소 잔고**
- 사람이 읽을 수 있는 Ethereum 주소를 위한 **ENS(이더리움 네임 서비스) 변환** ('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045' 대신 'vitalik.eth' 사용)

## 토큰 서비스 (Token services)

- **ERC20 토큰**
  - 토큰 메타데이터(이름, 기호, 소수점 자리, 공급량) 가져오기
  - 토큰 잔고 확인
  - 주소 간 토큰 전송
  - 지출 허용량(allowance) 승인
- **NFT(대체 불가능 토큰) (ERC721)**
  - 컬렉션 및 토큰 메타데이터 가져오기
  - 토큰 소유권 확인
  - 주소 간 NFT(대체 불가능 토큰) 전송
  - 토큰 URI(통합 자원 식별자) 검색 및 보유량 계산
- **다중 토큰 (ERC1155)**
  - 토큰 잔고 및 메타데이터 가져오기
  - 수량과 함께 토큰 전송
  - 토큰 URI(통합 자원 식별자) 접근

## 스마트 컨트랙트 상호작용 (Smart Contract Interactions)

- view/pure 함수를 통한 **컨트랙트 상태 읽기**
- **컨트랙트에 쓰기** - 자동 ABI(응용 프로그램 이진 인터페이스) 가져오기를 통해 상태 변경 함수 실행
- EOA(외부 소유 계정)와 구별하기 위한 **컨트랙트 검증**
- **이벤트 로그** 검색 및 필터링
- 모든 60개 이상의 네트워크에 걸쳐 Etherscan v2 API(응용 프로그램 프로그래밍 인터페이스)에서 **자동 ABI(응용 프로그램 이진 인터페이스) 가져오기** (사전에 ABI를 알 필요 없음)
- 함수 발견 기능을 포함한 **ABI(응용 프로그램 이진 인터페이스) 파싱 및 유효성 검사**

## 포괄적인 트랜잭션 지원 (Comprehensive Transaction Support)

- **유연한 지갑 지원** - HD(계층적 결정론적) 경로를 지원하는 프라이빗 키 또는 Mnemonic(니모닉, BIP-39)으로 구성 가능
- 모든 지원 네트워크에서 **네이티브 토큰 전송**
- 트랜잭션 계획을 위한 **가스비 추정**
- **트랜잭션 상태** 및 영수증 정보
- 설명이 포함된 메시지와 함께 **오류 처리**

## 메시지 서명 기능 (Message Signing Capabilities)

- **개인 메시지 서명 (Personal Message Signing)** - 인증 및 확인을 위해 임의의 메시지에 서명
- **EIP-712 형식 데이터 서명 (EIP-712 Typed Data Signing)** - 가스 없는 트랜잭션 및 메타 트랜잭션을 위한 구조화된 데이터 서명
- **SIWE(이더리움으로 로그인) 지원** - Sign-In With Ethereum(이더리움으로 로그인) 인증 흐름 활성화
- **퍼밋 서명 (Permit Signatures)** - 가스 없는 토큰 작업을 위한 오프체인 승인 생성
- **메타 트랜잭션 지원 (Meta-Transaction Support)** - 릴레이 서비스 및 가스 없는 전송을 위한 트랜잭션 데이터 서명

## AI(인공지능) 가이드 워크플로우 (프롬프트)

- **트랜잭션 준비** - 전송 계획 및 실행을 위한 안내
- **지갑 분석** - 지갑 활동 및 보유 자산 분석을 위한 도구
- **스마트 컨트랙트 탐색** - 대화형 ABI(응용 프로그램 이진 인터페이스) 가져오기 및 컨트랙트 분석
- **컨트랙트 상호작용** - 스마트 컨트랙트에서 쓰기 작업의 안전한 실행
- **네트워크 정보** - EVM(이더리움 가상 머신) 네트워크 및 비교 학습
- **승인 감사** - 토큰 승인 검토 및 관리
- **오류 진단** - 트랜잭션 실패 문제 해결

## 🌐 지원 네트워크 (Supported Networks)

## 메인넷 (Mainnets)

- Ethereum (ETH)
- Optimism (OP)
- Arbitrum (ARB)
- Arbitrum Nova
- Base
- Polygon (MATIC)
- Polygon zkEVM
- Avalanche (AVAX)
- Binance Smart Chain (BSC)
- zkSync Era
- Linea
- Celo
- Gnosis (xDai)
- Fantom (FTM)
- Filecoin (FIL)
- Moonbeam
- Moonriver
- Cronos
- Scroll
- Mantle
- Manta
- Blast
- Fraxtal
- Mode
- Metis
- Kroma
- Zora
- Aurora
- Canto
- Flow
- Lumia

## 테스트넷 (Testnets)

- Sepolia
- Optimism Sepolia
- Arbitrum Sepolia
- Base Sepolia
- Polygon Amoy
- Avalanche Fuji
- BSC Testnet
- zkSync Sepolia
- Linea Sepolia
- Scroll Sepolia
- Mantle Sepolia
- Manta Sepolia
- Blast Sepolia
- Fraxtal Testnet
- Mode Testnet
- Metis Sepolia
- Kroma Sepolia
- Zora Sepolia
- Celo Alfajores
- Goerli
- Holesky
- Flow Testnet
- Filecoin Calibration
- Lumia Testnet

## 🛠️ 사전 요구 사항 (Prerequisites)

- [Bun](https://bun.sh/) 1.0.0 이상 (권장)
- Node.js 20.0.0 이상 (Bun을 사용하지 않는 경우)
- 선택 사항: ABI(응용 프로그램 이진 인터페이스)를 가져오기 위한 [Etherscan API(응용 프로그램 프로그래밍 인터페이스) 키](https://etherscan.io/apis)

## 📦 설치 (Installation)

Bash

```
# 저장소 복제
git clone https://github.com/mcpdotdirect/mcp-evm-server.git
cd mcp-evm-server

# Bun으로 종속성 설치
bun install

# 또는 npm 사용
npm install
```

## ⚙️ 구성 (Configuration)

## 환경 변수 (Environment Variables)

서버는 다음과 같은 환경 변수를 사용합니다. 쓰기 작업 및 ABI(응용 프로그램 이진 인터페이스)를 가져오려면 다음 변수를 구성해야 합니다:

#### 지갑 구성 (쓰기 작업용)

프라이빗 키 또는 Mnemonic(니모닉) 문구 **중 하나**를 사용하여 지갑을 구성할 수 있습니다:

**옵션 1: 프라이빗 키 (Private Key)**

Bash

```
export EVM_PRIVATE_KEY="0x..." # 16진수 형식의 프라이빗 키 (0x 접두사는 선택 사항)
```

**옵션 2: 니모닉 문구 (Mnemonic Phrase - HD 지갑 권장)**

Bash

```
export EVM_MNEMONIC="word1 word2 word3 ... word12" # 12개 또는 24개 단어의 BIP-39 니모닉
export EVM_ACCOUNT_INDEX="0" # 선택 사항: HD(계층적 결정론적) 지갑 파생을 위한 계정 인덱스 (기본값: 0)
```

니모닉 옵션은 HD(계층적 결정론적) 지갑 파생을 지원합니다:

- BIP-39 표준 니모닉 문구(12개 또는 24개 단어) 사용
- BIP-44 파생 경로 지원: `m/44'/60'/0'/0/{accountIndex}`
- `EVM_ACCOUNT_INDEX`를 사용하면 동일한 니모닉에서 여러 계정을 파생시킬 수 있습니다.
- 기본 계정 인덱스는 0(첫 번째 계정)입니다.

**지갑이 사용되는 곳:**

- 네이티브 토큰 전송 (`transfer_native` 도구)
- ERC20 토큰 전송 (`transfer_erc20` 도구)
- 토큰 지출 승인 (`approve_token_spending` 도구)
- 스마트 컨트랙트에 쓰기 (`write_contract` 도구)
- 인증을 위한 메시지 서명 (`sign_message` 도구)
- 가스 없는 트랜잭션을 위한 구조화된 데이터 서명 (`sign_typed_data` 도구)

⚠️ **보안 (Security)**:

- 프라이빗 키나 니모닉을 절대 버전 관리에 커밋하지 마세요.
- 환경 변수 또는 안전한 키 관리 시스템을 사용하세요.
- 니모닉을 안전하게 보관하세요 - 니모닉은 파생된 모든 계정에 대한 접근 권한을 제공합니다.
- 다른 목적을 위해 다른 계정 인덱스를 사용하는 것을 고려해 보세요.

#### API(응용 프로그램 프로그래밍 인터페이스) 키 (ABI 가져오기용)

Bash

```
export ETHERSCAN_API_KEY="your-api-key-here"
```

이 API(응용 프로그램 프로그래밍 인터페이스) 키는 선택 사항이지만 다음과 같은 작업에 필요합니다:

- 블록 탐색기에서 자동 ABI(응용 프로그램 이진 인터페이스) 가져오기 (`get_contract_abi` 도구)
- 컨트랙트를 읽을 때 자동 ABI(응용 프로그램 이진 인터페이스) 가져오기 (`read_contract` 도구와 `abiJson` 매개변수 사용 시)
- `fetch_and_analyze_abi` 프롬프트 사용 시

여기에서 무료 API(응용 프로그램 프로그래밍 인터페이스) 키를 받으세요:

- [Etherscan](https://etherscan.io/apis) - Ethereum 및 호환 체인용
- 동일한 키가 Etherscan v2 API(응용 프로그램 프로그래밍 인터페이스)를 통해 모든 60개 이상의 EVM(이더리움 가상 머신) 네트워크에서 작동합니다.

## 서버 구성 (Server Configuration)

서버는 다음과 같은 기본 구성을 사용합니다:

- **기본 Chain ID**: 1 (Ethereum Mainnet)
- **서버 포트**: 3001
- **서버 호스트**: 0.0.0.0 (모든 네트워크 인터페이스에서 접근 가능)

이러한 값은 애플리케이션에 하드코딩되어 있습니다. 수정해야 할 경우 다음 파일을 편집할 수 있습니다:

- 체인 구성: `src/core/chains.ts`
- 서버 구성: `src/server/http-server.ts`

## 🚀 사용법 (Usage)

## npx 사용 (설치 불필요)

설치하지 않고도 npx를 사용하여 MCP(모델 컨텍스트 프로토콜) EVM(이더리움 가상 머신) 서버를 직접 실행할 수 있습니다:

Bash

```
# stdio 모드로 서버 실행 (CLI(명령줄 인터페이스) 도구용)
npx @mcpdotdirect/evm-mcp-server

# HTTP(하이퍼텍스트 전송 규약) 모드로 서버 실행 (웹 애플리케이션용)
npx @mcpdotdirect/evm-mcp-server --http
```

## 로컬에서 서버 실행

stdio를 사용하여 서버 시작 (CLI(명령줄 인터페이스) 도구 임베딩용):

Bash

```
# stdio 서버 시작
bun start

# 자동 재시작이 지원되는 개발 모드
bun dev
```

또는 웹 애플리케이션을 위해 SSE(서버 전송 이벤트)를 사용하는 HTTP(하이퍼텍스트 전송 규약) 서버 시작:

Bash

```
# HTTP(하이퍼텍스트 전송 규약) 서버 시작
bun start:http

# 자동 재시작이 지원되는 개발 모드
bun dev:http
```

## 서버 연결

MCP(모델 컨텍스트 프로토콜) 호환 클라이언트를 사용하여 이 MCP(모델 컨텍스트 프로토콜) 서버에 연결하세요. 테스트 및 디버깅을 위해서는 [MCP Inspector](https://github.com/modelcontextprotocol/inspector)를 사용할 수 있습니다.

## Cursor에서 연결

Cursor에서 MCP(모델 컨텍스트 프로토콜) 서버에 연결하려면:

1. Cursor를 열고 Settings(설정, 왼쪽 하단의 톱니바퀴 아이콘)로 이동합니다.
2. 왼쪽 사이드바에서 "Features"를 클릭합니다.
3. "MCP Servers" 섹션으로 스크롤을 내립니다.
4. "Add new MCP server"를 클릭합니다.
5. 다음 세부 정보를 입력합니다:
   - Server name: `evm-mcp-server`
   - Type: `command`
   - Command: `npx @mcpdotdirect/evm-mcp-server`
6. "Save"를 클릭합니다.

연결이 완료되면 Cursor 내에서 직접 MCP(모델 컨텍스트 프로토콜) 서버의 기능을 사용할 수 있습니다. 서버는 MCP Servers 목록에 표시되며 필요에 따라 활성화/비활성화할 수 있습니다.

## Cursor와 함께 mcp.json 사용

팀과 공유하거나 프로젝트 전반에서 사용할 수 있는 더 이식성 있는 구성을 원한다면, 프로젝트 루트 디렉터리에 `.cursor/mcp.json` 파일을 생성할 수 있습니다:

JSON

```
{
  "mcpServers": {
    "evm-mcp-server": {
      "command": "npx",
      "args": ["-y", "@mcpdotdirect/evm-mcp-server"]
    },
    "evm-mcp-http": {
      "command": "npx",
      "args": ["-y", "@mcpdotdirect/evm-mcp-server", "--http"]
    }
  }
}
```

이 파일을 프로젝트의 `.cursor` 디렉터리에 넣으면(없으면 생성), Cursor가 해당 프로젝트에서 작업할 때 자동으로 이 MCP(모델 컨텍스트 프로토콜) 서버 구성을 감지하고 사용합니다. 이 접근 방식은 다음과 같은 이점이 있습니다:

1. 팀과 MCP(모델 컨텍스트 프로토콜) 구성 공유
2. MCP(모델 컨텍스트 프로토콜) 설정 버전 관리
3. 프로젝트마다 다른 서버 구성 사용

## 예시: SSE(서버 전송 이벤트)를 사용한 HTTP(하이퍼텍스트 전송 규약) 모드

웹 애플리케이션을 개발 중이고 SSE(서버 전송 이벤트)를 통해 HTTP(하이퍼텍스트 전송 규약) 서버에 연결하려면 다음 구성을 사용할 수 있습니다:

JSON

```
{
  "mcpServers": {
    "evm-mcp-sse": {
      "url": "http://localhost:3001/sse"
    }
  }
}
```

이 구성은 HTTP(하이퍼텍스트 전송 규약) 서버의 SSE(서버 전송 이벤트) 엔드포인트에 직접 연결되며, 다음 상황에서 유용합니다:

- 브라우저에서 MCP(모델 컨텍스트 프로토콜) 서버에 연결해야 하는 웹 애플리케이션
- 로컬 명령어 실행이 이상적이지 않은 환경
- 여러 사용자나 애플리케이션 간에 단일 MCP(모델 컨텍스트 프로토콜) 서버 인스턴스 공유

이 구성을 사용하려면:

1. 존재하지 않는 경우 프로젝트 루트에 `.cursor` 디렉터리를 생성합니다.
2. 위 JSON(자바스크립트 객체 표기법)을 `.cursor` 디렉터리 내에 `mcp.json`으로 저장합니다.
3. Cursor를 다시 시작하거나 프로젝트를 엽니다.
4. Cursor가 구성을 감지하고 서버를 활성화할지 묻습니다.

## 예시: Cursor에서 MCP(모델 컨텍스트 프로토콜) 서버 사용

`mcp.json`으로 MCP(모델 컨텍스트 프로토콜) 서버를 구성한 후, Cursor에서 쉽게 사용할 수 있습니다. 다음은 워크플로우 예시입니다:

1. 프로젝트에 새 JavaScript/TypeScript 파일을 만듭니다:

JavaScript

```
// blockchain-example.js
async function main() {
  try {
    // ENS를 사용하여 주소의 ETH 잔고 가져오기
    console.log("Getting ETH balance for vitalik.eth...");

    // Cursor와 함께 사용할 때는 간단하게 Cursor에게 다음과 같이 요청할 수 있습니다:
    // "메인넷에서 vitalik.eth의 ETH 잔고를 확인해줘"
    // 또는 "내 지갑에서 vitalik.eth로 0.1 ETH를 전송해줘"

    // Cursor는 추가 코드 작성 없이 이러한 작업을 실행하기 위해 MCP 서버를 사용합니다.

    // 이것이 MCP 통합의 강력함입니다 - 여러분의 AI 어시스턴트가 
    // 자연어를 통해 블록체인 데이터 및 작업과 직접 상호 작용하고 실행할 수 있습니다.
  } catch (error) {
    console.error("Error:", error.message);
  }
}

main();
```

1. 파일을 Cursor에 열어둔 상태로 다음과 같이 요청할 수 있습니다:
   - "vitalik.eth의 현재 ETH 잔고를 확인해줘"
   - "Ethereum에서 USDC의 가격을 조회해줘"
   - "Optimism의 최신 블록을 보여줘"
   - "0x1234...가 컨트랙트 주소인지 확인해줘"
2. Cursor는 MCP(모델 컨텍스트 프로토콜) 서버를 사용하여 이러한 작업을 실행하고 대화 내에서 직접 결과를 반환합니다.

MCP(모델 컨텍스트 프로토콜) 서버는 모든 블록체인 통신을 처리하는 동시에 Cursor가 자연어를 통해 블록체인 관련 작업을 이해하고 실행할 수 있도록 합니다.

## Claude CLI(명령줄 인터페이스)를 사용한 연결

Claude CLI(명령줄 인터페이스)를 사용하는 경우 단 두 개의 명령으로 MCP(모델 컨텍스트 프로토콜) 서버에 연결할 수 있습니다:

Bash

```
# MCP 서버 추가
claude mcp add evm-mcp-server npx @mcpdotdirect/evm-mcp-server

# MCP 서버가 활성화된 상태로 Claude 시작
claude
```

## 예시: ENS(이더리움 네임 서비스)를 사용한 토큰 잔고 가져오기

JavaScript

```
// ENS를 사용하여 토큰 잔고를 확인하기 위해 MCP 클라이언트를 사용하는 예제
const mcp = new McpClient("http://localhost:3000");

const result = await mcp.invokeTool("get-token-balance", {
  tokenAddress: "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48", // Ethereum의 USDC
  ownerAddress: "vitalik.eth", // 주소 대신 ENS 이름 사용
  network: "ethereum",
});

console.log(result);
// {
//   tokenAddress: "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48",
//   owner: "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045",
//   network: "ethereum",
//   raw: "1000000000",
//   formatted: "1000",
//   symbol: "USDC",
//   decimals: 6
// }
```

## 예시: ENS(이더리움 네임 서비스) 이름 확인

JavaScript

```
// ENS 이름을 주소로 변환하기 위해 MCP 클라이언트를 사용하는 예제
const mcp = new McpClient("http://localhost:3000");

const result = await mcp.invokeTool("resolve-ens", {
  ensName: "vitalik.eth",
  network: "ethereum",
});

console.log(result);
// {
//   ensName: "vitalik.eth",
//   normalizedName: "vitalik.eth",
//   resolvedAddress: "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045",
//   network: "ethereum"
// }
```

## 예시: Multicall을 사용한 다중 호출 일괄 처리

JavaScript

```
// 단일 RPC 호출로 여러 컨트랙트 읽기를 일괄 처리하기 위해 multicall을 사용하는 예제
const mcp = new McpClient("http://localhost:3000");

const result = await mcp.invokeTool("multicall", {
  network: "ethereum",
  calls: [
    {
      contractAddress: "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48", // USDC
      functionName: "balanceOf",
      args: ["0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045"],
    },
    {
      contractAddress: "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48", // USDC
      functionName: "symbol",
    },
    {
      contractAddress: "0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48", // USDC
      functionName: "decimals",
    },
  ],
});

console.log(result);
// {
//   network: "ethereum",
//   totalCalls: 3,
//   successfulCalls: 3,
//   failedCalls: 0,
//   results: [
//     { contractAddress: "0xA0b...", functionName: "balanceOf", result: "1000000000", status: "success" },
//     { contractAddress: "0xA0b...", functionName: "symbol", result: "USDC", status: "success" },
//     { contractAddress: "0xA0b...", functionName: "decimals", result: "6", status: "success" }
//   ]
// }
```

## 📚 API(응용 프로그램 프로그래밍 인터페이스) 참조

## 도구 (Tools)

서버는 에이전트를 위해 집중화된 25개의 MCP(모델 컨텍스트 프로토콜) 도구를 제공합니다. **주소 매개변수를 허용하는 모든 도구는 Ethereum 주소와 ENS(이더리움 네임 서비스) 이름을 모두 지원합니다.**

#### 지갑 정보

| **도구 이름 (Tool Name)** | **설명**                                                   | **핵심 매개변수 (Key Parameters)** |
| ------------------------- | ---------------------------------------------------------- | ---------------------------------- |
| `get_wallet_address`      | 구성된 지갑의 주소 가져오기 (`EVM_PRIVATE_KEY`에서 가져옴) | 없음                               |

#### 네트워크 정보

| **도구 이름 (Tool Name)** | **설명**                                            | **핵심 매개변수 (Key Parameters)** |
| ------------------------- | --------------------------------------------------- | ---------------------------------- |
| `get_chain_info`          | 네트워크 정보 가져오기                              | `network`                          |
| `get_supported_networks`  | 지원되는 모든 EVM(이더리움 가상 머신) 네트워크 나열 | 없음                               |
| `get_gas_price`           | 네트워크의 현재 가스비 가져오기                     | `network`                          |

#### ENS(이더리움 네임 서비스) 서비스

| **도구 이름 (Tool Name)** | **설명**                                         | **핵심 매개변수 (Key Parameters)** |
| ------------------------- | ------------------------------------------------ | ---------------------------------- |
| `resolve_ens_name`        | ENS(이더리움 네임 서비스) 이름을 주소로 변환     | `ensName`, `network`               |
| `lookup_ens_address`      | 주소를 ENS(이더리움 네임 서비스) 이름으로 역조회 | `address`, `network`               |

#### 블록 및 트랜잭션 정보

| **도구 이름 (Tool Name)** | **설명**                               | **핵심 매개변수 (Key Parameters)**        |
| ------------------------- | -------------------------------------- | ----------------------------------------- |
| `get_block`               | 블록 데이터 가져오기                   | `blockNumber` 또는 `blockHash`, `network` |
| `get_latest_block`        | 최신 블록 데이터 가져오기              | `network`                                 |
| `get_transaction`         | 트랜잭션 세부 정보 가져오기            | `txHash`, `network`                       |
| `get_transaction_receipt` | 로그가 포함된 트랜잭션 영수증 가져오기 | `txHash`, `network`                       |
| `wait_for_transaction`    | 트랜잭션 확인 대기                     | `txHash`, `confirmations`, `network`      |

#### 잔고 및 토큰 정보

| **도구 이름 (Tool Name)** | **설명**                    | **핵심 매개변수 (Key Parameters)**                           |
| ------------------------- | --------------------------- | ------------------------------------------------------------ |
| `get_balance`             | 네이티브 토큰 잔고 가져오기 | `address` (주소/ENS), `network`                              |
| `get_token_balance`       | ERC20 토큰 잔고 확인        | `tokenAddress` (주소/ENS), `ownerAddress` (주소/ENS), `network` |
| `get_allowance`           | 토큰 지출 허용량 확인       | `tokenAddress` (주소/ENS), `ownerAddress` (주소/ENS), `spenderAddress` (주소/ENS), `network` |

#### 스마트 컨트랙트 상호작용

| **도구 이름 (Tool Name)** | **설명**                                                     | **핵심 매개변수 (Key Parameters)**                           |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `get_contract_abi`        | 블록 탐색기에서 컨트랙트 ABI(응용 프로그램 이진 인터페이스) 가져오기 (60개 이상의 네트워크) | `contractAddress` (주소/ENS), `network`                      |
| `read_contract`           | 스마트 컨트랙트 상태 읽기 (필요시 자동 ABI 가져오기)         | `contractAddress`, `functionName`, `args[]`, `abiJson` (선택 사항), `network` |
| `write_contract`          | 상태 변경 함수 실행 (필요시 자동 ABI 가져오기)               | `contractAddress`, `functionName`, `args[]`, `value` (선택 사항), `abiJson` (선택 사항), `network` |
| `multicall`               | 여러 읽기 호출을 단일 RPC(원격 프로시저 호출) 요청으로 일괄 처리 (Multicall3 사용) | `calls[]` (컨트랙트 호출 배열), `allowFailure` (선택 사항), `network` |

#### 토큰 전송

| **도구 이름 (Tool Name)** | **설명**                    | **핵심 매개변수 (Key Parameters)**                           |
| ------------------------- | --------------------------- | ------------------------------------------------------------ |
| `transfer_native`         | 네이티브 토큰 (ETH 등) 전송 | `to` (주소/ENS), `amount`, `network`                         |
| `transfer_erc20`          | ERC20 토큰 전송             | `tokenAddress` (주소/ENS), `to` (주소/ENS), `amount`, `network` |
| `approve_token_spending`  | 토큰 허용량 승인            | `tokenAddress` (주소/ENS), `spenderAddress` (주소/ENS), `amount`, `network` |

#### NFT(대체 불가능 토큰) 서비스

| **도구 이름 (Tool Name)** | **설명**                                           | **핵심 매개변수 (Key Parameters)**                           |
| ------------------------- | -------------------------------------------------- | ------------------------------------------------------------ |
| `get_nft_info`            | NFT(대체 불가능 토큰) (ERC721) 메타데이터 가져오기 | `tokenAddress` (주소/ENS), `tokenId`, `network`              |
| `get_erc1155_balance`     | ERC1155 잔고 확인                                  | `tokenAddress` (주소/ENS), `tokenId`, `ownerAddress` (주소/ENS), `network` |

#### 메시지 서명

| **도구 이름 (Tool Name)** | **설명**                                                     | **핵심 매개변수 (Key Parameters)**                      |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------- |
| `sign_message`            | 인증 및 확인을 위한 임의 메시지 서명 (SIWE, 오프체인 서명)   | `message`                                               |
| `sign_typed_data`         | 가스 없는 트랜잭션, 퍼밋 및 메타 트랜잭션을 위한 EIP-712 구조화된 데이터 서명 | `domainJson`, `typesJson`, `primaryType`, `messageJson` |

## 리소스 (Resources)

서버는 다음 MCP(모델 컨텍스트 프로토콜) 리소스 URI(통합 자원 식별자)를 통해 블록체인 데이터를 노출합니다. 주소를 허용하는 모든 리소스 URI(통합 자원 식별자)는 ENS(이더리움 네임 서비스) 이름도 지원하며 자동으로 주소로 변환됩니다.

#### 블록체인 리소스

| **리소스 URI(통합 자원 식별자) 패턴**       | **설명**                      |
| ------------------------------------------- | ----------------------------- |
| `evm://{network}/chain`                     | 특정 네트워크의 체인 정보     |
| `evm://chain`                               | Ethereum 메인넷 체인 정보     |
| `evm://{network}/block/{blockNumber}`       | 번호에 따른 블록 데이터       |
| `evm://{network}/block/latest`              | 최신 블록 데이터              |
| `evm://{network}/address/{address}/balance` | 네이티브 토큰 잔고            |
| `evm://{network}/tx/{txHash}`               | 트랜잭션 세부 정보            |
| `evm://{network}/tx/{txHash}/receipt`       | 로그가 포함된 트랜잭션 영수증 |

#### 토큰 리소스

| **리소스 URI(통합 자원 식별자) 패턴**                        | **설명**                                 |
| ------------------------------------------------------------ | ---------------------------------------- |
| `evm://{network}/token/{tokenAddress}`                       | ERC20 토큰 정보                          |
| `evm://{network}/token/{tokenAddress}/balanceOf/{address}`   | ERC20 토큰 잔고                          |
| `evm://{network}/nft/{tokenAddress}/{tokenId}`               | NFT(대체 불가능 토큰) (ERC721) 토큰 정보 |
| `evm://{network}/nft/{tokenAddress}/{tokenId}/isOwnedBy/{address}` | NFT(대체 불가능 토큰) 소유권 확인        |
| `evm://{network}/erc1155/{tokenAddress}/{tokenId}/uri`       | ERC1155 토큰 URI(통합 자원 식별자)       |
| `evm://{network}/erc1155/{tokenAddress}/{tokenId}/balanceOf/{address}` | ERC1155 토큰 잔고                        |

## 🔒 보안 고려 사항 (Security Considerations)

- **프라이빗 키**는 트랜잭션 서명에만 사용되며 서버에 절대 저장되지 않습니다.
- 프로덕션 환경에서 사용하려면 추가적인 인증 메커니즘 구현을 고려하세요.
- 프로덕션 환경에서는 HTTP(하이퍼텍스트 전송 규약) 서버에 대해 HTTPS를 사용하세요.
- 남용을 방지하기 위해 속도 제한(Rate limiting)을 구현하세요.
- 가치가 높은 서비스의 경우 확인 단계를 추가하는 것을 고려하세요.

## 📁 프로젝트 구조 (Project Structure)

```
mcp-evm-server/
├── src/
│   ├── index.ts                # 주요 stdio 서버 진입점
│   ├── server/                 # 서버 관련 파일
│   │   ├── http-server.ts      # SSE(서버 전송 이벤트)를 포함한 HTTP(하이퍼텍스트 전송 규약) 서버
│   │   └── server.ts           # 일반적인 서버 설정
│   ├── core/
│   │   ├── chains.ts           # 체인 정의 및 유틸리티
│   │   ├── resources.ts        # MCP(모델 컨텍스트 프로토콜) 리소스 구현
│   │   ├── tools.ts            # MCP(모델 컨텍스트 프로토콜) 도구 구현
│   │   ├── prompts.ts          # MCP(모델 컨텍스트 프로토콜) 프롬프트 구현
│   │   └── services/           # 핵심 블록체인 서비스
│   │       ├── index.ts        # 작업 내보내기 (Operation exports)
│   │       ├── balance.ts      # 잔고 서비스
│   │       ├── transfer.ts     # 토큰 전송 서비스
│   │       ├── utils.ts        # 유틸리티 함수
│   │       ├── tokens.ts       # 토큰 메타데이터 서비스
│   │       ├── contracts.ts    # 컨트랙트 상호작용
│   │       ├── transactions.ts # 트랜잭션 서비스
│   │       └── blocks.ts       # 블록 서비스
│   │       └── clients.ts      # RPC(원격 프로시저 호출) 클라이언트 유틸리티
├── package.json
├── tsconfig.json
└── README.md
```

## 🛠️ 개발 (Development)

서버를 수정하거나 확장하려면:

1. `src/core/services/` 아래의 적절한 파일에 새 서비스를 추가합니다.
2. `src/core/tools.ts`에 새 도구를 등록합니다.
3. `src/core/resources.ts`에 새 리소스를 등록합니다.
4. `src/core/chains.ts`에 새로운 네트워크 지원을 추가합니다.
5. 서버 구성을 변경하려면 `src/server/http-server.ts`의 하드코딩된 값을 편집합니다.

## 📄 라이선스 (License)

이 프로젝트는 [MIT License](https://www.google.com/search?q=./LICENSE)의 조건에 따라 라이선스가 부여됩니다.