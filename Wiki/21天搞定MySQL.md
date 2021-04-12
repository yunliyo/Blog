# 21天搞定MySQL

开始前的准备事项，第0天 ，  

开始之前的，前置准备事项：  
1、在自己电脑上安装一个mysql数据库  
2、找一个mysql客户端链接工具：推荐workbench 或者Navicat  

自行上网搜索下载。  

/  

第1天作业 ，  

1）创建数据库 yunlihub  
2）查看数据库创建是否成功  


/  

第2天作业 ，  

在昨天创建的yunlihub数据库下，创建 表 yunlihub 和 表 yunli  

注：SQL的作业，前几天的 库、表，都是打基础；没有这些，后面的增删改查，你也没法玩 ；  


1）yunlihub表的字段、类型、属性：  
id  INT(10)  NOT NULL  UNIQUE  PRIMARY KEY  ,  
uname  VARCHAR(20)  NOT NULL ,  
sex  VARCHAR(4)  ,  
birth  YEAR,  
department  VARCHAR(20) ,  
address  VARCHAR(50) ,  
yunli VARCHAR(20)   

2）yunli表的字段、类型、属性：  
id  INT(10)  NOT NULL  UNIQUE  PRIMARY KEY  AUTO_INCREMENT ,  
stu_id  INT(10)  NOT NULL ,  
c_name  VARCHAR(20) ,  
yunlihub VARCHAR(50) ,  
grade  INT(10)  



前一天作业答案参考 ，  

1）创建数据库 yunlihub  
create DATABASE yunlihub;  

2）查看数据库创建是否成功  
show DATABASES;  



/  

第3天作业 ，  

根据已有的表yunlihub 和 yunli 创建新表（复制表）  

1）复制yunlihub表结构，创建新表yunlihub2  
注：可以有两种方式  

2）复制yunli表结构和数据，创建新表yunli2  

3）复制yunli表结构的 id,stu_id,yunlihub三个字段，创建新表yunli3  



前一天作业答案参考 ，  

创建yunlihub和yunli表  

CREATE  TABLE  yunlihub (  
id  INT(10)  NOT NULL  UNIQUE  PRIMARY KEY  ,  
uname  VARCHAR(20)  NOT NULL ,  
sex  VARCHAR(4)  ,  
birth  YEAR,  
department  VARCHAR(20) ,  
address  VARCHAR(50) ,  
yunli VARCHAR(20)   
);  


CREATE  TABLE  yunli (  
id  INT(10)  NOT NULL  UNIQUE  PRIMARY KEY  AUTO_INCREMENT ,  
stu_id  INT(10)  NOT NULL ,  
c_name  VARCHAR(20) ,  
yunlihub VARCHAR(50) ,  
grade  INT(10)  
);  



/  

第4天作业 ，  

1）删除表 yunlihub2  
2）同时删除表yunli2和yunli3  
3）查看还有哪些表  



前一天作业答案参考 ，  

1）复制yunlihub表结构，创建新表yunlihub2  
注：可以有两种方式  
create table yunlihub2 like yunlihub ;  
或  
create table yunli2 as select * from yunli where 2=1;  

2）复制yunli表结构和数据，创建新表yunli3  
create table yunli3 as select * from yunli  

3）复制yunli表结构的 id,stu_id,yunlihub三个字段，创建新表yunli3  
create table yunli3 as select id,stu_id,yunlihub from yunli where 1<>1;  


/  

第5天作业 ，  

1）修改yunlihub表，添加一个字段yunlihub6 （字符类型VARCHAR，长度100，不允许为空）  

2）查看字段yunlihub6  ，是否添加成功  

3）修改yunlihub表，删除字段yunlihub6  

4）确认字段yunlihub6  ，是否删除成功  



前一天作业答案参考 ，  

1）删除表 yunlihub2  
drop table yunlihub2 ;  

2）同时删除表yunli2和yunli3  
drop table yunli2,yunli3 ;  

3）查看还有哪些表  
show tables;  


/  

第6天作业 ，  

插入 insert：  

1）向表yunlihub插入数据  
id = 1 ,uname = yunli ,yunli = 2020  
id = 2 ,uname = yunli2 ,yunli = 2020  

id=11,uname = yunli3,sex=1  
id=12,uname = yunli4,sex=2  
id=13,uname = yunli5,sex=1  
id=14,uname = yunli6,sex=2  


2）向表yunli插入数据  
id=4,stu_id=11,c_name=yunli,grade=90  
id=5,stu_id=12,c_name=lin,grade=100  
id=6,stu_id=33,c_name=yunlihub,grade=20  




前一天作业答案参考 ，  

1）修改yunlihub表，添加一个字段yunlihub6 （字符类型VARCHAR，长度100，不允许为空）  
ALTER table yunlihub add column yunlihub6 VARCHAR(100) NOT NULL;  

2）查看字段yunlihub6  ，是否添加成功  
desc yunlihub  

3）修改yunlihub表，删除字段yunlihub6  
ALTER table yunlihub drop yunlihub8  

4）确认字段yunlihub6  ，是否删除成功  
desc yunlihub  


/

第7天作业 ，  

1）查询yunlihub表 id = 1 的内容  
2）查询yunli 表 grade=100 的内容  



前一天作业答案参考 ，  

插入 insert：  

1）向表yunlihub插入数据  
id = 1 ,uname = yunli ,yunli = 2020  
id = 2 ,uname = yunli2 ,yunli = 2020  

id=11,uname = yunli3,sex=1  
id=12,uname = yunli4,sex=2  
id=13,uname = yunli5,sex=1  
id=14,uname = yunli6,sex=2  


2）向表yunli插入数据  
id=4,stu_id=11,c_name=yunli,grade=90  
id=5,stu_id=12,c_name=lin,grade=100  
id=6,stu_id=33,c_name=yunlihub,grade=20  

参考语句：  

insert into yunlihub(id,uname,yunli) values(1,"yunli",2020);  
insert into yunlihub(id,uname,yunli) values(2,"yunli2",2020);  

insert into yunlihub(id,uname,sex) values(11,"yunli3",1),(12,"yunli4",2),(13,"yunli5",1),(14,"yunli6",2);  

insert into yunli(id,stu_id,c_name,grade) values(4,11,"yunli",90),(5,12,"lin",100),(6,33,"yunlihub",20);  


/  


第8天作业 ，  

继续 select  

1）查找yunli表，名称（c_name）包含 “i” 的数据  
2）查找yunlihub表，id 包含 “1” 的数据  
3）查找yunlihub表，id 包含 “1” 的数据，按id降序  
4）查找yunlihub表，id 包含 “1” 的数据 ，取id最大的三个  


前一天作业答案参考 ，  

1）查询yunlihub表 id = 1的内容  
select * from yunlihub where id = 1;  

2）查询yunli 表 grade=100 的内容  
select * from yunli where grade =100;  




/  

第9天作业 ，  

1）找出yunli表中，分数最高的同学和分数  

2）找出yunli表中，分数最低的同学和分数  


前一天作业答案参考 ，  


1）查找yunli表，名称（c_name）包含 “i” 的数据  
select * from yunli where c_name like '%i%' ;  

2）查找yunlihub表，id 包含 “1” 的数据  
select * from yunlihub where id like '%1%';  

3）查找yunlihub表，id 包含 “1” 的数据，按id降序  
select * from yunlihub where id like '%1%' order by id desc ;  

4）查找yunlihub表，id 包含 “1” 的数据 ，取id最大的三个  
select * from yunlihub where id like '%1%' order by id desc limit 3 ;  


/  

第10天作业 ，  

-- 1)  找出yunlihub表，sex为空的的数据；  

-- 2）更新yunlihub表，把sex为空的，设置为0（性别未知）  

-- 3）找出yunli表，grade小于60分的同学  

-- 4）更新yunli表，把grade小于60分的同学，一律改为59分  



前一天作业答案参考 ，  

-- 1）找出yunli表中，分数最高的同学和分数；  
SELECT c_name,grade as "maxvalue" from yunli WHERE grade in (select MAX(grade)  from yunli ) ;  

-- 2）找出yunli表中，分数最低的同学和分数；
SELECT c_name,grade as "minvalue" from yunli WHERE grade in (SELECT MIN(grade)  from yunli );  



/  

第11天作业 ，  

-- 1）查找yunlihub表，按id降序  

-- 2）查找yunli表，按grade升序  


前一天作业答案参考 ，  


-- 1) 找出yunlihub表，sex为空的的数据；  
select * from yunlihub where sex is null ;  

-- 2）更新yunlihub表，sex为空的，设置为0（性别未知）  
update yunlihub set sex = 0 where sex is null ;  


-- 3）找出yunli表，grade小于60分的同学  
select * from yunli where grade < 60 ;  

-- 4）更新yunli表，把grade小于60分的同学，一律改为59分  
update yunli set grade = 59 where grade < 60 ;  



/  

第12天作业 ，  

1）查询yunlihub表，有多少条数据  

2）查询yunlihub表，有几种性别类型（sex字段，去重）  


前一天作业答案参考 ，  

-- 1）查找yunlihub表，按id降序  
select * from yunlihub order by id desc;  

-- 2）查找yunli表，按grade升序  
select * from yunli order by grade;  


/  



第13天作业 ，  

1）查找yunli表，学生成绩(grade) 总分  

2）查找yunli表，学生成绩(grade) 平均分  


前一天作业答案参考 ，  

1）查询yunlihub表，有多少行数据  
select COUNT(sex) from yunlihub;  

2）查询yunlihub表，有性别类型数量（sex字段，去重）  
select COUNT(DISTINCT sex) from yunlihub;  



/  


第14天作业 ，  

1）查找yunli表，成绩在80 - 100区间的学生 ；  
2）查找yunlihub表，id 为 2，11，12 的数据 ；  


前一天作业答案参考 ，  

1）查找yunli表，学生成绩(grade) 总分  
select sum(grade) as sumgrade from yunli ;  

2）查找yunli表，学生成绩(grade) 平均分  
select avg(grade) as avggrade from yunli ;  


/  



第15天作业 ，  

1）删除 yunlihub表，id大于12的数据 ；  
2）删除yunli表，分数grade不及格（小于60分）的数据 ；  


前一天作业答案参考 ，  

-- 1）查找yunli表，成绩在80 - 100区间的学生 ；  
select * from yunli where grade between 80 and 100;  
-- 2）查找yunlihub表，id 为 2，11，12 的数据 ；  
select * from yunlihub where id in (2,11,12) ;  



/  

第16天作业 ，  

1）造数据 ，把yunlihub表的所有数据，插入到 yunli表  
字段取值规则  
id 取id  
stu_id 取id  
c_name 取 uname  
yunlihub 和 grade字段，给默认值 60  


前一天作业答案参考 ，  

1）删除 yunlihub表，id大于12的数据 ；  
delete from yunlihub where id > 12;  

2）删除yunli表，分数grade不及格（小于60分）的数据 ；  
delete from yunli where grade < 60 ;  


/  


第17天作业 ，  


-- 1）把yunli表，改名为 yunli6  

-- 2）检查是否修改成功  

-- 3）修改表yunli，把字段yunlihub ，改为yunlihub6（字符类型varchar，长度160 ）  

-- 4）检查是否修改成功  



前一天作业答案参考 ，  

造数据 ，把yunlihub表的所有数据，插入到 yunli表  
字段关系  
id 取id  
stu_id 取id  
c_name 取 uname  
yunlihub 和 grade字段，给默认值 60  

insert into yunli(id,stu_id,c_name,yunlihub,grade) select id,id,uname,60,60 from yunlihub ;  




/  

第18天作业 ，  


1）创建数据库 yunlihubdb6  

2）检查数据库是否创建成功 ；  

3）进入yunlihubdb6 库  

4）在数据库 yunlihubdb6 ，创建yunli表，直接拷贝 yunlihub库yunli6表的数据和结构 ；  

5）检查表是否创建成功 ；  



前一天作业答案参考 ，  

-- 1）把yunli表，改名为 yunli6  
-- ALTER TABLE 旧表名 RENAME TO 新表名 ;  
ALTER TABLE yunli RENAME TO yunli681 ;  

-- 2）检查是否修改成功  
show tables;  

-- 3）修改表yunli，把字段yunlihub ，改为yunlihub6（字符类型varchar，长度160 ）  
alter table yunli CHANGE yunlihub yunlihub6 varchar(160);   

-- 4）检查是否修改成功  
desc yunlihub;  



/  

第19天作业 ，  

yunli表，分数grade  
1）排名前三的学生 和分数 ；  
2）排名3 - 6名的学生 和分数 ；  
3）排名6名以后的所有学生  和分数 ；  


前一天作业答案参考 ，  

1）创建数据库 yunlihubdb6  
create database yunlihubdb6 ;  

2）检查数据库是否创建成功 ；  
show databases ;  

3）进入yunlihubdb6 库  
use yunlihubdb6 ;  

4）在数据库 yunlihubdb6 ，创建yunli表，直接拷贝 yunlihub库yunli6表的数据和结构 ；  
create table yunlihubdb6.yunli as SELECT * from yunlihub.yunli6;  
或  
create table yunli as SELECT * from yunlihub.yunli6;  

5）检查表是否创建成功 ；  
show tables;  



/  

第20天作业 ，  

多表（左链接、右链接、内链接）  

表 yunli6 和 表yunlihub  



前一天作业答案参考 ，  

-- 1）排名前三的学生 和分数 ；   
SELECT c_name,grade FROM yunli ORDER BY grade DESC LIMIT 3;   

-- 2）排名3 - 6名的学生 和分数 ；   
SELECT c_name,grade FROM yunli ORDER BY grade DESC LIMIT 2,4;   

-- 3）排名6名以后的所有学生 和分数 ：  
SELECT c_name,grade FROM yunli ORDER BY grade DESC LIMIT 5,666;  

注：这题目的是limit的用法，很多同学写的太复杂 ；  

limit是mysql的语法  
select * from table limit m,n  
其中m是指记录开始的index，从0开始，表示第一条记录  
n是指从第m+1条开始，取n条。  
select * from tablename limit 2,4  
即取出第3条至第6条，4条记录  




/  

第21天作业（最后1天，结业） ，  

1）把表yunli6，改完yunli  
2）删除库 yunlihubdb6  
3）删除yunlihub表  
4）清空yunli表的数据  


End ，一切恢复如初，坐等SQL第2期 ；  


前一天作业答案参考 ，  

注：主要目的是熟悉这三种玩法，以及观察结果差异 ；  

#左连接   
SELECT * from yunli6 a LEFT JOIN yunlihub b on a.stu_id=b.id;   

#内连接   
SELECT * from yunli6 a INNER JOIN yunlihub b on a.stu_id=b.id;   

#右连接   
SELECT * from yunli6 a RIGHT JOIN yunlihub b on a.stu_id=b.id;  



/  

结业，最后一天作业答案参考  


1）把表yunli6，改名为yunli   
rename table yunli6 to yunli;   
或  
alter table yunli6 rename yunli;   

2）删除库 yunlihubdb6   
drop database yunlihubdb6;   

3）删除yunlihub表   
drop table yunlihub;   

4）清空yunli表的数据   
truncate table yunli;   
或  
delete from yunli;  

# End 
恭喜结业 ；  
循环3次21天打卡，总共63天  
（两个月掌握软测必备的SQL日常使用）  