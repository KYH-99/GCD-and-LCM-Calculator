# GCD-and-LCM-Calculator Public
2019 | Web development

# HTML, CSS, JS - 최대공약수와 최소공배수 계산기

## 프로젝트 개요

이 프로젝트는 HTML, CSS, 자바스크립트를 사용하여 최대공약수(GCD)와 최소공배수(LCM)를 계산하는 계산기를 제작하는 것을 목표로 하고 있습니다. 사용자 입력을 받아서 계산된 결과를 직관적으로 화면에 출력하며, 최대 입력 값은 1000으로 제한되어 있습니다.

## 사용된 도구 및 플랫폼

- **Visual Studio Code**: 개발 환경으로 사용
- **Github**: 소스 코드 관리를 위해 사용
- **Netlify**: 프로젝트 배포를 위해 사용

## 완성된 사이트

프로젝트는 Netlify를 통해 배포되었으며, 아래 링크에서 확인할 수 있습니다:
- [완성된 사이트 이동하기](https://tranquil-squirrel-ee89de.netlify.app/)

## 주요 기능

1. **최대공약수 및 최소공배수 계산**:
   - 사용자가 두 개의 숫자를 입력하면, 해당 숫자들의 최대공약수와 최소공배수를 계산하여 출력합니다.
   - 입력 값은 1에서 1000 사이의 양의 정수로 제한됩니다.

2. **오류 처리**:
   - 잘못된 입력(0 이하의 숫자, 1000 이상의 숫자 등)이 들어올 경우 경고 메시지를 출력하여 유효한 값을 입력하도록 유도합니다.

## 결과 화면

### (1) 시작 화면
- 사용자가 두 숫자를 입력할 수 있는 인터페이스 제공.
  
### (2) 오류 화면
- 1000 이상의 숫자가 입력되면 오류 메시지를 출력.

### (3) 결과 화면
- 입력된 두 숫자에 대한 최대공약수(GCD)와 최소공배수(LCM)가 출력.

## 핵심 코드

```html
// 최대공약수와 최소공배수를 계산하는 함수
function calculate() {
    const A = parseInt(document.getElementById('A').value);
    const B = parseInt(document.getElementById('B').value);

    if (isNaN(A) || isNaN(B) || A <= 0 || B <= 0 || A > 1000 || B > 1000) {
        showAlert("A와 B 모두 1에서 1000 사이의 양의 정수를 입력하세요.");
        return;
    }

    function gcd(a, b) {
        return b === 0 ? a : gcd(b, a % b);
    }

    function lcm(a, b) {
        return (a * b) / gcd(a, b);
    }

    const gcdResult = gcd(A, B);
    const lcmResult = lcm(A, B);

    document.getElementById('result').innerHTML = `최대공약수: ${gcdResult}, 최소공배수: ${lcmResult}`;
}
```

## 태그

- HTML
- CSS
- 자바스크립트
- Netlify
- Github
- 최대공약수
- 최소공배수
