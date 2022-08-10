# 같은 그림 찾기 게임(FindSamePicture) 
> 3 x 4 배열안에 6쌍의 그림이 존재합니다. 같은 그림끼리 맞춰주세요. 다맞추면 성공입니다.

<br>
<br>

![ezgif-1-a19d285023](https://user-images.githubusercontent.com/98979901/183835345-bdefe232-9580-45d7-82b7-d0e4c24f743b.gif)


<br>
## 설계
### 메모리게임 설계
1. HTML 각각을, 하드코딩. 그리드 사용
2. 각각의 영역을 div 로 잡아서 onclick 부여 (파라미터 받기)
3. 12개의 배열안에 객체, cardArray 만듦

   - name: String, 카드에 들어갈 동물 이름.
         나중에 이걸로 맞췄는지 판단.
   - img: String, 이미지의 경로,
   - id: String, DOM 에 부여될 아이디. ex) 1-4
   - done: Boolean, 맞췄는지 판단

gameDOM     array
        파싱한 돔 정보를 gameDOM 빈 배열에 집어넣음: querySelectorAll
clickCount    number
        처음엔 0 
        클릭 횟수
clickFirst    number
        처음엔 -1             //location 
        첫번째 클릭 위치
clickSecond    number
        처음엔 -1
        두번째 클릭 위치

getGameDOM()        DOM 정보를 작업하기 쉽게 미리 파싱
            열두개의 돔 정보 싹 다 가져옴

이후, cardArray 를 싹 다 섞어버림. 원래 배열 바뀜.

setIDtoCardArray()    cardArray 에 DOM 위치에 알맞는 id 부여

createBoard()        물음표로 가득 찬 게임판 생성

flip()            뒤집기. done 이 true 일 때는 실행 안됨.
            setClickHistory(location) 실행해서 첫번째 클릭인지 두번째 클릭인지 판단
            물음표를 그림으로 뒤집음
            만약, 클릭카운트가 2이면, isCorrect() 실행해서 맞았는지 틀렸는지 판단
            이후, clickFirst, clickSecond 둘 다 -1 로 초기화

-----------------------------------------------
setClickHistory(location)    첫번째 클릭인지 두번째 클릭인지 판단해 클릭 데이터 저장
                즉, 0, 1, 2, 3, ... 11 이 들어감.

isCorrect()        일치하는지 판별
            만약 클릭했던 두 개의 그림이 일치하면 done 을 true 로 바꿔서
                flip 이 작동 안되게 처리
            두 개의 그림이 일치하면
                backFlip() 실행

backFlip()        틀렸을 때 다시 뒤집음. 0.5초 딜레이 줌.

## TOOL
![React](https://img.shields.io/badge/HTML-444444?style=for-the-badge&logo=HTML5)
![React](https://img.shields.io/badge/JavaScript-444444?style=for-the-badge&logo=Javascript)
![React](https://img.shields.io/badge/CSS-444444?style=for-the-badge&logo=CSS3)



## HTML code
```HTML

```


## 사용 예제



## 업데이트 내역


