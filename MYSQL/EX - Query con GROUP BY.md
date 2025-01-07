```sql
-- Contare quanti iscritti ci sono stati ogni anno
SELECT YEAR(`enrolment_date`) AS `year`, COUNT(`id`) AS `enrolled_students`
FROM `university`.`students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY YEAR(`enrolment_date`);

-- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT `office_address` AS `building`, COUNT(*) AS `total_teachers`
FROM `university`.`teachers`
GROUP BY `office_address`
ORDER BY `total_teachers` DESC;

-- Calcolare la media dei voti di ogni appello d'esame
SELECT `exam_id`, AVG(`vote`)
FROM `university`.`exam_student`
GROUP BY `exam_id`;

-- Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT `department_id`, COUNT(*) AS `available_degrees`
FROM `university`.`degrees`
GROUP BY `department_id`
ORDER BY `available_degrees` DESC;
```
