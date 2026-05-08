select * from Department;

select * from Employee;

select * from Project;

select name , salary from Employee;

select * from Employee where age>30;

select name from Department;

select e.*
from Employee e
join Department d
on e.department_id = d.department_id
where d.name = 'IT';

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
where hire_date like "____-01-%";

select * from
Employee where hire_date like "2019%";

select * from Employee 
where hire_date >= "2021-03-__";

select *
from Employee
where hire_date >= CURDATE() - INTERVAL 2 YEAR;

select name,sum(salary) as totalsalary
from Employee group by name;

select avg(salary) as Average
from Employee;

select min(salary) as minimum from Employee;

select department_id, count(emp_id) as total_employees
from Employee
group by department_id;

select department_id,avg(salary) as average
from Employee group by department_id;
select department_id,sum(salary) as total 
from Employee group by department_id;

select department_id,round(avg(age)) as totalage
from Employee group by department_id;

SELECT YEAR(hire_date) AS hire_year,
       COUNT(*) AS total_employees
FROM Employee
GROUP BY YEAR(hire_date);

select department_id,max(salary) as max from Employee
group by department_id;

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

select emp_id,salary from Employee
order by salary ASC;

select emp_id,age from Employee
order by age DESC;

select emp_id,hire_date from Employee
order by hire_date ASC;

select emp_id,department_id,salary from Employee
order by department_id,salary;

select department_id,sum(salary) as total,emp_id from Employee
group by department_id,emp_id
order by sum(salary);

select e.name,d.name as department_name
from Employee e
join Department d
on e.department_id = d.department_id;

select d.name,p.name as project_name from Department d 
join Project p
on d.department_id = p.department_id;

select e.name as employee_name,p.name as project_name
from Employee e
join Project p
on e.department_id = p.department_id;

select e.emp_id ,e.name, d.department_id,d.name from Employee e
join Department d
on e.department_id = d.department_id;

select e.name
from Employee e
left join Project p
on e.department_id = p.department_id
where p.Project_id is null;

select e.name,d.name,count(p.project_id) as totalprojects 
from Employee e
join Department d
on e.department_id = e.department_id
left join Project p
on e.department_id = p.department_id
group by e.emp_id, e.name, d.name;

select d.name
from Department d
left join Employee e
on d.department_id = e.department_id
where e.emp_id is null;


select name
from Employee
where department_id = (
    select department_id
    from Employee
    where name = 'John Doe'
);

select d.name,avg(e.salary) as average_salary
from Employee e
join Department d
on e.department_id = d.department_id
group by d.name
order by average_salary desc
limit 1;
