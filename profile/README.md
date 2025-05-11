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
│   └── default.conf       
├── uploads/               ← 정적 이미지 폴더
└── docker-compose.yml
```

### docker-compose.yml
```yml
services:
  admin-frontend:
    build: ./planvel-admin-frontend
    ports:
      - "3000:80"
    depends_on:
      - admin


  user-frontend:
    build: ./planvel-user-frontend
    ports:
      - "3002:80"
    depends_on:
      - user


  admin:
    build: ./planvel-admin
    ports: 
      - "8080:8080"
    volumes:
      - ./uploads:/uploads

  user:
    build: ./planvel-backend
    ports:
      - "8082:8080"
    volumes:
      - ./uploads:/uploads

  nginx:
    image: nginx:latest
    ports:
      - "8081:80"
    volumes:
      - ./uploads:/usr/share/nginx/html/uploads
      - ./nginx/default.conf:/etc/nginx/conf.d/default.conf
  
  mysql:
    image: mysql:8.0
    container_name: planvel-mysql
    ports:
      - "3309:3306"
    environment:
      MYSQL_ROOT_PASSWORD: 1234
      MYSQL_DATABASE: planvel_db
      MYSQL_USER: planvel
      MYSQL_PASSWORD: planvel1234
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  mysql_data:


```
