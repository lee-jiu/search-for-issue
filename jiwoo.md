#### 2020-1 Capstone Design Project
Search for issue
-------------
Contributor :raising_hand: : [이지우](https://github.com/lee-jiu, "이지우")

### My Issue
- [보건·행정] COVID-19 관련 서비스 (마스크 조회, 안심병원 및 선별 진료소 조회)  
- [교통] 서울특별시 공공자전거 대여소 보조 서비스 (따릉이)   


* * *

#### Ⅰ. COVID-19 관련 서비스 (마스크 조회, 안심병원 및 선별 진료소 조회)
1. 문제정의  
- 마스크의 재고는 약국마다 실시간으로 변동 됨. 즉, 가변적이므로 정확한 재고 파악이 어려움    
> #### :point_right: 실시간(Online) 데이터를 활용해 마스크 재고 정보를 파악하고 간편하게 볼 수 있는 서비스 필요   
   
   
   
   
- 코로나 19 관련 유증상자/무증상자는 이용할 수 있는 병원 및 진료소가 다름. 그러나 이를 간편하게 확인하기 어려움. 
> #### :point_right: 국가에서 제공하는 병원 및 진료소 데이터를 활용해 병원 정보를 파악하고 간편하게 볼 수 있는 서비스 필요   



> 국가에서는 유증상자가 이용할 수 있는 '선별진료소' 정보를 제공함과 동시에 증상이 없는 환자가 안심하고 이용할 수 있는 '국민안심병원' 정보를 제공함, [국민안심병원 및 선별진료소 현황](https://www.mohw.go.kr/react/popup_200128.html, "국민안심병원 및 선별진료소 현황")   
   
   

* * *
2. 데이터 수집

* 공공 API 이용     
[공적 마스크 판매 현황 조회 API](https://app.swaggerhub.com/apis-docs/Promptech/public-mask-info/20200307-oas3#/StoreSaleResult, "공적 마스크 판매 현황 조회 API")
> 약국, 우체국, 농협 등의 마스크 판매처 정보 제공  
> 마스크 재고 상태 등의 판매 정보 제공  
> 위도/경도, 지역별 판매 정보 제공 

* Web scraping 기법 이용    
[국민안심병원 및 선별진료소 현황](https://www.mohw.go.kr/react/popup_200128.html, "국민안심병원 및 선별진료소 현황")   
   
<img width="304" alt="issue_jw_3" src="https://user-images.githubusercontent.com/56306637/77858437-839f1080-723e-11ea-9678-2083224e9201.PNG">
> 스크래핑 기법을 이용해 필요한 데이터만 추출   



* * *
3. 데이터 활용   
> * 실시간 마스크 재고, 약국 위치 조회 
> * 안심병원 및 선별 진료소 조회 
> * 그 외 : 사용자 데이터 분석  
>   * 가까운 병원 및 약국 추천 기능
>   * 자주 이용하는 약국 및 병원 조회 기능 


* * * 
4. 데이터 시각화 도구  
<img width="715" alt="issue_jw_2" src="https://user-images.githubusercontent.com/56306637/77857216-2bb0db80-7237-11ea-8ae6-2abf0a9fea35.PNG">

- 하둡(hadoop) 기반 [apache zeppelin](https://zeppelin.apache.org/, "apache zeppelin")
> 현재 다룰 수 있는 시각화 도구는 zeppelin 뿐이나, 추후 다른 시각화 도구 또한 조사 후 공부할 예정...:two_hearts:  
* * *  

#### Ⅱ. 서울특별시 공공자전거 대여소 보조 서비스 (따릉이)
 1. 문제 정의  
  - 자전거 대여소의 오프라인(Offline)특성상, 위치 정보 및 실시간 대여 정보를 파악하기 힘듦.   
  - 따릉이 대여 후 어느정도의 시간이 흘렀는지 개인이 별도의 행위(ex. 기록, 알람)를 하지 않으면 확인이 어려움.  
   
 > #### :point_right: 실시간(Online) 데이터를 활용해 위치, 대여 정보를 파악하고 사용시간을 간편하게 볼 수 있는 서비스 필요  
   
 * * *
   
     
      
  2. 데이터 수집  
 - 서울 열린 데이터 광장 제공 Open API  
   [서울특별시 공공자전거 대여소 정보](http://data.seoul.go.kr/dataList/OA-13252/F/1/datasetView.do;jsessionid=CBE9704CC496FEC9796117C0EB260453.new_portal-svr-21, "서울특별시 공공자전거 대여소 정보")
   , [서울특별시 공공자전거 실시간 대여정보](http://data.seoul.go.kr/dataList/OA-15493/A/1/datasetView.do#, "서울특별시 공공자전거 실시간 대여정보")
   
   <img width="497" alt="issue_jw_1" src="https://user-images.githubusercontent.com/56306637/77856429-171e1480-7232-11ea-9de3-9c51245459b4.PNG">    
     
     > API sample URL 이미지  
     > 변수명은 서울 열린 데이터 광장 사이트 참고 
   * * *
3. 데이터 활용   
> * 실시간 대여소 위치, 대여 여부 확인  
> * 사용 시간 확인 및 알림 
> * 그 외 : 사용자 데이터 분석  
>   * 자주 가는 대여소  기능  
>   * 가까운 대여소 추천 기능  

완성형 서비스 예시 : [서울 자전거 따릉이](https://www.bikeseoul.com/app/station/moveStationRealtimeStatus.do, "서울 자전거 따릉이") 
