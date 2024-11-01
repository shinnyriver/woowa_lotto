# java-lotto-precourse

## 기능 요구사항
1. **로또 번호 발행**
    - 번호 범위: 1~45
    - 1장의 로또: 중복되지 않는 6개의 숫자를 뽑아야 함

2. **당첨 번호 추첨**
    - 당첨 번호: 중복되지 않는 6개의 숫자
    - 보너스 번호: 중복되지 않는 1개의 숫자

3. **당첨 조건 및 금액**
    - 1등: 6개 번호 일치 / 2,000,000,000원
    - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
    - 3등: 5개 번호 일치 / 1,500,000원
    - 4등: 4개 번호 일치 / 50,000원
    - 5등: 3개 번호 일치 / 5,000원

4. **로또 구입 및 발행**
    - 입력: 구입 금액
    - 조건: 1장당 1,000원
    - 로또 발행 시 구입 금액에 맞게 발행해야 함

5. **당첨 번호 입력**
    - 당첨 번호 6개와 보너스 번호 1개를 입력받음
    - 입력값 검증: 범위는 1~45, 중복 불가

6. **당첨 결과 출력**
    - 각 등수의 당첨 개수 출력
    - 총 수익률 계산 및 출력

7. **예외 처리**
    - 잘못된 입력 시 `IllegalArgumentException`을 발생시키고 에러 메시지를 출력
    - 에러 메시지는 "[ERROR]"로 시작

8. **코딩 스타일**
    - indent depth는 2까지만 허용
    - 함수 길이는 15라인 이내
    - 함수는 한 가지 일만 수행
    - `else`, `switch/case` 사용 금지
    - `JUnit 5`와 `AssertJ`를 이용한 단위 테스트 작성

## 개발할 기능 목록

1. **로또 번호 생성기**
    - `generateLottoNumbers`: 중복되지 않는 6개의 로또 번호 생성
    - `generateBonusNumber`: 중복되지 않는 1개의 보너스 번호 생성

2. **로또 번호 유효성 검증기**
    - `validateLottoNumbers`: 입력된 로또 번호의 유효성을 검증

3. **로또 구매 로직**
    - `purchaseLottos`: 구입 금액에 따른 로또 번호 리스트 생성 및 반환

4. **당첨 번호 비교 로직**
    - `compareLotto`: 로또 번호와 당첨 번호를 비교하여 결과 반환
    - `calculateRank`: 일치 개수와 보너스 여부에 따른 당첨 등수 계산

5. **당첨 결과 집계 및 출력**
    - `calculateResults`: 당첨 통계 계산
    - `printResults`: 당첨 내역 및 수익률 출력

6. **수익률 계산**
    - `calculateYield`: 수익률 계산

7. **예외 처리**
    - `handleInputException`: 입력값이 잘못된 경우 `IllegalArgumentException`을 발생

## Java Enum
- **Rank Enum**: 각 당첨 등수와 그에 따른 금액을 관리
    - `FIRST(6, false, 2_000_000_000)`
    - `SECOND(5, true, 30_000_000)`
    - `THIRD(5, false, 1_500_000)`
    - `FOURTH(4, false, 50_000)`
    - `FIFTH(3, false, 5_000)`
    - `NONE(0, false, 0)`

## 테스트 명세
- **LottoGeneratorTest**
    - 로또 번호 생성기의 범위 및 중복 여부 테스트

- **LottoValidatorTest**
    - 입력된 로또 번호의 유효성 검증 테스트

- **LottoComparerTest**
    - 로또와 당첨 번호 비교 및 등수 계산 테스트

- **LottoResultCalculatorTest**
    - 당첨 결과 집계 및 수익률 계산 테스트

- **ExceptionHandlerTest**
    - 잘못된 입력에 대한 예외 처리 테스트
