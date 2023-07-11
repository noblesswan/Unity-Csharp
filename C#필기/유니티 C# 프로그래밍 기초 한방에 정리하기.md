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

# 배열(그룹형 변수)
- 변수들을 묶은 하나의 장소

```csharp
String monsters = "슬라임", "사막뱀", "악마";
```
이런 식으로 한 가지 변수에 여러 개의 데이터를 넣을 수 없음. 

```csharp
String[] monsters = {"슬라임", "사막뱀", "악마"}; // 초기화와 동시에 선언

Debug.Log("맵에 존재하는 몬스터");
Debug.Log(monsters[0]);
Debug.Log(monsters[1]);
Debug.Log(monsters[2]);
```
이런 식으로 사용하면 가능함 

```csharp
int[] monsterLevel = new int[3]; // 초기화

monsterLevel[0] = 1;
monsterLevel[1] = 6;
monsterLevel[2] = 20; // 값 입력
```

# List<>
```csharp
List<string> items = new List<string>();
items.Add("생명물약30");
items.Add("마나물약30");
```
- 배열과 달리 데이터를 삭제할 수 있음 

```csharp
items.removeAt(0);
```

# 연산자(상수, 변수값을 연산해주는 기호)
```csharp
int exp = 1500;

exp = 1500 + 320;
exp = exp - 10;
level = exp / 300;
strength = level * 3.1;

// % 몫이 아닌 나머지 출력
int nextExp = 300 - (exp % 300);
```
# 문자열 연산자
```csharp
string title = "전설의"; 

Debug.Log("용사의 이름은?");
Debug.Log(title + " " + playerName);
```

# 비교연산자 bool
```csharp
bool isFullLevel = false;
int fullLevel = 99;

isFullLevel = level == fullLevel;
Debug.Log("용사는 만렙입니까?" + isFullLevel); 

// 출력 : False / 만렙이 아니기 때문에 False가 뜸
```

```csharp
bool isEndTutorial = level > 10;
Debug.Log("튜토리얼이 끝난 용사입니까?" + isEndTutorial);
```

```csharp
int health = 30;
int mana = 25;
bool isBadCondition = health <= 50 && mana <= 20; 
// && and 연산자. 두 개가 충족이 돼야 함
// || or 연산자
```

# 삼항연산자
```csharp
string condition = isBadCondition ? "나쁨" : "좋음";
```
- ? A : B 
- true일 때 A, false일 때 B 출력

# 키워드 
`int float string bool new List` 
- 키워드는 프로그래밍 언어를 구성하는 특별한 단어
- 변수 이름으로도 사용할 수 없고, 값으로도 사용할 수 없음
```csharp
int float = 1;
string name = List;
```
* 불가능 !!

# 조건문
## if문
```csharp
if(bool type 조건){
    로직
}
```

```csharp
if(condition == "나쁨"){
    Debug.Log("플레이어 상태가 나쁘니 아이템을 사용하세요");
}
else{
    Debug.Log("플레이어 상태가 좋습니다");
}
```

```csharp
if(isBadCondition && item[0] == "생명물약30"){
    item.RemoveAt(0);
    health += 30;
    Debug.Log("생명포션 30을 사용하였습니다.");
}
else if(isBadCondition && items[0] == "마나물약30"){
    items.RemoveAt(0);
    mana += 30;
    Debug.Log("마나포션 30을 사용하였습니다.");
}
```

## switch, case 
- 변수의 값에 따라 로직 실행
```csharp
switch(변수){
    case 값1:
        break;
    case 값2:
        break;
    case 값3:
        break;
}
```

```csharp
switch(monster[0]){
    case "슬라임":
        Debug.Log("소형 몬스터가 출현 !");
        break;
    case "악마":
        Debug.Log("중형 몬스터가 출현 !");
        break;
    case "골렘":
        Debug.Log("대형 몬스터가 출현 !");
        break;
    default:
         Debug.Log("??? 몬스터가 출현!");
        // defalut는 모든 case문에 진입을 못 했을 경우 나옴
        break;
}
```
- 같은 소형 몬스터 출현 시 case를 따로 잡아야 하는가? 
- 아니다 

```csharp
switch(monster[0]){
    case "사막뱀":
    case "슬라임":
        Debug.Log("소형 몬스터가 출현 !");
        break;
    case "악마":
        Debug.Log("중형 몬스터가 출현 !");
        break;
    case "골렘":
        Debug.Log("대형 몬스터가 출현 !");
        break;
    default:
         Debug.Log("??? 몬스터가 출현!");
        // defalut는 모든 case문에 진입을 못 했을 경우 나옴
        break;
}
```

# 반복문
## while
```csharp
while(조건){
    로직
}
```

독 데미지를 입었을 경우를 가정한 예시
```csharp
while(health > 0){
    health--;
    if(health>0)
        Debug.Log("독 데미지를 입었습니다." + health);
    else
        Debug.Log("사망하였습니다.");
    
    // break를 넣으면, 반복하지 말고 빠져나갈 수 있음
    if(health == 10){
        Debug.Log("해독제를 사용합니다");
        break;
    }
}
```
## for
```csharp
for(연산될 변수; 조건; 연산){
    로직
}
```

```csharp
for(int count=0; count<10 ;count++){
    health++;
    Debug.Log("붕대로 치료 중..." + health);
}
```
- 그룹형 변수 길이 : Length(배열), Count(리스트)

```csharp
for(int index=0; index<monster.length ;index++){
    Debug.Log("이 지역에 있는 몬스터" + monster[index]);
}
```

## foreach
- 새로운 변수를 만들어서 연산으로 돌리는 게 아니라 직접 그룹형 변수 안에 있는 아이템들을 하나씩 가져와서 중괄호 안에 넣어서 직접 사용하는 방식

```csharp
foreach(string monster in monsters){
    Debug.Log("이 지역에 있는 몬스터 : " + monster);
}
```
- 결과는 같지만 for문의 괄호 부분과 foreach문의 괄호 부분이 다르다

# 함수(method)
- 여러 가지 기능을 편리하게 사용할 수 있도록 구성된 영역

```csharp
반환받을값 함수명(함수가 받을 변수){
    
}
```

```csharp
health = Heal(health);

int Heal(int currentHealth){
    currentHealth += 10;
    Debug.Log("힐을 받았습니다" + currentHealth);
    return crrentHealth;
}
```
* return : 함수가 값을 반환할 때 사용
* 함수 앞에 반환타입이 적혀있다면 return을 꼭 적어야 함

함수를 사용하기만 해도 heal을 받는 구조
```csharp
int health = 100;

void Heal(){
    health += 10;
    Debug.Log("힐을 받았습니다" + health);
}
```
* void : 반환 데이터가 없는 함수 타입 
- 이런 식으로 사용하면, Start()에서 설정한 지역변수 health를 Heal함수 내에서 사용하지 못 함
* 지역변수 : 함수 안에서 선언된 변수
* 전역변수 : 함수 바깥에 선언된 변수 

몬스터 레벨과 용사 레벨을 구분하여 승패를 점하는 예시
```csharp
for (int index=0; index < monster.Length; index++){
    Debug.Log("용사는" + monsters[index] + "에게" + Battle(monsterLevel[index]));
}

string Battle(int monsterLevel){
    string result;
    if(level >= monsterLevel)
        result = "이겼습니다";
    else
        result = "졌습니다";
    
    return result;
}
```

# 클래스
하나의 사물(오브젝트)와 대응하는 것
- class 클래스 선언에 사용

```csharp
public class Actor{
    // 접근자는 private이 default값임
    public int id;
    public string name;
    public string title;
    public string weapon;
    public float strenth;
    
    string Talk(){
        return "대화를 걸었습니다";
    }
    
    string HasWeapon(){
        return weapon;
    }
    
    void LevelUp(){
        level = level +1;
    }
}
```
다음과 같이 클래스를 만든 뒤 다른 스크립트에서 사용하려면, 
```csharp
Actor player = new ACtor();

player.id = 0;
player.name = "나법사";
Debug.Log(player.Talk());
```
- Actor 클래스를 하나의 변수로 만들어준다 
- 이를 인스턴스라 한다
* 인스턴스 : 정의된 클래스를 변수 초기화로 실체화

