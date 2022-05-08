# pg-sql

SELECT task_id, tasks.name,case when s <=20 then 'Hard'
when s <= 60  and s >20 then 'Medium'  
       else 'Easy' end as sex
 from (
SELECT  task_id,avg(score) as s from reports group by task_id  ) avgscore , tasks where tasks.id= avgscore.task_id order by tasks.id
