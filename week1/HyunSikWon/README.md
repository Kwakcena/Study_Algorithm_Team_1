## 메뉴 리뉴얼 Lv2

### 문제 접근 방식

1. 주어진 배열의 크기, 원소의 크기 모두 작아서 효율성은 고려하지 않고 구현에 초점을 맞췄습니다.
2. 단순하게 각각의 메뉴 구성에서 나올 수 있는 모든 경우의 수를 구하는 방식으로 문제를 풀었습니다.
3. 비트 연산을 통해서 `orders` 배열의 원소들로 만들 수 있는 모든 메뉴 구성을 구했습니다. ex) "ABC" → AB, AC ,BC
4. 3번에서 구한 메뉴 구성이 주문된 횟수를 구했습니다. "ABC", "ABD" → AB는 2번 주문됨.
5. 이들 중 2번 이상 주문되고, 단품 메뉴의 갯수가 `coures`에 포함되는 메뉴 구성을 필터링. 
6. 단품 메뉴의 갯수별로 가장 많이 주문된 코스를 골라 최종 결과 배열에 삽입. 가장 많이 주문된 횟수가 같으면 모두 넣음.
7. 최종 결과 배열은 정렬 후 반환.

## 조이스틱 Lv2

### 문제 접근 방식

1. `name`의 길이가 크지 않아 성능 고려는 하지 않아도 된다고 판단하고 기능 구현에 초점을 맞춰 문제 해결을 진행하였습니다.
2. 상,하/좌우 이동 중 먼저 더 쉬운 상,하 이동을 구현하였습니다.
3. 알파벳 선택은 A에서 가장 가까운 위치만 찾으면 되기 때문에 ASCII 코드를 이용해 구현했습니다.
4. 좌우 이동은 현재 위치에서 A를 제외한 처리해야할 가장 가장 가까운 위치로 이동하도록 구현했습니다. ex) JACD → J에서 가장 가까운 거리는 D. 방문한 위치는 배열을 통해 처리.
5. 3,4 번에서 이동 횟수를 더한 후 최종적으로 반환.

## 풍선 터트리기 Lv3

### 문제 접근 방식

1. 양 끝의 값은 무조건 끝까지 남을 수 있다는 점을 생각하게 됨. 
2. 그렇다면 다른 값들이 끝에 있는 것과 다름이 없다면, 이들도 끝까지 남을 수 있다고 생각.
3. 끝에 있는 것과 다름이 없다는 뜻은 무엇인가? → 작은 값의 풍선을 터트릴 기회가 남은 상태. 즉, 인접한 값에 상관 없이 남아있을 수 있음.
4. 배열을 앞에서 부터 한번, 뒤에서 부터 한번씩 총 두번 탐색.
5. 앞에서부터 탐색 → 현재 인덱스의 값이 앞에있는 모든 값보다 작으면 끝까지 남을 수 있다. 즉, 끝에 있는 것과 다름이 없다. ex) a[3]이 a[0]~a[2] 의 값들보다 작으면. 
6. 뒤에서부터 탐색 → 현재 인덱스의 값이 뒤에있는 모든 값보다 작으면 끝까지 남을 수 있다.
7. 5, 6에서 원소를 탐색하면서 Swift의 `Set`(원소 중복 불가) 컬렉션에 추가하여, 집합의 원소 갯수를 반환.