# CPiscineTest

42 SEOUL C Piscine 과정에서, **동료 평가 보조** 또는 **제출 전 자가 테스트**를 위해 사용하는 스크립트와 소스코드를 실행시키는 셸 스크립트 프로젝트 입니다.
본 프로젝트에는 테스트에 바로 사용할 수 있도록 템플릿 테스트 셸 스크립트 또는 소스코드가 이미 포함되어 있습니다.

◎ 동료 평가시에는 이 테스트 스크립트 및 소스코드는 참고 용도로만 이용하시기 바랍니다. 예기치 않은 결과가 나올 가능성도 있습니다.

## 설치

1. 적당한 곳에 저장소를 클론합니다.
```bash
git clone https://git.tensiya.net/tsy/CPiscineTest.git
```

2. 클론한 저장소 폴더로 이동한 후, 아래 처럼 _alias_ 커맨드를 사용해 테스트 스크립트를 별칭으로 등록합니다.
```bash
cd CPiscineTest
alias ptest="sh $(echo $(pwd)/test.sh)"
```

3. **클론한 저장소 폴더에서** 아래 커맨드를 실행하여 .zshrc 파일에 등록해두시면 터미널을 새로 켜도 자동으로 편리하게 사용할 수 있도록 별칭이 등록됩니다.
```bash
echo "alias ptest=\"sh $(echo $(pwd)/test.sh)\"" >> ~/.zshrc
```

## 사용법

1. 테스트를 수행할 과제 프로젝트의 디렉토리로 이동합니다.
```bash
cd ~/MyProject/C00
```

2. 별칭으로 지정해두었던 커맨드에 프로젝트 이름을 매개변수로 넣어주어 테스트를 수행합니다.
```bash
# Shell00 프로젝트를 평가할 때
ptest Shell00

# C00 프로젝트를 평가할 때
ptest C00

# C02 프로젝트를 평가할 때
ptest C02
```

## 테스트 출력 결과 표시하기

* 셸 스크립트를 실행할 때 맨 뒤에 **p** 문자열을 넣어 주면 결과 출력도 표시됩니다.

```bash
# Shell00 프로젝트를 평가하며, 결과 출력도 표시하기
ptest Shell00 p

# C00 프로젝트를 평가하며, 결과 출력도 표시하기
ptest C00 p

# C02 프로젝트를 평가하며, 결과 출력도 표시하기
ptest C02 p
```

## 테스트 출력 결과 확인하는 방법

프로젝트마다, 혹은 과제마다 테스트 수행 방법이 다소 다를 수 있습니다.
또한 저장소에서 함께 제공된 테스트 코드가 마음에 안들거나, 추가적인 테스트를 넣고 싶다면 각 프로젝트 이름의 서브 폴더에서 테스트 소스코드 또는 셸 스크립트를 수정해주세요.

* 예상 출력 결과와 비교(diff)하는 테스트일 경우, 뮬리네트 기계채점과 마찬가지로 각각 **Diff OK** 와 _Diff KO_ 로 구분되어 결과를 표시해줍니다.

### C 프로젝트

일반적으로 C 프로젝트는 저장소의 각 프로젝트 이름의 서브 폴더에서 테스트 소스코드를 (ex: ex00.c, ex02.c, ...)
과제로 제출된 파일과 함께 컴파일합니다. 그리고 실행하여 서브 폴더 내에 있는 예상 출력 결과 파일과 비교합니다. (ex: ex00.result, ex02.result)
**예상 출력 결과와 컴파일되어 실행된 프로그램의 결과가 일치하면 정답을 맞춘 것으로 간주합니다.**

단, C02 프로젝트의 12번 과제 같은 테스트 예외가 있을 수 있음으로, 이런 경우에는 직접 확인하셔야 합니다.

### 셸 스크립트 프로젝트

셸 스크립트 프로젝트는 Shell00과 Shell01 의 실행 루틴이 다소 다릅니다.
**셸00** 과제는 타임스탬프, 권한 등을 예상 출력값과 과제로 제출된 파일의 상태를 스크립트가 출력해주며, **직접 눈으로 비교하게끔 만들어져있습니다.**

셸01 과제는 예상 출력 값을 생성해낼 수 있기에, C 스크립트와 마찬가지로 직접 눈으로 확인할 필요 없이 **자동으로** 정답 여부를 검사합니다.
**예상 출력 결과와 과제로 제출된 결과가 일치한다면 정답을 맞춘 것으로 간주합니다.**

## 업데이트

깃 저장소에 새로운 스크립트 및 테스트 코드, 그리고 오류 수정 등이 올라올 경우,
클론한 저장소 폴더로 이동한 후, git pull로 저장소를 업데이트 해주세요.
```bash
cd CPiscineTest
git pull
```
