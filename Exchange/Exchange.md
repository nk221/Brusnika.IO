# Описание формата обмена
Версия 0.3

## Products
Товар
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(1024)|Наименование
MinimumOrderQuantity *|Decimal|Минимальная партия
OrderQuantityMultiplier *|Decimal|Множитель заказанного количества
Unit *|String(64)|Единица измерения
ImageUrl|String(1024)|Картинка для списка товаров
IsDisabled *|Boolean|Отключен

## ProductBarcodes
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
Code *|String(20)|Штрих-код

## ProductImages
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
SortOrder|Int32|Сортировка
Url|String(1024)|Картинка

## Stores
Магазин
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(256)|Наименование

## StoreData
Данные об остатках товара по складу
Поле|Тип|Описание
----|---|---------
StoreId *|String(40)|Код склада
ProductId *|String(40)|Код товара
AvailableQuantity *|Decimal|Количество на складе

## PriceData
Цены на товары
Поле|Тип|Описание
----|---|---------
StoreId *|String(40)|Код склада
ProductId *|String(40)|Код товара
Price *|Decimal|Цена

## ProductCategories
Категория товаров
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(64)|Наименование
ImageUrl|String(1024)|Картинка
SortOrder|Int32|Сортировка
IsDisabled *|Boolean|Отключена

## ProductCategoryMemberships
Принадлежность товара к категории
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
ProductCategoryId *|String(40)|Код категории

## ProductGroups
Группа товаров
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(64)|Наименование
ParentGroupId|String(40)|Код родителя
ImageUrl|String(1024)|Картинка
SortOrder|Int32|Сортировка
IsDisabled *|Boolean|Отключена

## ProductGroupMemberships
Принадлежность товара к группе
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
ProductGroupId *|String(40)|Код группы

## PropertyGroups
Группа свойств сущностей
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(128)|Наименование
SortOrder|Int32|Сортировка
ParentPropertyGroupId|String(40)|Код родителя
PropertyViewType|PropertyViewTypes|То, как отображаются свойства этой группы. [List,Boxes,Text]

## PropertyTypes
Тип свойств сущностей
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
PropertyGroupId *|String(40)|Код группы свойств
Name *|String(1024)|Наименование
ValueType|ValueTypes|Тип данных. [Integer,Decimal,String,Date,List]
SortOrder|Int32|Сортировка

## PropertyOptions
Варианты значений свойства, если тип свойства List
Поле|Тип|Описание
----|---|---------
PropertyTypeId *|String(40)|Код типа свойства
Id *|String(40)|Код
Value|String(1024)|Значение
SortOrder|Int32|Порядок

## ProductPropertyValues
Значения свойств товаров
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
PropertyTypeId *|String(40)|Код типа свойства
Value|String|Значение

## DeliveryTypes
Поле|Тип|Описание
----|---|---------
Id *|Int32|Код
Name *|String(1024)|Наименование
IsDeliveryToCustomer *|Boolean|Доставка на адрес покупателя

## OrderStatuses
Статус заказа
Поле|Тип|Описание
----|---|---------
Id *|Int32|Код
Name *|String(1024)|Наименование

## PaymentTypes
Тип оплаты
Поле|Тип|Описание
----|---|---------
Id *|Int32|Код
Name *|String(1024)|Наименование

## StockOptions
Варианты отбора товаров
Поле|Тип|Описание
----|---|---------
Id *|Int32|Код
Name *|String(1024)|Наименование
Comment|String(5120)|Комментарий

(*) - обязательное поле
