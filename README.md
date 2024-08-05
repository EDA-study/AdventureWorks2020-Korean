# AdventureWorks2020-Korean
AdventureWorks 데이터는 Microsoft에서 SQL Server 사용 연습을 위해 만든 샘플용 데이터입니다. 해당 데이터 중 일부를 한글로 번역 및 현지화하여 공유합니다. 원본 데이터 출처는 아래와 같습니다. 
  1. [Microsoft에서 제공하는 공식 원본](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms)
  2. [1번 데이터 중 일부를 CSV 형태로 가공한 파일](https://www.kaggle.com/datasets/algorismus/adventure-works-in-excel-tables/data)

본 데이터는 2번 데이터를 가지고 번역 및 현지화를 진행했습니다. 

_참고: 구분자는 comma가 아닌 tab으로 구분되어 있습니다._

## 데이터별 번역 및 현지화 과정

### Product_ko.csv
  - 열 이름 번역
  - `제품명`, `색상`, `하위 분류`, `분류` 열 내의 값 번역
  - `비용` 열 내에 있는 가격 원화 환산 (1 USD = 1,300 KRW) 후 반올림하여 백원 단위로 표시
 
### Region_ko.csv
  - 열 이름 번역
  - `지역`, `국가`, `그룹` 열 내의 값 번역
  - 7번 영업지역에 해당되는 프랑스를 한국으로 변경
    - `지역`: `한국`
    - `국가`: `한국`
    - `그룹`: `태평양`

### Reseller_ko.csv
  - 열 이름 번역
  - `사업 유형`, `국가` 열 내의 값 번역
  - `국가`가 프랑스인 경우 한국으로 변경
  - `국가`가 한국에 해당하는 경우 `도시` 및 `주/도`를 한국 행정구역으로 변경 및 `리셀러`를 한글로된 이름으로 무작위 입력

### Sales_ko.csv
  - 열 이름 번역
  - `주문일` yyyy/mm/dd 형식으로 변경
  - `단가` 열 내에 있는 가격 원화 환산 (1 USD = 1,300 KRW) 후 반올림하여 백원 단위로 표시
  - `수량`과 원화로 환산된 `단가`를 곱하여 `매출`에 입력
  - `Product_ko.csv`의 `비용` 열에 있는 값을 `수량`과 곱하여 `Sales_ko.csv`의 행별 `비용` 열에 입력

### Salesperson_ko.csv
  - 열 이름 번역
  - `직책` 열 내의 값 번역

### SalespersonRegion_ko.csv
  - 열 이름 번역
  - 프랑스가 한국으로 변경된 것을 영업 부서 조직 구조에 반영하기 위해 `직원 키`, `영업지역 키` 쌍 중, 290 - 7에 해당하는 것을 294 - 7로 변경

### Targets_ko.csv
  - 열 이름 번역
  - `목표 월` yyyy/mm/dd 형식으로 변경
  - `목표치` 열 내에 있는 가격 원화 환산 (1 USD = 1,300 KRW) 후 반올림하여 백원 단위로 표시

