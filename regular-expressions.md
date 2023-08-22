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


