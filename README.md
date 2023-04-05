# 냥랭 동영상 빌더

이 스크립트는 동영상을 냥랭 스크립트로 변환합니다.  
파이썬으로 작성되었으며, pillow 라이브러리 하나만을 사용합니다.

프레임 한장한장을 문자로 바꾼 뒤, 미리 정의된 메모리를 이용해 커서를 옮겨가면서 출력하는 방식으로 사용됩니다.

냥랭 1.6.0 버전 이상이 필요합니다.

## 사용법

먼저 동영상을 프레임 단위로 잘게 쪼개야 합니다.  
ffmpeg, 혹은 다른 툴을 사용해 프레임별로 나눠 자를 수 있습니다.

나눠진 프레임들은 반드시 **숫자 이름으로 되어 (1.png, 2.png, ...)** 저장되어야 합니다.  
또한 `./source` 폴더 안에 모든 프레임이 있어야 합니다.

이후 builder.py를 실행시키는 것으로 쪼개진 프레임 파일들을 냥랭 스크립트로 빌드할 수 있습니다.

**주의: 현재 냥랭 동영상 빌더에는 그 어떠한 압축방식도 적용되어 있지 않습니다.**  
**만약 크기가 큰 파일을 빌드할 경우, 소스코드를 보지 않는 것을 추천합니다. (컴퓨터가 터질 수도 있습니다..)**

빌더의 Output Filename 인풋은 출력 파일 이름을 정하는 것입니다.

냥랭 동영상 빌더는 `{입력된 파일 이름}.nyan` 파일과, `{입력된 파일 이름}.mouse`를 최종적으로 생산합니다.

`clear.nyan` 파일의 경우 각 프레임마다 화면을 지워주는 함수 모듈입니다.

만약 파일이 없거나 마우스 파일을 수정하여 clear.nyan 파일의 참조를 풀어버릴 경우 실행 도중 에러가 날 수 있으므로, **수정하지 않는 것을 권장합니다.**

만약 기능을 비활성화하고 싶을 경우, `clear.nyan` 파일의 내용물을 모두 지우고 `:` 문자 하나를 추가함으로써 비활성화시킬 수 있습니다.

## 공유

만약 파일을 공유하고 싶다면 `{출력 파일 이름}.nyan`과 `{출력 파일 이름}.mouse`, `clear.nyan`까지 3가지의 파일을 한번에 묶어서 공유해야 합니다.  
만약 셋 중 하나라도 없다면 스크립트를 실행할 수 없거나, 스크립트 실행 도중 에러가 날 수 있습니다.

또한 실행자가 냥랭 런타임을 설치해야 합니다.

냥랭 런타임 설치는 [공식 문서](https://nyanlang.org/docs/getting-started#installation)에서 확인할 수 있습니다.