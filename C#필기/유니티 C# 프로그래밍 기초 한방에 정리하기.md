# 변수 종류
`int` - 정수형 데이터 
`float` - 숫자형 데이터
`string` - 문자열 데이터 
`bool` - 논리형 데이터

# 프로그래밍 흐름 
선언 > 초기화 > 호출(사용)

```csharp
int level = 5;
float strngth = 15.5f;
string playerName = "나검사";
bool isFullLevel = false;

Debug.Log("용사의 이름은?");
Debug.Log(playerName);
```

# 그룹형 변수
- 변수들을 묶은 하나의 장소

```csharp
String monsters = "슬라임", "사막뱀", "악마";
```
이런 식으로 한 가지 변수에 여러 개의 데이터를 넣을 수 없음. 

```csharp
String[] monsters = {"슬라임", "사막뱀", "악마"};

Debug.Log("맵에 존재하는 몬스터");
Debug.Log(monsters[0]);
Debug.Log(monsters[1]);
Debug.Log(monsters[2]);
```
이런 식으로 사용하면 가능함 
