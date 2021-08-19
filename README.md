# Android-Tile (물품 찾기 트래커)
- Language : Android
- Tools : Android Studio
- Techs : google api, TMap api
- Database : Firebase
- 형성관리 : github
- hardware : GPS, Bluetooth 

## 특징목록
연&nbsp;번| 우&nbsp;선&nbsp;순&nbsp;위 | 특&nbsp;징
:--: | :--: | --
F-01 | 14 | 사용자는 어플리케이션 시작시 구글 계정으로 로그인 가능하다.
F-02 | 16 | 사용자는 구글 계정이 없을 시, 구글 계정 회원가입이 가능하다.
F-03 | 12 | 로그인한 사용자는 마이페이지 에서 계정 정보를 확인할 수 있다.
F-04 | 13 | 정상적으로 로그인한 사용자는 로그아웃 후 시작화면으로 돌아갈 수 있다.
F-05 | 5 | 트래커의 위치 데이터는 일정 시간이 지나면 삭제된다.
F-06 | 1 | 트래커는 모든 위치의 좌표를 읽을 수 있다.
F-07 | 2 | 트래커는 블루투스 통신이 가능하다.
F-08 | 3 | 블루투스와 연동한 트래커는 스마트폰과 통신 가능하다.
F-09 | 11 | 블루투스 통신이 끊어질 시, 진동으로 사용자에게 알려준다.
F-10 | 4 | 사용자는 트래커의 현재 위치를 알 수 있다.
F-11 | 6 | 사용자는 트래커와 현재 위치까지의 경로를 알 수 있다.
F-12 | 10 | 사용자는 스마트폰을 소지하고 있는 기준의 위치를 알 수 있다.
F-13 | 7 | 위치 데이터는 지도에 일정 시간마다 해당 위치 정보가 표시된다
F-14 | 9 | 사용자는 사이드바를 통해 어플리케이션이 제공하는 부가기능을 이용할 수 있다.
F-15 | 8 | 사용자는 메인화면 하단바를 통해 어플리케이션이 제공하는 주요기능을 이용할 수 있다.
F-16 | 15 | 어플리케이션 시작시, 스마트폰에 블루투스가 켜지지 않았다면, 사용자에게 접근허가 권한 여부를 물어본다.
## 관련기술
연&nbsp;번 | 특&nbsp;징 | 관&nbsp;련&nbsp;기&nbsp;술
-- | -- | --
F-01 | 사용자는 어플리케이션 시작시 구글 계정으로 로그인 가능하다. | 구글 API를 이용해 로그인 시도시 구글 아이디,비밀번호 입력시 로그인  공
F-02 | 사용자는 구글 계정이 없을 시, 구글 계정 회원가입이 가능하다. | 로그인 페이지에서 별도의 구글 계정이 없는 사용자를 위해 하이퍼링크를 이용해 구글 계정 회원가입 사이트 링크로 이동시킨다.
F-03 | 로그인한 사용자는 마이페이지 에서 계정 정보를 확인할 수 있다. | 네비게이션 사이드 바에서 마이페이지 메뉴 선택시, 구글 계정정보에서 프로필사진, 아이디, 이메일 값을 받아와 어플리케이션에 출력하여 보여준다.
F-04 | 정상적으로 로그인한 사용자는 로그아웃 후 시작화면으로 돌아갈 수 있다. | 네비게이션 사이드 바에서 로그아웃 메뉴 선택시 현재 계정정보에서 로그아웃하고 로그인 화면으로 돌아간다.
F-05 | 트래커의 위치 데이터는 일정 시간이 지나면 삭제된다. | 트래커의 위치 정보를 데이터베이스로 가져와서 저장시, 데이터베이스의 과부하를 방지하기 위해서 현재시간값과 데이터베이스가 저장된 날짜값을 비교하여 일정 기간 초과시 해다 데이터를 제거한다.
F-06 | 트래커는 모든 위치의 좌표를 읽을 수 있다. | 블루투스 모듈을 이용하여 트래커가 위치한 해당 장소의 위도,경도값을 받아온다.
F-07 | 트래커는 블루투스와 연동 가능하다. | 트래커는 블루투스 모듈을 통해 통신 가능하다.
F-08 | 블루투스와 연동한 트래커는 스마트폰과 통신 가능하다. | 데이터 파싱을 통해 형식을 맞추어 데이터 송/수신이 가능하다.
F-09 | 블루투스 통신이 끊어질 시, 진동으로 사용자에게 알려준다. | 어플리케이션과 트래커간 블루투스 통신이 끊기거나 종료시, 사용자에게 스마트폰 진동을 전달해준다.
F-10 | 사용자는 트래커의 현재 위치를 알 수 있다. | 어플리케이션 시작시, 블루투스를 키지 않은 상태일때는 사용자에게 접근허가권한 여부를 물어보고, 블루투스를 킨다. 그 후, 지도에서 해당위치의 경도,위도값을 이용해 지도에 표시해준다.
F-11 | 사용자는 트래커의 연결이 끊어질시, 트래커와 현재 위치까지의 경로를 알 수 있다. | 연결 시작 지점의 좌표와 연결 종료 지점의 좌표값을 통해 경로를 구해 표시해준다.
F-12 | 사용자는 스마트폰을 소지하고 있는 기준의 위치를 알 수 있다. | 스마트폰의 위치 좌표 값을 통해 지도에 표시해준다.
F-13 | 위치 데이터는 지도에 일정 시간마다 해당 위치 정보가 표시된다 | 트래커의 위치 데이터는 일정시간마다 저장되어 메뉴 선택시마다 위치를 표시해준다.
F-14 | 사용자는 사이드 메뉴바를 통해 어플리케이션이 제공하는 부가기능을 이용할 수 있다. | 어플리케이션 사이드 네비게이션바를 이용하여 로그아웃, 데이터동기화, 마이페이지 기능을 이용할 수 있다.
F-15 | 사용자는 메인화면 하단바를 통해 어플리케이션이 제공하는 주요기능을 이용할 수 있다. | 어플리케이션 바텀 네비게이션바를 이용해 트래커 위치, 길찾기, 현재위치 기능을 이용할 수 있다.
F-16 | 어플리케이션 시작시, 스마트폰에 블루투스가 켜지지 않았다면, 사용자에게 접근허가 권한 여부를 물어보고 블루투스를 킨다. | 접근 허가 권한을 사용자에게 물어보고 허가시, 블루투스를 키게 된다.

## 이해당사자와 요
연&nbsp;&nbsp;번 | 이&nbsp;해&nbsp; 당&nbsp;사&nbsp;자 | 요&nbsp;구&nbsp;사&nbsp;항
-- | -- | --
St-01 | 트래커 사용자 | 현재 자신의 위치를 파악할수 있어야한다.잃어버린 물품의 위치를 파악할 수 있어야한다.분실물과 일정 거리가 멀어짐을 알 수 있다.
St-02 | 개발자 | 트래커의 위치 좌표값을 정상적으로 받아올 수 있어야 한다.트래커와 블루투스 간의 통신을 원활히 유지해야 한다.트래커와 스마트폰 간 통신을 가능하게 한다.트래커와 스마트폰 간 데이터 전달이 가능해야 한다.사용자가 정상적인 구글 계정 정보값을 통해 로그인을 시도한 경우, 로그인 처리를 올바르게 해주어야 한다.위치 정보 값을 이용해 지도에 올바르게 표시할 수 있어야 한다.위치 정보 값 간의 최적의 경로를 제공할 수 있어야 한다.
St-03 | 데이터 베이스 관리자 | GPS 위도, 경도 센서 데이터를 저장한다.센서 데이터는 일정한 규칙에 따라 저장된다.트래커의 위치 정보값을 데이터베이스에 저장할 수 있고, 일정 조건 충족시 해당 데이터를 지울 수 있어야 한다.

## 확장 유스케이스
- 구글 Api

![image](https://user-images.githubusercontent.com/71927210/130020066-2510fdfd-f635-4c5f-b5ae-f3b9a8c61152.png)
- 실시간 위치 데이터

![image](https://user-images.githubusercontent.com/71927210/130020395-cc05466e-0327-4fee-a77d-c103ef0ec5ba.png)

- 트래커 지도

![image](https://user-images.githubusercontent.com/71927210/130020618-e3c3d214-6a26-4945-893b-ae04ebb93d05.png)

- 블루투스 통신

![image](https://user-images.githubusercontent.com/71927210/130020797-1950d8f4-de5b-4877-9f88-751377716f44.png)


## 시스템 순차 다이어그램
- 구글 Api

![image](https://user-images.githubusercontent.com/71927210/130020114-ed4bb23b-af3a-4629-a22d-df28c26b0407.png)
- 실시간 위치 데이터

![image](https://user-images.githubusercontent.com/71927210/130020468-e7108caa-cb22-471b-9d60-1d0753293f7a.png)

- 트래커 지도

![image](https://user-images.githubusercontent.com/71927210/130020693-ef5eb27c-ec2b-43da-98fa-b3706d36b607.png)

- 블루투스 통신

![image](https://user-images.githubusercontent.com/71927210/130020876-db35bcc7-b23d-406c-8a87-c806c36daec9.png)

## 통신 다이어그램
- 구글 Api

![image](https://user-images.githubusercontent.com/71927210/130020184-998eaf63-ac39-457f-af90-a951ce3c3dd7.png)

- 실시간 위치 데이터
 
![image](https://user-images.githubusercontent.com/71927210/130020557-cd6b3086-8b0f-44f4-9bb7-7714d7df681c.png)

- 트래커 지도

![image](https://user-images.githubusercontent.com/71927210/130020733-8f181c84-512d-4a22-bdba-2bc80dd9f8a4.png)

- 블루투스 통신

![image](https://user-images.githubusercontent.com/71927210/130020898-bf5211de-d590-474e-b396-48a0c535bcb8.png)

## 구현

- 구글 Api

![image](https://user-images.githubusercontent.com/71927210/130020975-5a25fd05-f2b3-4427-8400-11a2cd2f575b.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130021486-68015755-abe7-4d2a-ab7b-ffa77373bc71.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130021691-8d821133-6cac-488d-8e65-4bb56d62c910.png)
![image](https://user-images.githubusercontent.com/71927210/130021706-cd82e571-2e4b-4de8-ac3f-4de2c5a06ef4.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130022216-cdb2f0e7-be92-4224-8050-b89314893c3c.png)
- 로그아웃

![image](https://user-images.githubusercontent.com/71927210/130022363-92899893-0141-4503-a8c7-3d2f896b7f49.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130022376-f6b80d53-05a8-48cb-9f0d-6f9e287ca1ae.png)

- 실시간 위치 데이터

![image](https://user-images.githubusercontent.com/71927210/130022158-9e665ff2-8330-4521-847a-fd30e552e79a.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130022417-77a9b7e2-a802-4cb4-8b05-b14db9413d95.png)

- 트래커 지도

![image](https://user-images.githubusercontent.com/71927210/130022453-ddabf085-576f-474c-9054-b5b427ba0ac2.png)
<br>
![image](https://user-images.githubusercontent.com/71927210/130022463-d13ead50-2439-4ef2-984f-46970b378cf4.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130022474-d1325fa5-fb1a-41b4-9f77-24004bdc8712.png)

- 블루투스 통신

![image](https://user-images.githubusercontent.com/71927210/130022176-c3d889de-d930-4129-8fb1-dfe0c6a66f8c.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![image](https://user-images.githubusercontent.com/71927210/130022490-355845cd-2ea1-4b1e-b6b5-1ac87daccd84.png)

