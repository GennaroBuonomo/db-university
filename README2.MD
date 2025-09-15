/_Selezionare tutti gli studenti nati nel 1990 (160)_/
SELECT \*
FROM `students`
WHERE `date_of_birth` LIKE '1990%';

/_Selezionare tutti i corsi che valgono più di 10 crediti (479)_/
SELECT \*
FROM `courses`
WHERE `cfu` > 10;

/_Selezionare tutti gli studenti che hanno più di 30 anni_/
SELECT \*
FROM `students`
WHERE `date_of_birth` < CURDATE() - INTERVAL 30 YEAR;

/_Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)_/
SELECT \*
FROM `courses`
WHERE `year` = 1 AND `period` = 'I semestre';

/_Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)_/
SELECT \*
FROM `exams`
WHERE `date` = '2020-06-20' AND `hour` > '14:00:00';

/_Selezionare tutti i corsi di laurea magistrale (38)_/
SELECT \*
FROM `degrees`
WHERE `level` = 'magistrale';

/_Da quanti dipartimenti è composta l'università? (12)_/
SELECT \*
FROM `departments`
