# Planvel : 여행 계획 플랫폼
- 25.05.05 - 25.05.16
- 한세영, 변지민, 정현경
- [프로젝트 문서(API 명세, 회의록 등)](https://veiled-foe-fd5.notion.site/2-1e577da8c8038015ad8cf4f60b8bea86?pvs=4)

### 기능
1. 여행 계획 만들기 지원(여행지, 교통, 숙박, 관광지 정보 제공)
2. 여행 계획표 공유
3. 여행지 리뷰 작성


### Skill

Java, Spring boot, MySQL, JPA(백엔드 서버), Mybatis(관리자 서버), Docker


### ERD


### project structure
```shell
planvel/
├── planvel-admin/
│   └── Dockerfile
├── planvel-backend/
│   └── Dockerfile
├── planvel-admin-frontend
│   └── Dockerfile
├── planvel-user-frontend
│   └── Dockerfile
├── nginx/
│   └── admin.conf       
├── uploads/               ← 정적 이미지 폴더
└── docker-compose-admin.yml
└── docker-compose-service.yml
└── docker-compose-mysql.yml
```
