# Домашнее задание
## Использование neo4j

Выполнение домашнего задания:
Взять 4-5 популярных туроператора. Каждый туроператор должен быть представлен в виде ноды neo4j
Взять 10-15 направлений, в которые данные операторы предоставляют путевки. Представить направления в виде связки нод: страна - конкретное место
```sql
MERGE (op1:Operator {name : "БИБЛИОГЛОБУС"})
MERGE (op2:Operator {name : "ТУИ"})
MERGE (op3:Operator {name : "АНЕКСТУР"})
MERGE (op4:Operator {name : "CORAL TRAVEL"})
MERGE (op5:Operator {name : "ТЕЗТУР"})
MERGE (op6:Operator {name : "АЛЕАН"})
MERGE (op7:Operator {name : "INTOURIST"})

MERGE (dir1:Direction {name : "Курорты Азовского моря"})
MERGE (dir2:Direction {name : "Калининградская область"})
MERGE (dir3:Direction {name : "Краснодарский край"})
MERGE (dir4:Direction {name : "Крым"})
MERGE (dir5:Direction {name : "Карелия"})
MERGE (dir6:Direction {name : "Абхазия"})
MERGE (dir7:Direction {name : "Азербайджан"})
MERGE (dir8:Direction {name : "Турция"})
MERGE (dir9:Direction {name : "Китай"})
MERGE (dir10:Direction {name : "Тунис"})
MERGE (dir11:Direction {name : "Танзания"})

MERGE (op1) -[:OPER_DIR]-> (dir1)
MERGE (op1) -[:OPER_DIR]-> (dir2)
MERGE (op1) -[:OPER_DIR]-> (dir3)
MERGE (op1) -[:OPER_DIR]-> (dir4)
MERGE (op1) -[:OPER_DIR]-> (dir5)
MERGE (op1) -[:OPER_DIR]-> (dir6)
MERGE (op1) -[:OPER_DIR]-> (dir7)
MERGE (op1) -[:OPER_DIR]-> (dir8)
MERGE (op1) -[:OPER_DIR]-> (dir9)
MERGE (op1) -[:OPER_DIR]-> (dir10)
MERGE (op1) -[:OPER_DIR]-> (dir11)

MERGE (op2) -[:OPER_DIR]-> (dir5)
MERGE (op2) -[:OPER_DIR]-> (dir6)
MERGE (op2) -[:OPER_DIR]-> (dir7)
MERGE (op2) -[:OPER_DIR]-> (dir8)
MERGE (op2) -[:OPER_DIR]-> (dir9)
MERGE (op2) -[:OPER_DIR]-> (dir10)
MERGE (op2) -[:OPER_DIR]-> (dir11)

MERGE (op3) -[:OPER_DIR]-> (dir1)
MERGE (op3) -[:OPER_DIR]-> (dir2)
MERGE (op3) -[:OPER_DIR]-> (dir3)
MERGE (op3) -[:OPER_DIR]-> (dir4)
MERGE (op3) -[:OPER_DIR]-> (dir7)
MERGE (op3) -[:OPER_DIR]-> (dir8)
MERGE (op3) -[:OPER_DIR]-> (dir9)
MERGE (op3) -[:OPER_DIR]-> (dir10)
MERGE (op3) -[:OPER_DIR]-> (dir11)

MERGE (op4) -[:OPER_DIR]-> (dir1)
MERGE (op4) -[:OPER_DIR]-> (dir2)
MERGE (op4) -[:OPER_DIR]-> (dir3)
MERGE (op4) -[:OPER_DIR]-> (dir4)
MERGE (op4) -[:OPER_DIR]-> (dir5)
MERGE (op4) -[:OPER_DIR]-> (dir10)
MERGE (op4) -[:OPER_DIR]-> (dir11)

MERGE (op5) -[:OPER_DIR]-> (dir1)
MERGE (op5) -[:OPER_DIR]-> (dir5)
MERGE (op5) -[:OPER_DIR]-> (dir6)
MERGE (op5) -[:OPER_DIR]-> (dir7)
MERGE (op5) -[:OPER_DIR]-> (dir8)
MERGE (op5) -[:OPER_DIR]-> (dir9)

MERGE (op6) -[:OPER_DIR]-> (dir1)
MERGE (op6) -[:OPER_DIR]-> (dir2)
MERGE (op6) -[:OPER_DIR]-> (dir6)
MERGE (op6) -[:OPER_DIR]-> (dir7)
MERGE (op6) -[:OPER_DIR]-> (dir8)

MERGE (op7) -[:OPER_DIR]-> (dir2)
MERGE (op7) -[:OPER_DIR]-> (dir3)
MERGE (op7) -[:OPER_DIR]-> (dir4)
MERGE (op7) -[:OPER_DIR]-> (dir6)
MERGE (op7) -[:OPER_DIR]-> (dir7)
MERGE (op7) -[:OPER_DIR]-> (dir8)
MERGE (op7) -[:OPER_DIR]-> (dir10)
MERGE (op7) -[:OPER_DIR]-> (dir11)

```
Графическое представление данных:<br/>
![Data Operator - Direction](/img/oper_dir.jpg)

Взять ближайшие к туристическим локациям города, в которых есть аэропорты или вокзалы и представить их в виде нод

```sql
CREATE (ct1:City {name : "Мариуполь"})
CREATE (ct2:City {name : "Таганрог"})
CREATE (ct3:City {name : "Ейск"})
CREATE (ct4:City {name : "Калининград"})
CREATE (ct5:City {name : "Светлогорск"})
CREATE (ct6:City {name : "Гвардейск"})
CREATE (ct7:City {name : "Анапа"})
CREATE (ct8:City {name : "Туапсе"})
CREATE (ct9:City {name : "Сочи"})
CREATE (ct10:City {name : "Лазаревское"})
CREATE (ct11:City {name : "Симферополь"})
CREATE (ct12:City {name : "Севастополь"})
CREATE (ct13:City {name : "Форос"})
CREATE (ct14:City {name : "Ялта"})
CREATE (ct15:City {name : "Петрозаводск"})
CREATE (ct16:City {name : "Кижи"})
CREATE (ct17:City {name : "Кондопога"})
CREATE (ct18:City {name : "Шёлтозеро"})
CREATE (ct19:City {name : "Сухум"})
CREATE (ct20:City {name : "Гагра"})
CREATE (ct21:City {name : "Гудаута"})
CREATE (ct22:City {name : "Баку"})
CREATE (ct23:City {name : "Сумгаит"})
CREATE (ct24:City {name : "Стамбул"})
CREATE (ct25:City {name : "Аланья"})
CREATE (ct26:City {name : "Анталья"})
CREATE (ct27:City {name : "Измир"})
CREATE (ct28:City {name : "Хайнань"})
CREATE (ct29:City {name : "Хейхе"})
CREATE (ct30:City {name : "Шанхай"})
CREATE (ct31:City {name : "Тунис"})
CREATE (ct32:City {name : "Карфаген"})
CREATE (ct33:City {name : "Танзания"})
CREATE (ct34:City {name : "Занзибар"})
CREATE (ct35:City {name : "Москва"})
CREATE (ct36:City {name : "Тула"})
CREATE (ct37:City {name : "Воронеж"})
CREATE (ct38:City {name : "Курск"})
CREATE (ct39:City {name : "Ростов-на-Дону"})
CREATE (ct40:City {name : "Краснодар"})
CREATE (ct41:City {name : "Санкт-Петербург"})
CREATE (ct42:City {name : "Благовещенск"})

MERGE (p:Direction {name: "Курорты Азовского моря"})-[:DIR_CITY]->(m:City {name: "Мариуполь"}) RETURN p, m;
MERGE (p:Direction {name: "Курорты Азовского моря"})-[:DIR_CITY]->(m:City {name: "Таганрог"}) RETURN p, m;
MERGE (p:Direction {name: "Курорты Азовского моря"})-[:DIR_CITY]->(m:City {name: "Ейск"}) RETURN p, m;
MERGE (p:Direction {name: "Калининградская область"})-[:DIR_CITY]->(m:City {name: "Калининград"}) RETURN p, m;
MERGE (p:Direction {name: "Калининградская область"})-[:DIR_CITY]->(m:City {name: "Светлогорск"}) RETURN p, m;
MERGE (p:Direction {name: "Калининградская область"})-[:DIR_CITY]->(m:City {name: "Гвардейск"}) RETURN p, m;
MERGE (p:Direction {name: "Краснодарский край"})-[:DIR_CITY]->(m:City {name: "Анапа"}) RETURN p, m;
MERGE (p:Direction {name: "Краснодарский край"})-[:DIR_CITY]->(m:City {name: "Туапсе"}) RETURN p, m;
MERGE (p:Direction {name: "Краснодарский край"})-[:DIR_CITY]->(m:City {name: "Сочи"}) RETURN p, m;
MERGE (p:Direction {name: "Краснодарский край"})-[:DIR_CITY]->(m:City {name: "Лазаревское"}) RETURN p, m;
MERGE (p:Direction {name: "Крым"})-[:DIR_CITY]->(m:City {name: "Симферополь"}) RETURN p, m;
MERGE (p:Direction {name: "Крым"})-[:DIR_CITY]->(m:City {name: "Севастополь"}) RETURN p, m;
MERGE (p:Direction {name: "Крым"})-[:DIR_CITY]->(m:City {name: "Форос"}) RETURN p, m;
MERGE (p:Direction {name: "Крым"})-[:DIR_CITY]->(m:City {name: "Ялта"}) RETURN p, m;
MERGE (p:Direction {name: "Карелия"})-[:DIR_CITY]->(m:City {name: "Петрозаводск"}) RETURN p, m;
MERGE (p:Direction {name: "Карелия"})-[:DIR_CITY]->(m:City {name: "Кижи"}) RETURN p, m;
MERGE (p:Direction {name: "Карелия"})-[:DIR_CITY]->(m:City {name: "Кондопога"}) RETURN p, m;
MERGE (p:Direction {name: "Карелия"})-[:DIR_CITY]->(m:City {name: "Шёлтозеро"}) RETURN p, m;
MERGE (p:Direction {name: "Абхазия"})-[:DIR_CITY]->(m:City {name: "Сухум"}) RETURN p, m;
MERGE (p:Direction {name: "Абхазия"})-[:DIR_CITY]->(m:City {name: "Гагра"}) RETURN p, m;
MERGE (p:Direction {name: "Абхазия"})-[:DIR_CITY]->(m:City {name: "Гудаута"}) RETURN p, m;
MERGE (p:Direction {name: "Азербайджан"})-[:DIR_CITY]->(m:City {name: "Баку"}) RETURN p, m;
MERGE (p:Direction {name: "Азербайджан"})-[:DIR_CITY]->(m:City {name: "Сумгаит"}) RETURN p, m;
MERGE (p:Direction {name: "Турция"})-[:DIR_CITY]->(m:City {name: "Стамбул"}) RETURN p, m;
MERGE (p:Direction {name: "Турция"})-[:DIR_CITY]->(m:City {name: "Аланья"}) RETURN p, m;
MERGE (p:Direction {name: "Турция"})-[:DIR_CITY]->(m:City {name: "Анталья"}) RETURN p, m;
MERGE (p:Direction {name: "Турция"})-[:DIR_CITY]->(m:City {name: "Измир"}) RETURN p, m;
MERGE (p:Direction {name: "Китай"})-[:DIR_CITY]->(m:City {name: "Хайнань"}) RETURN p, m;
MERGE (p:Direction {name: "Китай"})-[:DIR_CITY]->(m:City {name: "Хейхе"}) RETURN p, m;
MERGE (p:Direction {name: "Китай"})-[:DIR_CITY]->(m:City {name: "Шанхай"}) RETURN p, m;
MERGE (p:Direction {name: "Тунис"})-[:DIR_CITY]->(m:City {name: "Тунис"}) RETURN p, m;
MERGE (p:Direction {name: "Тунис"})-[:DIR_CITY]->(m:City {name: "Карфаген"}) RETURN p, m;
MERGE (p:Direction {name: "Танзания"})-[:DIR_CITY]->(m:City {name: "Танзания"}) RETURN p, m;
MERGE (p:Direction {name: "Танзания"})-[:DIR_CITY]->(m:City {name: "Занзибар"}) RETURN p, m;
```

Графическое представление данных:<br/>
![Data Direction-City](/img/dir_city.jpg)


Представить маршруты между городами в виде связей. Каждый маршрут должен быть охарактеризован видом транспорта, который позволяет переместиться между точками.
```sql
MERGE (p:City {name: "Таганрог"}) MERGE (m:City {name: "Мариуполь"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Таганрог"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Краснодар"}) MERGE (m:City {name: "Ейск"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Калининград"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Калининград"}) MERGE (m:City {name: "Светлогорск"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Калининград"}) MERGE (m:City {name: "Гвардейск"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Краснодар"}) MERGE (m:City {name: "Анапа"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Краснодар"}) MERGE (m:City {name: "Туапсе"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Сочи"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Сочи"}) MERGE (m:City {name: "Лазаревское"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Симферополь"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Севастополь"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Севастополь"}) MERGE (m:City {name: "Форос"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Севастополь"}) MERGE (m:City {name: "Ялта"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Петрозаводск"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Петрозаводск"}) MERGE (m:City {name: "Кижи"}) MERGE (p)-[:transit {name:"ship"}]->(m);
MERGE (p:City {name: "Петрозаводск"}) MERGE (m:City {name: "Кондопога"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Петрозаводск"}) MERGE (m:City {name: "Шёлтозеро"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Сухум"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Сухум"}) MERGE (m:City {name: "Гагра"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Сухум"}) MERGE (m:City {name: "Гудаута"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Баку"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Баку"}) MERGE (m:City {name: "Сумгаит"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Стамбул"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Аланья"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Анталья"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Анталья"}) MERGE (m:City {name: "Измир"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Шанхай"}) MERGE (m:City {name: "Хайнань"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Благовещенск"}) MERGE (m:City {name: "Хейхе"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Шанхай"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Тунис"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Тунис"}) MERGE (m:City {name: "Карфаген"}) MERGE (p)-[:transit {name:"avto"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Танзания"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Танзания"}) MERGE (m:City {name: "Занзибар"}) MERGE (p)-[:transit {name:"avia"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Тула"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Тула"}) MERGE (m:City {name: "Воронеж"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Воронеж"}) MERGE (m:City {name: "Курск"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Курск"}) MERGE (m:City {name: "Ростов-на-Дону"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Ростов-на-Дону"}) MERGE (m:City {name: "Краснодар"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Санкт-Петербург"}) MERGE (p)-[:transit {name:"train"}]->(m);
MERGE (p:City {name: "Москва"}) MERGE (m:City {name: "Благовещенск"}) MERGE (p)-[:transit {name:"train"}]->(m);
```

Графическое представление данных:<br/>
![Data Route](/img/route.jpg)


Написать запрос, который бы выводил направление (со всеми промежуточными точками), который можно осуществить только наземным транспортом.
```sql
MATCH (st:City {name:"Москва"}), p=(st)-[m:transit*]->(e:City), (d:Direction)-[:DIR_CITY]-(e), (op:Operator)-[:OPER_DIR]-(d) 
 WITH p as pp,  relationships(p) as path, d.name as dir_name,  e.name as to_city , COLLECT(op.name) as oper_list
 WHERE ALL (ps IN path WHERE ps.name IN ["train","avto"])  
 RETURN dir_name, to_city, pp as path, oper_list
 ORDER BY dir_name, to_city
```
Результат:<br/>
```
╒════════════════════════╤══════════════╤═════════════════════════════════════════════════════════════╤═════════════════════════════════════════════════════════════╕
│dir_name                │to_city       │path                                                         │oper_list                                                    │
╞════════════════════════╪══════════════╪═════════════════════════════════════════════════════════════╪═════════════════════════════════════════════════════════════╡
│"Карелия"               │"Кондопога"   │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["CORAL TRAVEL", "БИБЛИОГЛОБУС", "ТЕЗТУР", "ТУИ"]            │
│                        │              │name: "Петрозаводск"})-[:transit {name: "avto"}]->(:City {nam│                                                             │
│                        │              │e: "Кондопога"})                                             │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Карелия"               │"Петрозаводск"│(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["CORAL TRAVEL", "БИБЛИОГЛОБУС", "ТЕЗТУР", "ТУИ"]            │
│                        │              │name: "Петрозаводск"})                                       │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Карелия"               │"Шёлтозеро"   │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["CORAL TRAVEL", "БИБЛИОГЛОБУС", "ТЕЗТУР", "ТУИ"]            │
│                        │              │name: "Петрозаводск"})-[:transit {name: "avto"}]->(:City {nam│                                                             │
│                        │              │e: "Шёлтозеро"})                                             │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Китай"                 │"Хейхе"       │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["ТУИ", "ТЕЗТУР", "БИБЛИОГЛОБУС", "АНЕКСТУР"]                │
│                        │              │name: "Благовещенск"})-[:transit {name: "avto"}]->(:City {nam│                                                             │
│                        │              │e: "Хейхе"})                                                 │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Краснодарский край"    │"Анапа"       │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["АНЕКСТУР", "БИБЛИОГЛОБУС", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Тула"})-[:transit {name: "train"}]->(:City {name: "Вор│                                                             │
│                        │              │онеж"})-[:transit {name: "train"}]->(:City {name: "Курск"})-[│                                                             │
│                        │              │:transit {name: "train"}]->(:City {name: "Ростов-на-Дону"})-[│                                                             │
│                        │              │:transit {name: "train"}]->(:City {name: "Краснодар"})-[:tran│                                                             │
│                        │              │sit {name: "avto"}]->(:City {name: "Анапа"})                 │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Краснодарский край"    │"Лазаревское" │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["АНЕКСТУР", "БИБЛИОГЛОБУС", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Сочи"})-[:transit {name: "train"}]->(:City {name: "Лаз│                                                             │
│                        │              │аревское"})                                                  │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Краснодарский край"    │"Сочи"        │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["АНЕКСТУР", "БИБЛИОГЛОБУС", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Сочи"})                                               │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Краснодарский край"    │"Туапсе"      │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["АНЕКСТУР", "БИБЛИОГЛОБУС", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Тула"})-[:transit {name: "train"}]->(:City {name: "Вор│                                                             │
│                        │              │онеж"})-[:transit {name: "train"}]->(:City {name: "Курск"})-[│                                                             │
│                        │              │:transit {name: "train"}]->(:City {name: "Ростов-на-Дону"})-[│                                                             │
│                        │              │:transit {name: "train"}]->(:City {name: "Краснодар"})-[:tran│                                                             │
│                        │              │sit {name: "train"}]->(:City {name: "Туапсе"})               │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Крым"                  │"Севастополь" │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["БИБЛИОГЛОБУС", "АНЕКСТУР", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Севастополь"})                                        │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Крым"                  │"Симферополь" │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["БИБЛИОГЛОБУС", "АНЕКСТУР", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Симферополь"})                                        │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Крым"                  │"Форос"       │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["БИБЛИОГЛОБУС", "АНЕКСТУР", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Севастополь"})-[:transit {name: "avto"}]->(:City {name│                                                             │
│                        │              │: "Форос"})                                                  │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Крым"                  │"Ялта"        │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["БИБЛИОГЛОБУС", "АНЕКСТУР", "CORAL TRAVEL", "INTOURIST"]    │
│                        │              │name: "Севастополь"})-[:transit {name: "avto"}]->(:City {name│                                                             │
│                        │              │: "Ялта"})                                                   │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Курорты Азовского моря"│"Ейск"        │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["CORAL TRAVEL", "ТЕЗТУР", "АЛЕАН", "БИБЛИОГЛОБУС", "АНЕКСТУР│
│                        │              │name: "Тула"})-[:transit {name: "train"}]->(:City {name: "Вор│"]                                                           │
│                        │              │онеж"})-[:transit {name: "train"}]->(:City {name: "Курск"})-[│                                                             │
│                        │              │:transit {name: "train"}]->(:City {name: "Ростов-на-Дону"})-[│                                                             │
│                        │              │:transit {name: "train"}]->(:City {name: "Краснодар"})-[:tran│                                                             │
│                        │              │sit {name: "train"}]->(:City {name: "Ейск"})                 │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Курорты Азовского моря"│"Мариуполь"   │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["CORAL TRAVEL", "ТЕЗТУР", "АЛЕАН", "БИБЛИОГЛОБУС", "АНЕКСТУР│
│                        │              │name: "Таганрог"})-[:transit {name: "avto"}]->(:City {name: "│"]                                                           │
│                        │              │Мариуполь"})                                                 │                                                             │
├────────────────────────┼──────────────┼─────────────────────────────────────────────────────────────┼─────────────────────────────────────────────────────────────┤
│"Курорты Азовского моря"│"Таганрог"    │(:City {name: "Москва"})-[:transit {name: "train"}]->(:City {│["CORAL TRAVEL", "ТЕЗТУР", "АЛЕАН", "БИБЛИОГЛОБУС", "АНЕКСТУР│
│                        │              │name: "Таганрог"})                                           │"]                                                           │
└────────────────────────┴──────────────┴─────────────────────────────────────────────────────────────┴─────────────────────────────────────────────────────────────┘

```

Графическое представление плана запроса :<br/>
![Plan 1](/img/plan_1_1.jpg)
![Plan 1](/img/plan_1_2.jpg)
![Plan 1](/img/plan_1_3.jpg)
![Plan 1](/img/plan_1_4.jpg)

Добавить индексы для оптимизации запроса
```sql
create index on for (n:City) on (n.name);
create index dd for (m:transit) on (m.name)
create index dr for (m:Direction) on (m.name);
```

Графическое представление плана запроса с учетом индексов:<br/>
![Plan 2](/img/plan_2_1.jpg)
![Plan 2](/img/plan_2_2.jpg)
![Plan 2](/img/plan_2_3.jpg)
