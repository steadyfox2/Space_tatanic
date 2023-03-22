# 🐋Space_tatanic
## Space_tatanic kaggle 데이터를 활용한 EDA 및 모델링

스토리 설명 두줄요약: 항행 중인 우주선이 항행중 먼지 구름 속에 숨겨진 시공간 이상과 충돌하였다. 배는 손상되지 않았지만, 거의 절반의 승객들이 다른 차원으로 옮겨졌다. 지구의 타이타닉과 비슷한 스토리에 이야기이다.

설명 이 대회에서 여러분의 과제는 우주선 타이타닉이 시공간 이상과 충돌하는 동안 승객이 대체 차원으로 이동되었는지 여부를 예측하는 것입니다. 이러한 예측을 돕기 위해 선박의 손상된 컴퓨터 시스템에서 복구된 개인 기록 세트가 제공됩니다.

## ⭐EDA

각 데이터에 대한 설명은 EDA로 그림보면서 진행하겠다. 종속변수인 전송여부는 승객들이 잘 전송되었는지 여부이다.

편의상 이 글에서는 생존여부로 바꾸겠다. 물론 어느 시공간에서 살아남았을 수도 있지만... 

### 🌠행성별, CryoSleep, Destination, Vip 분포

<img src = "https://user-images.githubusercontent.com/114843451/226583513-1711ea86-945f-44b3-8d9d-94312c588767.png" width="80%" height="50%">

먼저 HomePlanet은 출발한 행성이다. 지구가 54.1%로 가장 많고, 화성, 유로파가 각각을 차지하고 있다.

CryoSleep은 냉동수면 상태여부를 말한다. 냉동수면 상태가 36.2%를 차지하고 있는 것을 볼 수 있다.

Destination는 목적지를 말한다. TRAPPIST-1e라는 행성을 목적지로 둔 승객이 70%로 가장 많다.

마지막으로 VIP이다. VIP는 2.2%로 매우 작다. 

### 🌠Age, RoomService, FoodCourt, ShoppingMall, Spa, VRDeck

<img src = "https://user-images.githubusercontent.com/114843451/226584910-db28e96a-80ca-465a-8afc-3e3aa44fda49.png" width="80%" height="50%">

Age는 20~30대가 가장 많아보인다. RoomService, FoodCourt, ShoppingMall, Spa, VRDeck는 각각 승객이 어디서 소비했는지를 나타낸다.

### 🌠출발 행성별 생존여부

<img src = "https://user-images.githubusercontent.com/114843451/226587009-ff999d09-59e7-4937-8622-2c9cd66498ed.png" width="40%" height="40%">

출발 행성별로 무사히 잘 생존했는지에 대한 여부이다. 유로파 행성에서 출발한 인원이 비교적 많이 생존하였다.


### 🌠VIP 생존여부
<img src = "https://user-images.githubusercontent.com/114843451/226587661-3057628e-83ae-40b6-ba0c-7b3a60024764.png" width="40%" height="40%">

생존여부는 VIP와 큰 관련이 없어보인다. 

### 🌠연령별 생존여부
<img src = "https://user-images.githubusercontent.com/114843451/226588004-21faecad-b33a-4ab5-b87d-165b0bb456fc.png" width="50%" height="50%">

생존여부는 연령별로 큰 관련은 없어보인다.

### 🌠냉동수면별 생존여부
<img src = "https://user-images.githubusercontent.com/114843451/226588961-8dae30d8-b881-47b2-965b-d20a150ac5f9.png" width="40%" height="40%">

냉동수면별 여부에 따라 생존률의 차이가 크다. 냉동수면이 이뤄진 승객들이 생존률이 훨씬 더 높다. 

### 🌠좌석위치별 생존여부 P,S 좌석위치 여부

<img src = "https://user-images.githubusercontent.com/114843451/226590391-bc31f861-4b2a-41c8-84c0-46ea6fd2c719.png" width="40%" height="40%">

상대적으로 P좌석에 있었던 사람보다 S좌석에 있던 사람의 생존률이 더 높았다. 

### 🌠출발 행성, 냉동수면별 생존여부
<img src = "https://user-images.githubusercontent.com/114843451/226589272-1f65f0b5-e66f-42b1-b440-585766c9c72e.png" width="40%" height="40%">

유로파와 화성에서 출발하고, 냉동수면한 승객들은 대부분 생존하였다. 냉동수면한 곳이 차원이동을 비껴 간 것으로 보인다.

다만, 냉동수면한 지구에서 출발한 승객들은 절반정도가 사라졌다. 

그래도 냉동수면하지 않는 지구에서 출발한 승객들은 2/3이상이 사라진 것과 비교하면 높은 생존률이다. 

## 🚀Modeling

모델은 크게 네가지 모델을 사용하였다. 
