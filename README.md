 

# INNER JOIN 

- Müşteri verilen sipariş için ne kadar ücret ödeyecek. 

``` sql
SELECT first_name,last_name,total_price FROM orders o 

INNER JOIN customers cu 

ON cu.customer_id = o.customer_id; 
```

![image](https://user-images.githubusercontent.com/58787155/204285557-4bae25de-b212-48a0-9ae9-c8a51856fefa.png)  

# LEFT JOIN 
- Null ürünleri gösterme

![image](https://user-images.githubusercontent.com/58787155/204294432-f4e1a6a5-8a2b-41af-81b6-c5c88559d88d.png)
``` sql
SELECT * FROM Customers cm 
LEFT JOIN Orders ord 
ON cm.customer_id = ord.customer_id 
```
# RIGHT JOIN 
- Artık satılmayacak ürünleri göster Yani müşterisi olmayan ürünler 

 ``` sql
SELECT first_name, last_name, total_price, name 

FROM customers cu 

RIGHT JOIN orders o  

ON cu.customer_id = o.customer_id 

RIGHT JOIN order_details od 

ON o.order_id = od.order_id 

RIGHT JOIN products pd  

ON od.product_id=pd.product_id; 

 ```
 ![image](https://user-images.githubusercontent.com/58787155/204294764-27a3f41b-fcba-42a3-9aa1-3a0c9cfdd8ef.png)

# INSERT 
-Yeni kategori eklemek

 ``` sql
INSERT INTO  categories(category_name,description)
VALUES ('Beyaz Eşya','Ev aletleri buz dolabı');
SELECT * FROM categories;
 ```
  ![image](https://user-images.githubusercontent.com/58787155/204293188-a33bc8cd-7c55-4d66-a72d-cc828e8ecba4.png)

# UPDATE 
- Ürünün stok ve birim fiyatını güncelle.

![image](https://user-images.githubusercontent.com/58787155/204286579-f5be4650-c688-4d77-9257-4d2ab3c08e77.png)
 ``` sql
UPDATE products
Set stock = 250 , unit_price = 1000
where product_id = 200
 ```
![image](https://user-images.githubusercontent.com/58787155/204286702-fa78385d-a895-4403-9425-d2deb8a02c67.png)


# IN
 ``` sql
SELECT * FROM products WHERE name IN('Tulpar')
 ```
 
# UPDATE
- 200 numaralı ürünün stok ve birim fiyatını güncellemek.

![image](https://user-images.githubusercontent.com/58787155/204287386-35d76fc2-4e26-4dae-bd44-5776a908063a.png)

   ``` sql
UPDATE products
Set stock = 250 , unit_price = 1000
where product_id = 200
 ```

# GROUP BY 

- Müşterilerin hangi şehirlerde kaç tane olduğunu bul.
 ``` sql
SELECT city_name,COUNT(city_name)
FROM customers cm
JOIN addresses ad
on cm.customer_id = ad.customer_id 
JOIN cities ci
ON ad.city_id = ci.city_id
group by city_name
 ```
 
 
 ![image](https://user-images.githubusercontent.com/58787155/204294915-f1fb504c-ca5d-453b-b886-0238e6ad1783.png)


# HAVING 
- Toplam ücreti 80 den büyük olan ürünleri ve hangi müşteride olduğunu getir.

``` sql
SELECT first_name,last_name ,total_price,order_number FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id
GROUP BY total_price,first_name,last_name,total_price,order_number
HAVING total_price > 80;
```
  ![image](https://user-images.githubusercontent.com/58787155/204296216-337708ae-ce33-481f-852f-b34b97bd9b6d.png)


# BETWEEN 
- Belirtilen aralıktaki ürünlerin zamlı fiyatlarıyla değiştir.

![image](https://user-images.githubusercontent.com/58787155/204294238-544ab632-469c-40f3-8037-88d45f31f281.png)

  ``` sql
UPDATE products SET unit_price =unit_price-3
WHERE unit_price BETWEEN 0 AND 10;
 ```
 ![image](https://user-images.githubusercontent.com/58787155/204294297-8949a2f3-88fe-46d5-8533-03b06da24016.png)


 
