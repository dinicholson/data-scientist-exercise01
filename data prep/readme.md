###SQL query for general use
```sql
SELECT r.id, r.age, r.workclass_id, r.education_level_id, r.education_num, r.marital_status_id, r.occupation_id, r.race_id, r.sex_id, r.capital_gain, r.capital_loss,
r.hours_week, r.country_id, r.over_50k, w.name as workclass,  e.name as education_level , m.name as marital_status, o.name as occupation, 
ra.name as race, s.name as sex, c.name as country
FROM records r
LEFT JOIN workclasses w
on r.workclass_id = w.id
LEFT JOIN education_levels e
on r.education_level_id = e.id
LEFT JOIN marital_statuses m
on r.marital_status_id = m.id
LEFT JOIN occupations o
on r.occupation_id = o.id
LEFT JOIN races ra
on r.race_id = ra.id
LEFT JOIN sexes s
on r.sex_id = s.id
LEFT JOIN countries c
on r.country_id = c.id
```
