# Movie For You
## AI Movie Recommendation Project
- 사용자의 단어 입력에 따른 영화를 추천해주는 인공지능 추천 시스템입니다.
- 소셜 리뷰 데이터를 기반으로 입력값과의 코사인유사도를 측정하여 영화를 추천합니다.
  - 복수개의 단어 입력 가능 (예: 박진감+유쾌한 / 가족+힐링 )
  - 추천받은 영화에 대한 감성분석 제공
  - 리뷰 데이터 기반 평가지수 제공
## 데이터 수집
1. 네이버 영화 리뷰
  - 기존 영화목록이 아닌 연도별 목차에서 영화목록을 가져왔습니다. (목록과 다른 부분은 재검색)
  - HTML코드가 일정하지 않은 부분이 있어서 예외처리(2개) 했습니다.
  - 연도 당 영화 평균 600개정도의 데이터를 크롤링 했습니다, 약 4만개
2. 네이버 블로그 리뷰
  - 영화진흥위원회 영화 데이터 베이스를 기반으로 하여 관객수가 백만이상의 영화에 대한 블로그 리뷰를 가져왔습니다(기간 : 2006-03-26 ~ 2020-07-18, 정렬 : 정확도순)
  - Selenium, webdriver를 이용했고, 블로그 타이틀, URL을 타고 들어가 내용 크롤링
  - 영화당 리뷰 5개씩 크롤링 (크롤링이 금지된 블로그의 리뷰, 네이버 검색어 검열에 걸리는 영화 2개 제외), 약 8천개
3. 다음 영화 리뷰
  - 다음영화리뷰 사이트에서 영화리스트의 title을 검색하여, 각 영화에 맞는 리뷰를 가져왔습니다.  
  - 검색 시, 검색은 되지만, 영화리뷰가 존재하지않는 경우가 있어 try~except를 사용하여  NoSuchElementException을 예외처리하였습니다.     
  - 다음 영화사이트의 경우, 영화마다의 코드와 페이지 변경 방식이기 때문에, selunium을 사용하여 페이지 변경을 반영하였습니다.     
  - 정적페이지의 리뷰를 받아오기 위해서, BS4를 이용해 10페이지까지의 리뷰를 수집하였습니다, 약 80만개
4. 왓챠피디아 영화 리뷰
  - 왓챠피디아 (구 왓챠)는 국내에서 제일 많이 쓰는 영화, TV 프로그램 추천 프로그램 앱입니다.  
  - 검색창에 영화 제목을 검색하여 접근하는 방식으로 크롤링을 진행. 리뷰가 스크롤을 내려야 로딩이 되는 방식이라 코드에 반영하였습니다. 
  - Beautifulsoup이 아닌 Selenium, webdriver 만을 이용해 태그로 접근하여 리뷰를 가져왔습니다. 
  - 모든 리뷰를 가져오는 것이 아니라서 스크롤 내리는 정도를 일정하게 지정하였습니다, 약 7만개
## 데이터정제
1. 
2.   
3. 
## 추천시스템
1. 
2. 
3.   
4. 
## Consine Similarity 추천시스템
1. 
2. 
3.   
4. 
## 감성분석 
1. 
2.  
3.   
