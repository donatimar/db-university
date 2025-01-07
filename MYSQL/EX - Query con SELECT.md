```sql
-- Selezionare tutti gli studenti nati nel 1990 (160)
SELECT `id`, `name`, `surname`, `date_of_birth`
FROM `university`.`students`
WHERE YEAR(`date_of_birth`) = 1990;

-- Selezionare tutti i corsi che valgono più di 10 crediti (479)
SELECT `id`, `name`
FROM `university`.`courses`
WHERE `cfu` > 10;

-- Selezionare tutti gli studenti che hanno più di 30 anni
SELECT `id`, `name`, `surname`, `date_of_birth`
FROM `university`.`students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) > 30;

-- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
SELECT `id`, `year`, `period`, `name`
FROM `university`.`courses`
WHERE `year` = 1 AND `period` = "I semestre";

-- Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
SELECT `id`, `date`, `hour`
FROM `university`.`exams`
WHERE DATE(`date`) = "2020-06-20" AND TIME(`hour`) > "14:00:00";

-- Selezionare tutti i corsi di laurea magistrale (38)
SELECT `id`, `name`, `level`
FROM `university`.`degrees`
WHERE `level` = "magistrale";

-- Da quanti dipartimenti è composta l'università? (12)
SELECT COUNT(*)
FROM `university`.`departments`;

-- Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
SELECT `id`, `name`, `surname`, `phone`
FROM `university`.`teachers`
WHERE `phone` IS null;

-- Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)
INSERT INTO `university`.`students` (`degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`)
VALUES ("13", "Marco", "Donati", "1989-4-27", "DNTMRC89D27H294K", "2023-9-11", "69420", "donatimar@gmail.com");

-- Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126
UPDATE `university`.`teachers`
SET `office_number` = "126"
WHERE `name` = "Pietro";

-- Eliminare dalla tabella studenti il record creato precedentemente al punto 9
DELETE FROM `university`.`students`
WHERE `id` IN (5001);

```
