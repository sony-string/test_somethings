## 사전 준비 사항

1. 필요한 패키지 설치:
```bash
sudo apt install python3-full python3-venv
```

2. 가상 환경 생성:
```bash
# 프로젝트 디렉토리에서
python3 -m venv venv
```

3. 가상 환경 활성화:
```bash
source venv/bin/activate
```

4. 필요한 패키지 설치:
```bash
pip install requests matplotlib pandas
```

5. 스크립트 실행:
```bash
python k6_visualize.py your.json
```

6. 작업 완료 후 가상 환경 비활성화:
```bash
deactivate
```

### option
```js
export const options = {
    vus: 10,        // 동시 접속하는 가상 유저 수
    duration: '10s', // 테스트 시간
    thresholds: {
        checks: ['rate>0.95'] // 테스트 통과 커버리지
    }
};
```

### 서버는 클라이언트에서 끊어진 세션에 대해 정확하게 핸들링하지 못합니다.
아래의 테스트를 한 번 수행한 이후에 stop API 를 명시적으로 호출해주어야합니다.   
`stop.sh` 파일을 참고해서 호출해주시면 됩니다.

### text-mode 테스트 방법
```bash
#1
k6 run --summary-export=text_mode.json text-test.js
```

### interactive-mode 테스트 방법
```bash
#1
k6 run --summary-export=interactive_mode.json interactive-test.js
```
   
### debug-mode 테스트 방법
```bash
#1
k6 run --summary-export=debug_mode.json debug-test.js
```
