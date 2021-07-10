# Blog-Project

<br>

 ## 📌 MOVIE CLOSER ( 가명 ) 
> #### 영화 리뷰 OPEN BLOG 

<br>

## 1. 제작 기간 & 참여 인원
* 2021년 6월 25일 ~ 
* 개인 프로젝트 

<br>

## 2. 사용기술
`Back-end`   
* Java 15
* MySQL 
* Apache Tomcat 9.0v
* JSP
* Servlet



`Front-end`  
* JSP
* BootStrap 


`Tool`   
* Eclipse 2021-03
* Navicat Premium 15.0.25v


<br>


### 3. ERD 설계 



<br>

## 4. 요구사항


<br>

## 5. 핵심기능
#### 이 서비스의 핵심 기능은 컨텐츠 등록 기능입니다. 
#### 사용자들이 작성한 영화 리뷰, 기사 등에 대한 컨텐츠를 모든 사용자들이 볼 수 있습니다.
#### 글 뿐만 아니라 사진업로드, 수정, 삭제 또한 가능합니다.
#### 홈에서는 swiper-slide로 최신글과 인기글, 내가 관심갈만 한 글을 볼 수 있습니다.

<br>


## 6. 핵심 트러블 슈팅 (코드 안에 URL 삽입) 
6.1 컨텐츠 필터와 페이징 처리 문제
* 저는 이 서비스가 페이스북이나 인스타그램처럼 가볍게, 자주 사용되길 바라는 마음으로 개발했습니다.    
때문에 페이징 처리도 무한 스크롤을 적용했습니다.
* 하지만 무한 스크롤, 페이징 혹은 "더보기" 버튼? 어떤 걸 써야할까 라는 글을 읽고 무한 스크롤의 단점들을 알게 되었고,    
다양한 기준(카테고리, 사용자, 등록일, 인기도)의 게시물 필터 기능을 넣어서 이를 보완하고자 했습니다.    
* 그런데 게시물이 필터링 된 상태에서 무한 스크롤이 동작하면,    
필터링 된 게시물들만 DB에 요청해야 하기 때문에 아래의 기존 코드처럼 각 필터별로 다른 Query를 날려야 했습니다.

<br>

📍 기존코드
* 이 때 카테고리로 게시물을 필터링 하는 경우,   
 각 게시물은 최대 3개까지의 카테고리(tag)를 가질 수 있어 해당 카테고리를 포함하는 모든 게시물을 질의해야 했기 때문에
* 아래 개선된 코드와 같이 QueryDSL을 사용하여 다소 복잡한 Query를 작성하면서도 페이징 처리를 할 수 있었습니다.
   
📍 개선된 코드 


## 7. 그 외 트러블 슈팅

<br>


## 8. SERVLET & JSP 설명 
about-us.jsp : 홈페이지 소개글 페이지 / 블로그 관리 기능은 따로 구현하지 않으므로 화면에서 처리
author-post.jsp : 로그인 한 작성자의 글 목록 페이지 / 로그인 사용자가 등록한 글이 없다면 no-post.jsp로 보내 글쓰기 유도
blog-details.jsp : 작성글을 볼 수 있는 블로그 상세 페이지 / 작성한 글 뿐만 아니라 , 같은 카테고리의 다른 글과 다른 회원들이 최근 작성한 글 swiper-slide로 포함 
category.jsp : 카테고리 별 글 목록 페이지
contact-us.jsp : 비회원을 포함한 사용자가 문의를 남길 수 있는 페이지 / 보통 문의 확인을 작성한 사용자에게 email 보내주지만, 여기서는 DB에 문의 내역을 저장하기만 구현
error-404.jsp : 각 페이지에서 에러 발생시 가게되는 페이지 / 각 페이지에 에러 페이지를 명시함
index.jsp : 블로그의 홈 화면 페이지 / 회원들이 작성한 글 리스트에서 랜덤으로 하나를 뽑아 보여줌, 조회수 순으로 인기글 랭크인, 인기주제는 화면에서만 처리, 내가 관심갈만 한 글에는 최근 작성글의 같은 카테고리 글들을 모아 swiper-slide로 보여줌, 유튜브 영상을 링크하여 영화 예고편을 화면에서만 처리해줌


<br>
