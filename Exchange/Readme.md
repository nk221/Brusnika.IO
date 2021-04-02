# Обмен данными
В файле [Exchage.md](https://github.com/nk221/Brusnika.IO/blob/master/Exchange/Exchange.md)  детальное описание формата обмена.

В каталоге [Examples](https://github.com/nk221/Brusnika.IO/blob/master/Exchange/Examples)  находятся примеры выгрузки данных.

# Общее описание структуры данных
## Каталог товаров
![alt text](https://github.com/nk221/Brusnika.IO/blob/master/Exchange/Images/Catalog.jpg?raw=true)

На странице "Каталог" видны следующие данные:
- Параметры заказа - данные из **StockOptions**
- Получение - **DeliveryTypes**
- В зависимости от значения **DeliveryTypes.IsDeliveryToCustomer** видно Магазин (**Stores**) или адрес покупателя
- Список групп товаров - данные из **ProductCategories** и **ProductGroups**, в которых нет родителя, отсортированные по **SortOrder**

## Список товаров
![alt text](https://github.com/nk221/Brusnika.IO/blob/master/Exchange/Images/ProductList.jpg?raw=true)

В список попадаем в результате перехода по группе, поиска по названию товара или поиска по штрих-коду товара. В результате перехода получаем список товаров из **Products**. Из этого списка находим группы (**ProductGroups**) в которых состоят эти товары и их названия попадают в список групп под строкой поиска. Цена и доступное количество у товара берется из **PriceData** и **StoreData** соответственно, с учетом выбранного (прямо или косвенно через адрес доставки) магазина на странице "Каталог".

## Карточка товара
![alt text](https://github.com/nk221/Brusnika.IO/blob/master/Exchange/Images/ProductCard.jpg?raw=true)

Картинки - изображения из **ProductImages**

### Свойства товара
Все свойства поделены на группы (**PropertyGroups**). Если у группы нет **ParentPropertyGroupId**, то эта группа становится страницей в карточке товара.
Например на изображении ниже это "Характеристики", "Состав" и "Описание".

Для каждой корневой группы выбираются подгруппы и они располагаются на соответствующей странице свойств. Тут это "Пищевая ценность", "Энергетическая ценность" и т.п. расположены они в соответствие с **SortOrder**.

Группа свойств имеет свойства **PropertyTypes** которые в нее входят. Например тут, у группы "Пищевая ценность" есть свойства Белки, Жиры и Углеводы. 

За то, как отображаются свойства, входящие в группу свойств  отвечает поле **PropertyViewType** из **PropertyGroups**. 

Оно может принимать одно из 3 значений:
- List - список, то, как изображено свойство "Общие"
- Boxes - в прямоугольниках, то как изображено "Пищевая ценность" и "Энергетическая ценность"
- Text - просто текст

Значения свойств для конкретного товара берется из **ProductPropertyValues**

## Создание заказа
![alt text](https://github.com/nk221/Brusnika.IO/blob/master/Exchange/Images/Checkout.jpg?raw=true)

- Получение - **DeliveryTypes**
- В зависимости от значения **DeliveryTypes.IsDeliveryToCustomer** видно Магазин ( **Stores**) или адрес покупателя
- Тип оплаты - **PaymentTypes**