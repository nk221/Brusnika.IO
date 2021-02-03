# Описание формата обмена
Версия 0.2

## ProductGroups
Группа товаров
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(64)|Наименование
ParentGroupId|String(40)|Код родителя
ImageUrl|String(1024)|Картинка
SortOrder|Int32|Сортировка
Products|string []|Членство товаров в группе
IsDisabled *|Boolean|Отключена

## ProductCategories
Категория товаров
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(64)|Наименование
ImageUrl|String(1024)|Картинка
SortOrder|Int32|Сортировка
Products|string []|Членство товаров в категории
IsDisabled *|Boolean|Отключена

## Products
Товар
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(1024)|Наименование
Description|String|Описание
MinimumOrderQuantity *|Decimal|Минимальная партия
OrderQuantityMultiplier *|Decimal|Множитель заказанного количества
ImageUrl|String(1024)|Картинка
Properties|string []|Свойства
Groups|string []|Членство товара в группах
Categories|string []|Принадлежность товара категориям
Images|string []|Картинки
IsDisabled *|Boolean|Отключен
Barcodes|string []|Штрих-коды

## PropertyGroups
Группа свойств сущностей
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(128)|Наименование
SortOrder|Int32|Сортировка

## PropertyTypes
Тип свойств сущностей
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
PropertyGroupId *|String(40)|Код группы свойств
Name *|String(1024)|Наименование
ValueType|ValueTypes|Тип данных
SortOrder|Int32|Сортировка
PropertyOptions|string []|Варианты значений для типа List

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

(*) - обязательное поле
