# JUNIT 학습 - 배포를 위해서!! (혼자 개발할때는 JUNIT안해도 댐)

### DB는 기존 DB사용
### 1. 테이블 생성
```sql
-- product table --
CREATE TABLE product(
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(20) NOT NULL,
    product_price INT NOT NULL,
    product_qty INT NOT NULL,
    created_at TIMESTAMP NOT NULL
);

-- customer table --
CREATE TABLE customer(
    customer_id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(20) NOT NULL,
    password VARCHAR(20) NOT NULL,
    created_at TIMESTAMP
);

-- orders table --
CREATE TABLE orders(
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    product_id INT NOT NULL,
    created_at TIMESTAMP
);

-- utf8 --
ALTER TABLE product CONVERT TO CHARACTER SET UTF8;
ALTER TABLE customer CONVERT TO CHARACTER SET UTF8;
ALTER TABLE orders CONVERT TO CHARACTER SET UTF8;
```

### 2. 더미데이터 
```sql
INSERT INTO product(product_name, product_price, product_qty, created_at) VALUES('바나나', 3000, 98, NOW());
INSERT INTO product(product_name, product_price, product_qty, created_at) VALUES('딸기', 2000, 100, NOW());

INSERT INTO customer(username, PASSWORD, created_at) VALUES('ssar', '1234', NOW());
INSERT INTO customer(username, PASSWORD, created_at) VALUES('cos', '1234', NOW());

INSERT INTO orders(customer_id, product_id, created_at) VALUES(1, 1, NOW());
INSERT INTO orders(customer_id, product_id, created_at) VALUES(2, 1, NOW());
```