# 도감 등록

| 메소드 | 경로      | 짧은 설명 |
| ------ | --------- | --------- |
| POST   | /pokemons | 도감 등록 |



## 요청 헤더

##### 	Content-Type: multipart/form-data



## 요청 바디

```json
{
    "name": "피카츄",
    "type": "쥐",
    "photo": "사진 url"
}
```

## 응답바디

### 등록 성공

```json
{
    "status":201,
    "message": "등록 성공",
    "data":null
}
```

### 등록 실패

```json
{
    "status":400,
    "message": "등록 실패",
    "data":null
}
```

### DB 에러

```json
{
    "status": 600,
    "message": "데이터베이스 에러",
    "data": null
}
```



# 도감 전체 불러오기

| 메소드 | 경로      | 짧은 설명          |
| ------ | --------- | ------------------ |
| GET    | /pokemons | 도감 전체 불러오기 |



## 요청 헤더

##### 	content-Type: application/json

### 응답 바디

#### 모든 글 조회 성공

```json
{
    "status":200,
    "message": "모든 글 조회 성공",
    "data": [
        {
            "id": 1,
            "name": "도라에몽",
            "contents": "주머니에서 도구가 나옴",
            "date": "2018-12-01",
            "type": "로봇"
        },
        {
            "id": 2,
            "name": "롱스톤",
            "contents": "박치기함",
            "date": "2018-12-01",
            "type": "로봇"
        }
    ]
}
```

### INTERNAL SERVER ERROR

```json
{
    "status": 500,
    "message": "서버 내부 에러",
    "data": null
}
```



# 특정 포켓몬 검색

| 메소드 | 경로                   | 짧은 설명   |
| ------ | ---------------------- | ----------- |
| GET    | /pokemons/{pokemonIdx} | 포켓몬 조회 |

### 요청 헤더

#### Content-Type: application/json



### 응답 바디

#### 글 조회 성공

```json
{
    "status":200,
    "message": "글 조회 성공",
    "data": {
        "id": 22,
        "title": "꼬북이",
        "contents": "물대포를 쏘는 거북이다",
        "date": "2018-11-03",
        "photo": "https://s3.ap-northeast-2~~~~~"
    }
}
```



#### 없는 글 조회

```json
{
    "status": 404,
    "message": "글이 존재하지 않습니다.",
    "data": null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status":500,
    "message": "서버 내부 에러",
    "data": null
}
```

# 도감에서 포켓몬 삭제(ㅜㅜ)

| 메소드 | 경로                   | 짧은 설명       |
| ------ | ---------------------- | --------------- |
| DELETE | /pokemons/{pokemonIdx} | 포켓몬 삭제하기 |

### 요청 헤더

#### Content-Type: application-json



### 응답 바디

#### 포켓몬 삭제 성공

```json
{
    "status": 204,
    "message": "포켓몬 삭제 성공",
    "data": null
}
```

#### 포켓몬 조회 실패

```json
{
    "status": 404,
    "message" : "포켓몬을 찾을 수 없음",
    "data":null
}
```

#### DB 에러

```json
{
    "status": 600,
    "message": "데이터베이스 에러",
    "data": null
}
```

#### INTERNAL SERVER ERROR

```json
{
    "status":500,
    "message": "서버 내부 에러",
    "data": null
}
```

