# formation-oracle-pl-sql


Programme 0: Hello wrold

BEGIN
dbms_output.put_line('Hello world..');
END;

Programme 1:

Dans cet exemple j'ai créé un simple programme qui affiche l'adresse d'une personne en utilisant la notion de record.
le record permet de regroupper plusieurs variables dans une seule structure:

DECLARE
type adress is record (city varchar2(20), country varchar2(20));
myadress adress;
BEGIN
myadress.city := 'berkane';
myadress.country := 'maroc';
dbms_output.put_line('Your adress is: '||myadress.city||' '|| myadress.country);
END;

-------------------------
Programme 2:

Ici, j'ai crée les trois types de boucle sous oracle simple et qui affiche les chiffre allons de 1 à 10.

DECLARE
a number:=1;
BEGIN
loop
a:=a+1;
dbms_output.put_line(a);
exit when a=10;
end loop;
END;

DECLARE
BEGIN
for i in 1..10 loop
dbms_output.put_line(i);
end loop;
END;


DECLARE
i number:=0;
BEGIN
while i<10 loop
i:=i+1;
dbms_output.put_line(i);
end loop;
END;


DECLARE
BEGIN
for i in reverse 1..10 loop
dbms_output.put_line(i);
end loop;
END;


------------------------
Programme 3:

là, j'ai créé un simple programme qui rempli un enregistrement par le nom d'utilisateur et la date de creation à partir
de la table demo_users, puis affiche le nom d'utilisateur.

DECLARE
type enr is record(username varchar2(250), created date);
myrow enr;
BEGIN
select user_name,created_on into myrow.username,myrow.created
from demo_users
where user_id=2;
dbms_output.put_line(myrow.username);
END;

---------------------------
Programme 4:

Dans cet example j'ai créé un curseur qui lit la liste des utilisateurs un par un
 et affiche leur nom d'utilisateur en majuscule.

Un curseur est une zonne d'execution privé utilisé par oracle pour ..

DECLARE
cursor c is select * from demo_users;
line c%rowtype;
BEGIN
open c;
loop
fetch c into line;
dbms_output.put_line(UPPER(line.user_name));
exit when c%notfound;
end loop;
close c;
END;

----------------------------
Programme 5:

Dans cet exemple j'ai utilisé la notion case dans un simple programme qui, selon la valeur existe dans 
une variable nommé a, affiche true si sa valeur vaux 1,false si sa valeur vaux 0 ou undefined sinon;

DECLARE
a NUMBER;
BEGIN
a:=0;
case a
when 0 then dbms_output.put_line('false');
when 1 then dbms_output.put_line('true');
else dbms_output.put_line('undefined');
end case;
END;

---------------------------
Programme 6:

Dans cet exemple j'ai créé une procédure stocké qui affiche la somme de deux nombres données en paramétres.


a- Déclaration:

CREATE OR REPLACE PROCEDURE p(a in number,b in number)
AS
BEGIN
dbms_output.put_line('la somme est: '||(a+b));
END

b- Exécution:

DECLARE 
b number;
BEGIN
p(2,3);
END;

-----------------------
Programme 7:

Dans ce programme j'ai crée une fonction qui retourne le double d'un nombre donée en paramètre.

a- Déclaration:

CREATE OR REPLACE function f(a in number) RETURN NUMBER
AS
BEGIN
RETURN a*2;
END


b- Exécution:

DECLARE 
b number;
BEGIN
b:=f(2);
dbms_output.put_line(b);
END;

------------------------
Programme 8:

Dans ce programme j'ai créé une exception de type utilisateur qui se déclanche si une variable a vaux 0
et affiche un message à l'utilisateur.

DECLARE
myexception exception;
a number:=0;
BEGIN
if(a=0) then raise myexception;
end if;
EXCEPTION
when myexception then dbms_output.put_line('Hello, I am an exception');
END;



------------------------
Programme 9:

Dans cet exemple j'ai crée un trigger qui se déclenche avant l modification d'une table produits et 
affiche la nouvelle et l'ancienne valeur de champ titre:

create or replace trigger t1
before update on produits
for each row
begin
dbms_output.put_line('nouvelle valeur: '||:new.title|| 'ancien valeur: '|| :old.title);
end;


----------------------

Programme 10:

Dans cet exemple j'ai créé un package qui regroupe deux procédures p1 et p2:

a- Création

create or replace package  pkg as
procedure p1(a in number);
procedure p2(a in number);
end pkg;

create or replace package body pkg as
procedure p1(a in number) is
begin 
dbms_output.put_line(a*2);
end;
procedure p2(a in number) is
begin 
dbms_output.put_line(a*3);
end;
end pkg;

b- Utilisation:

BEGIN
pkg.p1(2);
pkg.p2(4);
END

