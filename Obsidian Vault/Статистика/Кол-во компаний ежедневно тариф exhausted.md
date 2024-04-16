#SQL Общее количество число
```
select count(*)

from company_tarifs ct

where ct.tarif_id = '22bc5514-4704-44be-b61f-b18df1388964' and

ct.date_add >='startDate' and ct.date_add <='endDate'
```

#SQL Для графиков по дням
```
select DATE_TRUNC('day', ct.date_add) AS date, count(*)

from company_tarifs ct

where ct.tarif_id = '22bc5514-4704-44be-b61f-b18df1388964' and

ct.date_add >='startDate' and ct.date_add <='endDate'

GROUP BY

DATE_TRUNC('day', ct.date_add)

ORDER BY

date;
```

#SQL Для графиков по месяцам
```
select DATE_TRUNC('month', ct.date_add) AS date, count(*)

from company_tarifs ct

where ct.tarif_id = '22bc5514-4704-44be-b61f-b18df1388964' and

ct.date_add >='startDate' and ct.date_add <='endDate'

GROUP BY

DATE_TRUNC('month', ct.date_add)

ORDER BY

date;
```