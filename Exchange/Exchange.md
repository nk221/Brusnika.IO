# Описание формата обмена
Версия 0.3

## Stores
Магазин
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(256)|Наименование

## ProductGroups
Группа товаров
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(64)|Наименование
ParentGroupId|String(40)|Код родителя
ImageUrl|String(1024)|Картинка
SortOrder|Int32|Сортировка
Products|Product []|Членство товаров в группе
IsDisabled *|Boolean|Отключена

## ProductCategories
Категория товаров
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(64)|Наименование
ImageUrl|String(1024)|Картинка
SortOrder|Int32|Сортировка
Products|Product []|Членство товаров в категории
CustomerProducts|Product []|Служебное, для персонализированного членства товаров в категории
CustomerProductCategoryMembership|CustomerProductCategoryMembership []|Персонализированная принадлежность товара категориям
IsDisabled *|Boolean|Отключена

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
Images|ProductImage []|Картинки
IsDisabled *|Boolean|Отключен
Barcodes|Barcode []|Штрих-коды

## ProductGroupMemberships
Членство товара в группах
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
ProductGroupId *|String(40)|Код группы

## ProductCategoryMemberships
Членство товара в категориях
Поле|Тип|Описание
----|---|---------
ProductId *|String(40)|Код товара
ProductCategoryId *|String(40)|Код категории

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

## PropertyGroups
Группа свойств сущностей
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
Name *|String(128)|Наименование
SortOrder|Int32|Сортировка
ParentPropertyGroupId|String(40)|Код родителя
ChildPropertyGroups|PropertyGroup []|Членство товаров в группе
PropertyViewType|PropertyViewTypes|То, как отображаются свойства этой группы

## PropertyTypes
Тип свойств сущностей
Поле|Тип|Описание
----|---|---------
Id *|String(40)|Код
PropertyGroupId *|String(40)|Код группы свойств
Name *|String(1024)|Наименование
ValueType|ValueTypes|Тип данных
SortOrder|Int32|Сортировка
PropertyOptions|PropertyOptions []|Варианты значений для типа List

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
