# 당근마켓 클론코딩

## 프로젝트 설명

### 📆 기간

2021.04.02 ~ 2021.04.08<br/>

### 🏃 팀 구성

- Frontend<br/>
  - 박민경(React)
  - 사용 기술 : react-create-app, react-hook, redux, redux-logger, axios
- Backend<br/>
  - 김동현(Spring)
  - 채수연(Spring)

### 💡 당근마켓을 클론코딩한 이유

```
첫 클론코딩인만큼 완성도를 높이기 위해 접근하기 쉬운 사이트를 찾았습니다. 쉬운 사이트 중에서도 당근마켓이 기본적인 기능들을 겪어볼 수 있는 것 같아 선택했습니다.
```

### 📺 시연영상

[Youtube](https://www.youtube.com/watch?v=5tLHyCBxhm4)

## 🔎 기능 설명

### 1. 메인페이지

![](https://images.velog.io/images/pmk4236/post/ae4ed29d-8ac0-481e-839c-93368452f042/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-04-11%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.02.08.png)

- Header에 당근마켓 사이트(PC버전) 없는 로그인 / 회원가입 버튼을 추가했습니다.

- Header 상단 고정 방법으로 `position:sticky`를 선택했습니다. 처음에 `position:fixed`를 사용하였는데, 부모 요소의 영향을 받아 뷰가 깨지는 현상이 있었습니다. 그래서 부모요소의 기준없이 본인 요소에만 속성을 적용하기 편리한 `sticky`를 사용했습니다.

- 총 4개의 배너가 포함되어 있었습니다. 최소화 컴포넌트를 하기 위해 4개로 쪼개어 작업했습니다. 최소화 컴포넌트를 하니 재사용성의 장점을 느껴볼 수 있었습니다.

### 2. 로그인

![](https://images.velog.io/images/pmk4236/post/292f2aeb-55d8-4186-b5ad-f24de8452e1b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-04-11%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.20.46.png)

- PC버전에는 로그인 / 회원가입 기능이 없어 직접 구현했습니다. 디자인이 따로 없어서 비슷한 디자인으로 와이어프레임을 작성하여 뷰를 구축했습니다.
- 백엔드에서 성공적인 reponse를 받지 못할 경우 로그인에 실패했다는 안내의 alert 처리를 해두었습니다.

### 3. 회원가입

![](https://images.velog.io/images/pmk4236/post/7a5339cf-5080-4cc6-95db-d911cfa29023/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-04-11%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.20.58.png)

- 로그인과 마찬가지로 회원가입도 와이어프레임을 작성하여 뷰를 구축했습니다.
- 백엔드에서 성공적인 reponse를 받지 못할 경우 회원가입에 실패했다는 안내의 alert 처리를 해두었습니다.

### 4. 인기매물 페이지

![](https://images.velog.io/images/pmk4236/post/8575e871-9578-40d8-b6a0-f3c3c1016d92/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-04-11%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.12.35.png)

- 실제 당근마켓 사이트에서는 전국 지역을 드롭다운으로 선택할 수 있습니다. 팀 회의를 거친 끝에 전국 지역을 filtering하는 것은 시간 관계 상의 어려움이 있어, 서울 내 지역명 클릭 시 해당 지역 매물 리스트를 filtering하여 불러오게 했습니다.
- 지역명 클릭 시 `useState`를 사용해 해당 텍스트 값을 request로 요청합니다.
- reponse로 받은 매물 리스트를 map 내장함수를 사용하여 뿌려주었습니다.
- 백에서 데이터를 요청시마다 랜덤으로 값을 보내주고, reload 시 매물 리스트가 실제로 업데이트되는 듯한 효과를 넣었습니다.

### 5. 매물상세 페이지

<center><img src="https://images.velog.io/images/pmk4236/post/6c5d92ac-e728-4d6b-bb13-845c4932acdf/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-04-11%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.15.59.png" width="70%" height="70%" /></center>

- 매물 클릭 시 해당 ID값으로 상세페이지를 불러오게 했습니다.
- 이미지, 닉네임, 카테고리, 가격, 상세설명, 채팅/조회 수를 불러옵니다.

## 아쉬웠던 점

- 프로젝트 진행 중 React 팀원 한 분이 개인 사정으로 그만두게 되어 프론트엔드가 맡은 부분을 혼자 하게 되었습니다. 분량의 문제는 염려되지 않았으나, 제한된 시간적 문제가 컸기에 기능 구현에 대한 완성도가 낮다는 생각을 했습니다. CUD의 기능을 구현하지 못한 것이 대표적인 예입니다. 추후 시간을 투자해 꼭 추가적인 기능을 넣을 예정입니다.

- 깃허브 관리를 제대로 하지 못했습니다. 아직 시도해보지 못한 GUI 사용법을 익혀 다음 프로젝트에 반영 예정입니다.

- 코드 효율성의 극대화를 시키지 못한 것이 아쉽습니다. 좀 더 공부하여 잘 짜여진 코드를 만드는 것이 목표입니다.

## 느낀 점

- 클론코딩은 처음이라 그런지 실제 운영사이트와 똑같이 만들고 배포했을 때 너무 신기하고 감격스러웠습니다. 비록 100% 완벽히 구현하진 못했지만 이번 프로젝트를 계기로 다음 클론코딩 프로젝트를 한다면 지금과는 더 많은 성장의 차이를 느낄 수 있지 않을까 생각합니다.
