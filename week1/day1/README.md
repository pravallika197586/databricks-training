select * from Department;
select * from Employee;
select * from Project;
select name , salary from Employee;
select * from Employee where age>30;
select name from Department;

select e.*
from Employee e
join Department  d
on e.department_id = d.department_id
where d.name ='IT';

select * from
Employee where name like "j%";
select * from
Employee where name like "%e";
select * from
Employee where name like "%a%";
select * from
Employee where name like "_________";
select * from
Employee where name like "_o%";
select * from
Employee where hire_date like "2020%";
select * from Employee
where hire_date like"___-01%";
select * from 
Employee where hire_date like "2019%";
select * from Employee 
where hire_date>= "2021-03-__";
select *
from Employee
where hire_date >= CURDATE() - INTERVAL 2 YEAR;
select name,sum(salary) as totalsalary
from Employee group by name;
select avg(salary) as Average
from Employee;

select min(salary) as minimum from Employee;
select department_id,
count(emp_id) AS total_employees
from Employee
group by department_id;

select department_id, avg(salary) as average
from Employee group by department_id
