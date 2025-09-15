/_Selezionare tutti gli studenti nati nel 1990 (160)_/
SELECT \*
FROM `students`
WHERE `date_of_birth` LIKE '1990%';

/_Selezionare tutti i corsi che valgono più di 10 crediti (479)_/
SELECT \*
FROM `courses`
WHERE `cfu` > 10;
