[Click-Here for Practice Site](https://www.sql-practice.com/)

	1. Show first name, last name, and gender of patients who's gender is 'M'
		SELECT first_name, last_name, gender From patients where gender='M'
	2. Show first name and last name of patients who does not have allergies (null)
		SELECT first_name,last_name From patients WHERE allergies IS NULL
	3. Show first name of patients that start with the letter 'C'
		SELECT first_name from patients WHERE first_name LIKE 'C%'
	4. Show first name and last name of patients that weight within the range of 100 to 120 (inclusive)
		SELECT first_name,last_name From patients WHERE weight between 100 and 120
	5. Update the patients table for the allergies column. If the patient's allergies is null then replace it with 'NKA'
		UPDATE patients set allergies= 'NKA' where allergies is NULL
	6. Show first name and last name concatinated into one column to show their full name.
		SELECT concat(first_name,'  ',last_name) AS full_name From patients
	7. Show first name, last name, and the full province name of each patient.
	Example: 'Ontario' instead of 'ON'
		SELECT first_name, last_name,province_name fROM patients as 'p' inner join provinces as 'q' 
		WHERE p.province_id = q.province_id
	8. Show how many patients have a birth_date with 2010 as the birth year.
		SELECT COUNT(*) FROM patients where birth_date LIKE '2010%'
	9. Show all columns for patients who have one of the following patient_ids:1,45,534,879,1000
		SELECT * FROM patients where patient_id IN(1,45,534,879,1000)
	10. Show the first_name, last_name, and height of the patient with the greatest height.
		SELECT first_name, last_name, height from patients where height = (SELECT MAX(height) from patients)
		OR  SELECT first_name, last_name, MAX(height) as height FROM patients;
	11. Show the total number of admissions.
        SELECT count(*) from admissions