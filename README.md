# ODEV 7

Merhabalar,

Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

    film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
    film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

3. customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

Kolay Gelsin.

# CEVAPLAR 

## 1.Soru:

SELECT rating FROM film
GROUP BY rating;

"PG"
"R"
"NC-17"
"PG-13"
"G"

## 2.Soru:

SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50;

13.99	55
20.99	57
27.99	53
29.99	53
12.99	55
14.99	51
22.99	55
21.99	55

## 3.Soru:

SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;

1	326
2	273

## 4.Soru:

SELECT country_id, COUNT(city) FROM city
GROUP BY country_id
ORDER BY COUNT(city) DESC
LIMIT 1;

44	60