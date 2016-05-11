### Разбор летучки 2

#### 1

Различие интерфейсов и абстрактных классов в java 8 (после того, как можно стало писать default в интерфейсах)

---

1. Абстрактные классы могут хранить состояние, а интерфейсы нет. (неверно говорить, что в абстрактных классах могут быть поля, а в интерфесах нет, ибо в интерфейсах они могут быть, только final и abstract)


#### 3
Что куда можно класть?

---

```java
List<? super Apple> list;
```
Можно класть только `Apple` или наследников `Apple`. А получать мы будем оттуда `Object`.

```java
List<? extends Apple> list;
```
Доставать будет `Apple`, а добавлять нельзя ничего (`null` разве что!)


#### 4

Не надо:
```java
<T> T max(Collection<? extends T> c, Comparator<? super T> cmp) {}
```
Надо:
```java
<T> T max(Collection<T> c, Comparator<? super T> cmp) {}
```

#### 5

Вопрос про `eqauls`

---

```java
class Point {
}

class ColoredPoint {
}
```
В слайдах посмотри, любитель.

#### 7

Анонимные классы в java 8

---

**Локальные** переменные должны быть `final` в java7, а в java8 не обязательно, там теперь такие переменные *effectively final*.

