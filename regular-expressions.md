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
-- Afficher les clients dont leurs noms commençent par a ou e que ce soit minuscule ou majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[ae]','i');

Requête 5:
-- Afficher les clients dont leurs noms commençent par a ou e que ce soit minuscule ou majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[ae]','i');

Requête 6:
-- Afficher les clients dont leurs noms commençent par a ou e que ce soit minuscule ou majuscule
select * from demo_customers where regexp_like(cust_first_name,'^[ae]','i');

Requête 7:
-- Afficher les clients dont leurs noms commençent par e et se terminent par d 
select * from demo_customers where regexp_like(cust_first_name,'^e.*d$','i');
