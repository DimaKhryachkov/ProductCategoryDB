# ProductCategoryDB
В базе данных MS SQL Server есть продукты и категории. Одному продукту может соответствовать много категорий, в одной категории может быть много продуктов

## Схема БД
![alt text](https://github.com/DimaKhryachkov/ProductCategoryDB/blob/ebb89d03a8b0955d35e51e4257c0cd4c670e158a/%D0%A1%D1%85%D0%B5%D0%BC%D0%B0.PNG)

## SQL запрос для выбора всех пар «Имя продукта – Имя категории» 
Если у продукта нет категорий, то его имя все равно должно выводиться.

    SELECT ProductName, CategoryName
    FROM Product
    LEFT JOIN Product_Category ON Product.Id = Product_Category.ProductId
    LEFT JOIN  Category ON Category.Id = Product_Category.CategoryId;
