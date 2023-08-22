Partie 1:
____________________________________________________________
Requête 1:
-- Afficher les clients dont leurs noms contient la lettre a
select * from demo_customers where regexp_like(cust_first_name,'a');

Requête 2:
-- Afficher les clients dont leurs noms commencent par la lettre j
select * from demo_customers where regexp_like(cust_first_name,'^J');

Requête 3:
-- Afficher les clients dont leurs noms se terminent par la lettre j
select * from demo_customers where regexp_like(cust_first_name,'J$');

Requête 4:
-- Afficher les clients dont leurs noms commençant par a ou e que ce soit minuscule ou majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[ae]','i');

Requête 5:
-- Afficher les clients dont leurs noms commençant par a ou e que ce soit minuscule ou majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[ae]','i');

Requête 6:
-- Afficher les clients dont leurs noms commençant par a ou e que ce soit minuscule ou majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[ae]','i');

Requête 7:
-- Afficher les clients dont leurs noms commençant par e et se terminent par d 
select * from demo_customers where regexp_like(cust_first_name,'^e.*d$','i');

Requête 8:
-- Afficher les clients dont leurs noms continent la lettre l 2 fois 
select * from demo_customers where regexp_like(cust_first_name,'l{2}','i');

Requête 8:
-- Afficher les clients dont leurs noms continent la lettre l au moins 2 fois
select * from demo_customers where regexp_like(cust_first_name,'l{2,3}','i');

Requête 9:
-- Afficher les clients dont leurs noms continent la lettre l au moins une fois et 3 fois au plus
select * from demo_customers where regexp_like(cust_first_name,'l{2,3}','i');

Requête 10:
-- Afficher les clients dont leurs noms commençant par une lettre majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[A-Z]','i');

Requête 11:
-- Afficher les clients dont leurs noms continent John ou Jon.
select * from demo_customers where regexp_like(cust_first_name,'Joh?n','i');

 
___________________________________
Partie 2:

Requête 1:
Remplacer le premier  mot par April:
 
SELECT REGEXP_REPLACE ('Mars is a month', '^(\S*)', 'April') FROM dual;

Requête 2:
Remplacer les chiffres par la lettre Z:

select  regexp_replace('ab5hdh7uru9dhh1','[[:digit:]]','Z') from dual;

Requête 3:
Remplacer plus de deux espaces par un seul espace:

select  regexp_replace('hello   man   how are you','( ){2,}',' ') from dual;

______________________________________________________________________
Partie 3:

Requête 1:

Combien de fois s'occurs la lettre a dans la phrase:
select regexp_count('my name is imran','a') from dual;

Requête 2:

Combien de chiffres existe dans la phrase:
select regexp_count('my birthdate is 10-10-2006','[[:digit:]]') from dual;

Requête 3:

Combien de lettres existe dans la phrase:
select regexp_count('my birthdate is 10-10-2006','[[:alpha:]]') from dual;

_______________________
Partie 4:
Requête 1:
recupere la position de laposition de la premiere lettre majuscule
select regexp_instr('my Name is Omar','[[:upper:]]') from dual;
Requête 2:
REcupere la premiere lettre a
select regexp_instr('hello my name is imran','a') from dual;




