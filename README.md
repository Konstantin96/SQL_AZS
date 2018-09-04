# SQL_AZS
04.09.2018

USE AZS
GO

create table info_Mark_fuel(
info_Mark_fuel_ID int NOT NULL identity(1,1) PRIMARY KEY,
Name_Mark_Fuel varchar (100)
)

create table Worker_Dolzhnosts(
Worker_Dolzhnosts_ID int NOT NULL identity(1,1) PRIMARY KEY,
Worker_Dolzhnost_Name varchar(200)
)

create table Workers(
Worker_ID int NOT NULL identity(1,1) PRIMARY KEY,
Worker_Name varchar (200),
Worker_Dolzhnost int REFERENCES Worker_Dolzhnosts(Worker_Dolzhnosts_ID),
Worker_BirthDay date,
Worker_Telephone char(11),
Worker_Dop_INFO varchar(300)
)
ALTER TABLE Workers ADD AZS_ID int REFERENCES AZS(AZS_ID)

create table AZS(
AZS_ID int NOT NULL identity(1,1) PRIMARY KEY,
AZS_Name varchar (250),
AZS_Address varchar (250)
)

create table Order_fuels(
Order_fuel_ID int NOT NULL identity(1,1) PRIMARY KEY,
Mark_fuel int REFERENCES info_Mark_fuel(info_Mark_fuel_ID),
AZS_ID int REFERENCES AZS(AZS_ID),
Workers_info int REFERENCES Workers(Worker_ID),
QuantitySale_Fuel float,
DateSale_Fuel datetime,
Price_Fuel float
)

create table CurrentsFUEL_AZS(
CurrentsFUEL_AZS_ID int NOT NULL identity(1,1) PRIMARY KEY,
AZS_ID int REFERENCES AZS(AZS_ID),
info_Mark_fuel_ID int REFERENCES info_Mark_fuel(info_Mark_fuel_ID),
amountfuel float
)

create table TotalFUELs_AZS(
TotalFUELs_AZS_ID int NOT NULL identity(1,1) PRIMARY KEY,
AZS_ID int REFERENCES AZS(AZS_ID),
info_Mark_fuel_ID int REFERENCES info_Mark_fuel(info_Mark_fuel_ID),
amountfuel float
)



insert into info_Mark_fuel (Name_Mark_Fuel) VALUES ('АИ-80')
insert into info_Mark_fuel (Name_Mark_Fuel) VALUES ('АИ-92')
insert into info_Mark_fuel (Name_Mark_Fuel) VALUES ('АИ-95')
insert into info_Mark_fuel (Name_Mark_Fuel) VALUES ('АИ-98')
Select * from info_Mark_fuel

insert into Worker_Dolzhnosts (Worker_Dolzhnost_Name) VALUES ('Директор')
insert into Worker_Dolzhnosts (Worker_Dolzhnost_Name) VALUES ('Секретарь')
insert into Worker_Dolzhnosts (Worker_Dolzhnost_Name) VALUES ('Офис-мэнэджер')
insert into Worker_Dolzhnosts (Worker_Dolzhnost_Name) VALUES ('Продажник')
insert into Worker_Dolzhnosts (Worker_Dolzhnost_Name) VALUES ('Бухгалтер')
Select * from Worker_Dolzhnosts

insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Константин Клюкин',1,'1996.01.20',87479191579,NULL)
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Галина Иванова',2,'1998.11.15',87021569482,'Работник месяца')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Сергей Бородин',4,'1990.02.01', 87715694518,'Стажер')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Татьяна Свирепина',4,'1997.03.10',87026511234,'Лучший продажник')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Иван Снегин',5,'2000.01.20',87476491678,'Душа компании')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Владимир Бобров',3,'1989.08.16',87476491678,'Зануда')

insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Константин Клюкин',1,'1996.01.20',87479191579,NULL)
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Галина Иванова',2,'1998.11.15',87021569482,'Работник месяца')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Сергей Бородин',4,'1990.02.01', 87715694518,'Стажер')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Татьяна Свирепина',4,'1997.03.10',87026511234,'Лучший продажник')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Иван Снегин',5,'2000.01.20',87476491678,'Душа компании')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Владимир Бобров',3,'1989.08.16',87476491678,'Зануда')
Select * from Workers

insert into AZS (AZS_Name,AZS_Address) VALUES ('Helios','Фурманова 215')
insert into AZS (AZS_Name,AZS_Address) VALUES ('KazMunai','Сейфулина 163')
Select * from AZS

insert into Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel)VALUES (1,1,3,20,'2018.09.01 15:45',120)
insert into Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel)VALUES (3,1,4,25,'2018.09.01 17:30',141)
Select * from Order_fuels

select * from AZS

select * from Workers

select * from CurrentsFUEL_AZS/**/

select * from info_Mark_fuel

select * from Order_fuels

select * from TotalFUELs_AZS/**/

select * from Worker_Dolzhnosts

INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,2,1000)



insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Шляпин Сергей',1,'1998.01.20',87479191579,NULL)
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Василий Иванов',2,'1998.11.15',87021569482,'Работник месяца')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Андрей Бородин',4,'1990.02.01', 87715694518,'Стажер')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Валерия Свирепина',4,'1997.03.10',87026511234,'Лучший продажник')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Богдан Снегин',5,'2000.01.20',87476491678,'Душа компании')
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('Альтаир Бобров',3,'1989.08.16',87476491678,'Зануда')

INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (1,1,3,100,'01.09.2018 12:00',156)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (2,1,3,200,'09.07.2018 13:00',123)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (3,1,3,120,'15.08.2018 15:00',546)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (4,1,3,60,'12.07.2018 16:00',345)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (1,2,4,80,'02.08.2018 20:00',235)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (2,2,4,90,'12.06.2018 23:00',453)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (3,2,4,70,'22.07.2018 09:00',132)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (4,2,4,100,'18.08.2018 08:00',137)

INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (1,2,10,52,'02.09.2018 15:00',150)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (2,2,10,85,'05.07.2018 14:00',125)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (3,2,10,34,'16.08.2018 12:00',250)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (4,2,10,37,'17.07.2018 09:00',210)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (1,1,11,37,'13.08.2018 23:00',238)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (2,1,11,28,'18.06.2018 21:00',253)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (3,1,11,12,'28.07.2018 01:00',132)
INSERT INTO Order_fuels(Mark_fuel,AZS_ID,Workers_info,QuantitySale_Fuel,DateSale_Fuel,Price_Fuel) VALUES (4,1,11,82,'12.08.2018 05:00',137)

INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,2,1000)
INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,1,1200)
INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,3,800)
INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,4,900)

INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,4,800)
INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,2,1500)
INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,1,2000)
INSERT INTO CurrentsFUEL_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,3,1100)

INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,2,1600)
INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,1,1500)
INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,3,1500)
INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (1,4,2000)

INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,2,2000)
INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,1,2200)
INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,3,1600)
INSERT INTO TotalFUELs_AZS(AZS_ID,info_Mark_fuel_ID,amountfuel) VALUES (2,4,1800)

/*1. Выбрать все продажи топлива за определенный период времени */
SELECT * FRom Order_fuels WHERE DateSale_Fuel BETWEEN '15.08.2018 00:00' AND '01.09.2018 23:59'

/*2. Выбрать сотрудников (продавцов) продавших больше определенного количества литров топлива за определенный период времени */
SELECT * FROM Workers w JOIN Order_fuels o ON o.Workers_info=w.Worker_ID WHERE o.QuantitySale_Fuel>80 AND o.DateSale_Fuel BETWEEN '15.08.2018 00:00' AND '01.09.2018 23:59'

SELECT W.Worker_Name,W.AZS_ID,W.Worker_Dolzhnost,SUM(o.QuantitySale_Fuel) AS SUM
FROM Workers W 
JOIN Order_fuels o on o.Workers_info=w.Worker_ID
where o.DateSale_Fuel BETWEEN '15.08.2018 00:00' AND '01.09.2018 23:59' 
group by w.Worker_ID,w.Worker_Name,w.AZS_ID,w.Worker_Dolzhnost
having SUM(o.QuantitySale_Fuel)>20

/*3.  Выбрать все АЗС с общей емкостью топлива больше определенного значения и выбрать на 
       них все продажи определенной марки за определенный период времени.
	   Отсортировать по убыванию продаж */
SELECT a.AZS_ID,a.AZS_Name,o.Mark_fuel,o.DateSale_Fuel, o.QuantitySale_Fuel FROM AZS a 
JOIN Order_fuels o on o.AZS_ID=a.AZS_ID
JOIN TotalFUELs_AZS t on t.AZS_ID=a.AZS_ID
WHERE o.DateSale_Fuel BETWEEN '15.08.2017 00:00' AND '01.09.2019 23:59' AND o.Mark_fuel=2 AND t.TotalFUELs_AZS_ID>=5
GROUP BY a.AZS_ID,a.AZS_Name,o.Mark_fuel,o.DateSale_Fuel, o.QuantitySale_Fuel
ORDER BY o.QuantitySale_Fuel DESC

/*4. Выбрать все цены на топливо по всем АЗС в базе и отсортировать по возрастанию и по маркам топлива.*/
SELECT a.AZS_Name,o.Price_Fuel,o.Mark_fuel 
FROM Order_fuels o,AZS a
GROUP BY a.AZS_Name,o.Price_Fuel,o.Mark_fuel 
ORDER BY o.Price_Fuel ,o.Mark_fuel

--5
SELECT a.AZS_Name,COUNT(o.Order_fuel_ID) AS 'quan zakazov'FROM AZS a
 JOIN Order_fuels o on o.AZS_ID=a.AZS_ID 
GROUP BY a.AZS_Name

--6
SELECT a.AZS_Name,SUM(ta.amountfuel) FROM AZS a
Join TotalFUELs_AZS ta on ta.AZS_ID=a.AZS_ID
GROUP BY a.AZS_Name

--7
select SUM(cf.amountfuel),cf.AZS_ID from CurrentsFUEL_AZS cf
join Order_fuels o on o.AZS_ID=cf.AZS_ID
where o.Price_Fuel*o.QuantitySale_Fuel=(select max(o.Price_Fuel*o.QuantitySale_Fuel)from Order_fuels o)
group by cf.amountfuel,cf.AZS_ID

--8
select * from AZS a 
where a.AZS_ID not in (select o.AZS_ID from Order_fuels o where o.DateSale_Fuel BETWEEN '2018-09-01 15:44' AND '2018-09-01 15:46')
select * from Order_fuels

--9
insert into Workers (Worker_Name,Worker_Dolzhnost,Worker_BirthDay,Worker_Telephone,Worker_Dop_INFO) VALUES ('GSgs dhdrgd',5,'2000.02.20',87476387275,'')
select * from Workers

--10
select * from Workers w
right join AZS a on a.AZS_ID=w.AZS_ID
where a.AZS_ID=w.AZS_ID
