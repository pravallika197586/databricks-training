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


select department_id,avg(salary) as average from Employee 
group by department_id
order by average DESC
limit 1;


select department_id,count(emp_id) as employee from Employee
group by department_id
having count(emp_id)>2;

select department_id,avg(salary) as averagesalary from Employee
group by department_id
having avg(salary)>55000;

select year(hire_date) as year ,count(emp_id) as employe from Employee
group by year(hire_date) 
having count(emp_id)>1;

select department_id,avg(salary) from Employee
group by department_id
having avg(salary)<100000;

select department_id,sum(salary) from Employee
group by department_id
having sum(salary)<75000;
