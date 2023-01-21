# NOTE: Estas son las respuestas a las 50 peticiones SQL y a las 2 especificas con JOIN

Respuestas a las peticiones SQL:
--------------------------------

1: SELECT nombre FROM usuarios;

2: SELECT max(saldo) FROM usuarios
   WHERE sexo = 'M';
   
3: SELECT nombre,telefono FROM usuarios
   WHERE marca IN ('NOKIA','BLACKBERRY','SONY');
   
4: SELECT COUNT(*) FROM usuarios
   WHERE saldo = 0 OR activo = 0;

5: SELECT usuario FROM usuarios
   WHERE nivel IN(1,2,3);
   
6: SELECT saldo FROM usuarios
   WHERE saldo <=300;
   
7: SELECT SUM(saldo) FROM usuarios
   WHERE compania = 'NEXTEL';
   
8: SELECT COUNT(usuario) FROM usuarios
   GROUP BY compania;

9: SELECT COUNT(usuario) FROM usuarios
   GROUP BY nivel;
 
10: SELECT usuario FROM usuarios
    WHERE nivel=2;
   
11: SELECT email FROM usuarios
    WHERE email LIKE '%gmail.com';

12: SELECT nombre,telefono FROM usuarios
    WHERE marca IN ('LG','SAMSUNG','MOTOROLA')
	
13: SELECT nombre,telefono FROM usuarios
	WHERE marca NOT IN('LG', 'SAMSUNG');
	
14: SELECT usuario,telefono FROM usuarios
	WHERE compania = 'IUSACELL';
	
15: SELECT usuario,telefono FROM usuarios
	WHERE marca != 'TELCEL'
	
16: SELECT AVG(saldo) FROM usuarios
	WHERE marca='NOKIA';
	
17: SELECT usuario,telefono FROM usuarios
	WHERE compania IN('IUSACELL','AXEL')
	
18: SELECT email FROM usuarios
	WHERE email NOT LIKE '%@yahoo.com';
	
19: SELECT usuario,telefono FROM usuarios
	WHERE compania NOT IN('TELCEL','IUSACELL');

20: SELECT usuario,telefono FROM usuarios
	WHERE compania = 'UNEFON';

21: SELECT DISTINCT marca FROM usuarios
	ORDER BY marca DESC;

22: SELECT  DISTINCT compania FROM usuarios
	ORDER BY RAND();

23: SELECT usuario FROM usuarios
	WHERE nivel IN(0,2);

24: SELECT AVG(saldo) FROM usuarios
	WHERE marca = 'LG';

25: SELECT usuario FROM usuarios
	WHERE nivel IN (1,3);
 
26: SELECT nombre,telefono FROM usuarios
	WHERE marca != 'BLACKBERRY';

27: SELECT usuario FROM usuarios
	WHERE nivel = 3;

28: SELECT usuario FROM usuarios
	WHERE nivel = 0;

29: SELECT usuario FROM usuarios
	WHERE nivel = 1;

30: SELECT sexo,COUNT(*) FROM usuarios
	GROUP BY sexo;

31: SELECT usuario,telefono FROM usuarios
	WHERE compania = 'AT&T';

32: SELECT DISTINCT compania FROM usuarios
	ORDER BY compania DESC;

33: SELECT usuario FROM usuarios
	WHERE activo = 0;

34: SELECT telefono FROM usuarios
	WHERE saldo = 0;

35: SELECT MIN(saldo) FROM usuarios
	WHERE sexo = 'H';

36: SELECT telefono FROM usuarios
	WHERE saldo >300;

37: SELECT marca, COUNT(*) FROM usuarios
	GROUP BY marca;

38: SELECT nombre,telefono FROM usuarios
	WHERE marca != 'LG';

39: SELECT DISTINCT compania FROM usuarios
	ORDER BY compania ASC;

40: SELECT SUM(saldo) FROM usuarios
	WHERE compania ='UNEFON';

41: SELECT email FROM usuarios
	WHERE email LIKE '%hotmail.com';

42: SELECT nombre FROM usuarios
	WHERE saldo=0 OR activo=0;

43: SELECT usuario,telefono FROM usuarios
	WHERE compania IN('IUSACELL','TELCEL');

44: SELECT DISTINCT marca FROM usuarios
	ORDER BY marca ASC;

45: SELECT DISTINCT marca FROM usuarios
	ORDER BY RAND();

46: SELECT usuario, telefono FROM usuarios
	WHERE compania IN('IUSACELL','UNEFON');

47: SELECT nombre,telefono FROM usuarios
	WHERE marca NOT IN('MOTOROLA','NOKIA');

48: SELECT SUM(saldo) FROM usuarios
	WHERE compania = 'TELCEL';
	
	
Respuestas a las peticiones JOIN;
--------------------------------

1:  SELECT prov.codigo,prov.nombre FROM provincias AS prov
	LEFT JOIN clientes AS cli
	ON cli.codigoProvincia=prov.codigo
	WHERE cli.codigoprovincia is NULL;
	
2:  SELECT DISTINCT prov.codigo,prov.nombre FROM provincias AS prov
	LEFT JOIN clientes AS cli
	ON cli.codigoProvincia=prov.codigo
	WHERE cli.codigoprovincia is NOT NULL;
