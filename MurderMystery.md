*SQL MURDER MYSTERY*
A crime has taken place and the detective needs your help. The detective gave you the crime scene report, but you somehow lost it. You vaguely remember that the crime was a ​murder​ that occurred sometime on ​Jan.15, 2018​ and that it took place in ​SQL City​.

Start by retrieving the corresponding crime scene report from the police department’s database.

``SELECT * FROM crime_scene_report LIMIT 10 
 SELECT * FROM crime_scene_report WHERE type = ‘murder’ AND city = ‘SQL City’ AND date = ‘20180115’
 WITH witnesses as (SELECT * FROM interview JOIN person p ON p.id = person_id
 WHERE (name LIKE’%Annabel%’ AND address_street_name = ‘Franklin Ave’) OR  (address_street_name = “Northwestern Dr”))``

Witness 1: I saw the murder happen, and I recognized the killer from my gym when I was working out last week on January the 9th.

Witness 2: I heard a gunshot and then saw a man run out. He had a “Get Fit Now Gym” bag.
The membership number on the bag started with “48Z”. Only gold members have those bags. The man got into a car with a plate that included “H42W”.

``SELECT * FROM get_fit_now_member m JOIN get_fit_now_check_in ON m.id = membership_id
 WHERE check_in_date = ‘20180109’ AND membership_status = ‘gold’ AND membership_id LIKE ’48Z%’
 WITH p AS (SELECT name, license_id FROM person WHERE id in (‘28819’, ‘67318’)) 
 SELECT  * FROM drivers_license d JOIN p on p.license_id = d.id WHERE id IN (select license_id FROM p)``

**BONUS**

``select * from interview where person_id = ‘insert murderer’s id here’``

Murderer's Testimony: I was hired by a woman with a lot of money. I don’t know her name but I know she’s around 5’5″ (65″) or 5’7″ (67″). She has red hair and she drives a Tesla Model S. I know that she attended the SQL Symphony Concert 3 times in December 2017. 

``SELECT id FROM drivers_license WHERE car_model = “Model S” AND gender = ‘female’
 SELECT * FROM person WHERE license_id IN (‘202298’, ‘291182’, ‘918773’)
 SELECT p.name, f.* FROM facebook_event_checkin f JOIN person p ON p.id = f.person_id
 WHERE f.person_id IN (‘78881’, ‘90700’, ‘99716’)

 ```INSERT INTO solution VALUES (1, 'Miranda Priestly');
        SELECT value FROM solution;```
