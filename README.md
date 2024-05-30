# zkp-circom-library

MIMC

MIMC는 영지식증명에 친화적인 해시 함수입니다. MIMC를 블록체인에 포팅합니다. 그리고 동일한 입력값으로 블록체인과 오프체인에서 해시값을 계산합니다. 각각 계산한 해시값을 비교하여 일치 여부를 확인하여 계산이 정확한지 검증할 수 있습니다.
Circom Library의 mimc.circom 코드에는 단일 입력 값을 계산하는 MiMC7 템플릿과 다중 입력 값을 계산하는 MultiMiMC7 템플릿이 있습니다. 아래 예제에서는 단일 입력 값을 계산하는 MiMC7 템플릿을 다루고 있습니다.

디렉토리를 생성하고 터미널에 `npm i circomlib` 명령어를 입력하여 모듈을 다운받습니다.
mimc.circom 파일을 생성하고 아래 코드를 복사 붙여놓고 저장합니다.
```
pragma circom 2.0.0;
include "node_modules/circomlib/circuits/mimc.circom";
component main = MiMC7(91);
```
그리고 `circom mimc.circom --r1cs --wasm --sym -o .` 명령어로 컴파일합니다.
컴파일 후 `snarkjs r1cs export json mimc.r1cs mimc.r1cs.json` 명령어로 mimc.r1cs의 json형태를 생성해줍니다.