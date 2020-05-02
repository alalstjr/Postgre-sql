# 반복문과 INSERT 문법을 조합한 쿼리

~~~
do
$$
    begin
        for i in 10..10000
            loop
                insert into university (uni_subject, uni_content, uni_name, ip, id, control_status,
                                        public_status, created_date, modified_date, uni_atmosphere, uni_price,
                                        account_id)
                values ('subject', 'content', '건국대학교', 'ip', i, false, true,
                        '2020-03-04 03:01:21.878393', '2020-03-04 03:01:21.878393',1, 1, 1);
            end loop;
    end;
$$;
~~~

# 테이블 수정

~~~
UPDATE 테이블명 SET 컬럼명 = 0;
~~~

# 테이블 컬럼 NULL 상태변경

NOT NULL  추가/제거

~~~
ALTER TABLE 테이블명 ALTER COLUMN 컬럼명 SET NOT NULL
ALTER TABLE 테이블명 ALTER COLUMN 컬럼명 DROP NOT NULL
~~~

# 테이블 컬럼 이름 변경

~~~
ALTER TABLE 테이블명 RENAME COLUMN 현재컬럼명 TO 새컬럼명
~~~

# 기타

~~~
SELECT * FROM fileStorage;

-- UPDATE product_order SET orderState = 0;
-- UPDATE product SET filestorageids = ',13,' WHERE id = 1;

-- SELECT productid FROM product_access WHERE ageRange = 20;

/* 테이블 컬럼 추가 */
-- ALTER TABLE product_order ADD productName VARCHAR;

/* 테이블 컬럼 타입변경 */
-- ALTER TABLE product_order ALTER COLUMN accountId TYPE integer USING (accountId::BIGINT);

/* JOIN 조회 */
-- SELECT * FROM product_order INNER JOIN product ON product_order.productIds LIKE '%,'||product.id||',%';
--
-- SELECT * FROM
--     product
-- WHERE
--         enabled = true
--   AND
--             shopGroupIds LIKE '%,1,%'
-- ORDER BY createddate DESC

~~~