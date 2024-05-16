1. Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*), YEAR(`enrolment_date`) AS "anno_inizio"
FROM `students`
GROUP BY YEAR(`enrolment_date`);

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(*), `office_address` AS "indirizzo"
FROM `teachers`
GROUP BY `office_address`;

3. Calcolare la media dei voti di ogni appello d'esame
SELECT AVG(`exam_student`.`vote`) AS "media", `exams`.`date` AS "data"
FROM `exam_student`
JOIN `exams`
ON `exams`.`id` = `exam_student`.`exam_id`
GROUP BY `exams`.`date`;

4. Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(*) AS "numero_corsi", `departments`.`name` AS "dipartimenti"
FROM `degrees`
JOIN `departments`
ON `departments`.`id` = `degrees`.`department_id`
GROUP BY `degrees`.`department_id`;