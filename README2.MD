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
WHERE timestampdiff(YEARS, `date_of_birth`, CURDATE()) > 30;

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

/_Quanti sono gli insegnanti che non hanno un numero di telefono? (50)_/
SELECT \*
FROM `teachers`
WHERE `phone` IS NULL

**GROUP BY**
/_Contare quanti iscritti ci sono stati ogni anno_/
SELECT count(\*) AS `subscriber_count`, year(`enrolment_date`) AS `year`
FROM `students`
GROUP BY `year`

/_Contare gli insegnanti che hanno l'ufficio nello stesso edificio_/
SELECT count(\*) AS `number_of_teachers`, `office_address`
FROM `teachers`
GROUP BY `office_address`

/_Calcolare la media dei voti di ogni appello d'esame_/
SELECT avg(`vote`) AS `average_grades`, `exam_id`
FROM `exam_student`
GROUP BY `exam_id`

/_Contare quanti corsi di laurea ci sono per ogni dipartimento_/
SELECT count(\*) AS `num_courses`, `department_id`
FROM `degrees`
GROUP BY `department_id`

**JOIN**
/_Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia_/
SELECT students.id, students.name, students.surname
FROM `students`
JOIN degrees ON students.degree_id = degrees.id
WHERE degrees.name = "Corso di Laurea in Economia";
