# Campus Clash · 학과 공싸움

한칸데이터와 별도로 운영하는 독립 게임 프로젝트입니다.

## 로컬 실행

Node.js 24 기준으로 `npm ci` 다음 `npm run dev`를 실행합니다.
배포 빌드는 `npm run build`, 실행은 `npm run start -- --port 3000`입니다.

## 별도 Render 배포

1. 이 프로젝트만 새 GitHub 저장소에 올립니다.
2. Render에서 New → Blueprint를 선택하고 해당 저장소를 연결합니다.
3. 저장소 루트의 `render.yaml`을 적용합니다. Root Directory는 비워둡니다.
4. 서비스 이름은 campus-clash이며 주소는 Render가 생성합니다. Live 이후 해당 주소의 `/`에서 게임을 엽니다.

수동 Web Service로 연결할 경우:

- Runtime: Node
- Build Command: `npm ci && npm run build`
- Start Command: `npm run start -- --port $PORT`
- Node 버전: 24
- Health Check Path: `/`

기존 한칸데이터 서비스나 도메인을 연결하지 않습니다. DB·메일·스토리지·비밀 API 키는 필요하지 않습니다.
Free 인스턴스는 유휴 상태에서 중지될 수 있습니다. 광고·분석·온라인 다중 접속은 아직 포함하지 않습니다.

## 게임

주요 학과명 133개와 직접 입력을 지원합니다. 고정 시드에 따라 충돌 공격·치명타를 계산하며 이름은 승패 계산에 사용하지 않습니다.
같은 링크는 같은 대결을 재생합니다. 다시 뽑기는 새로운 시드로 시작합니다.
