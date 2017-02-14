# MinePing
마인크래프트 Ping 라이브러리입니다. [JLChnToZ님이 제작하신 mcs2 소스](https://github.com/JLChnToZ/mcs2)로부터 추출하였습니다.

현재 [마인리스트](https://minelist.kr)의 백엔드 라이브러리로 사용하고 있습니다.

### License
GPLv3

### 사용법

```js
var mineping = require("mineping");

mineping(버전 번호, 서버 주소, 포트, function(err, response) {
// 코드 추가
});
```

#### 버전 번호

버전      | 버전 번호
--------|-----------
1.4 미만 | 0
1.6 미만 | 1
1.7 미만 | 2
1.7 이상 | 3

#### 리턴값
##### 1.7 미만
* protocolVersion (1.6 미만일 경우 ```71```로 고정)
* version (고정값) (1.6 미만일 경우 ```<= 1.5.x``` 로 고정)
* motd
* currentPlayers
* maxPlayers

##### 1.7 이상
* protocolVersion
* version (고정값)
* motd
* currentPlayers
* maxPlayers
* players (존재할경우) - 1.7 이상 sample 플레이어 값
* favicon (존재할경우)



### 예제
```js
var mineping = require("mineping");

mineping(3, "example.com", 25565, function(err, response) {
if(err)
    console.log("오류가 있습니다.");
else
    console.log(response.motd)
});
```
