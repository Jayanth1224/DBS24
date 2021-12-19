# DBS24
db code


create database DBS;
use DBS;
create table Customer_table(customer_id int primary key, customer_name varchar(255),user_id varchar(255),password varchar(255));
create table Stocks(stock_id int primary key, stock_name varchar(255), current_price int(255));
show tables;

Create Table Stock_book_order
(
Order_id Int Primary Key,
order_type varchar(255),PRIMARY
price int, quantity int,
order_date date,
stock_id int,
customer_id int,
Foreign Key(stock_id) REFERENCES Stocks(stock_id),
Foreign Key(customer_id) REFERENCES Customer_table(customer_id)
);
create table Admin
(
Order_id int,
foreign key(Order_id) references Stock_book_order(Order_id),
stock_name varchar(255),
order_status varchar(255) default 'Placed'
);
show tables;
insert into customer_table(customer_id, customer_name,user_id,password)
values (1,'DBS','Jayanth','dbs@123'),(2,'DBS','swapnil','dbs@403'),(3,'DBS','sravan','dbs@23');
insert into Stocks(stock_id, stock_name,current_price)
values (1123,"paytm",1120),(1124,"zomato",1120),(1125,"DBS",1120);
