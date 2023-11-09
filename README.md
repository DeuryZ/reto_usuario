### CREATE DATABASE

   ```sql
CREATE DATABASE IF NOT EXISTS pruebas;
USE pruebas;
CREATE TABLE tblUsuarios (
   idx INT PRIMARY KEY AUTO_INCREMENT,
   usuario VARCHAR(20),
   nombre VARCHAR(20),
   sexo VARCHAR(1),
   nivel TINYINT,
   email VARCHAR(50),
   telefono VARCHAR(20),
   marca VARCHAR(20),
   compañia VARCHAR(20),
   saldo FLOAT,
   activo BOOLEAN
);
   ```
### DATA

   ```sql
USE pruebas;
INSERT INTO tblUsuarios 
VALUES 
('1','BRE2271','BRENDA','M','2','brenda@live.com','655-330-5736','SAMSUNG','IUSACELL','100','1'),
('2','OSC4677','OSCAR','H','3','oscar@gmail.com','655-143-4181','LG','TELCEL','0','1'),
('3','JOS7086','JOSE','H','3','francisco@gmail.com','655-143-3922','NOKIA','MOVISTAR','150','1'),
('4','LUI6115','LUIS','H','0','enrique@outlook.com','655-137-1279','SAMSUNG','TELCEL','50','1'),
('5','LUI7072','LUIS','H','1','luis@hotmail.com','655-100-8260','NOKIA','IUSACELL','50','0'),
('6','DAN2832','DANIEL','H','0','daniel@outlook.com','655-145-2586','SONY','UNEFON','100','1'),
('7','JAQ5351','JAQUELINE','M','0','jaqueline@outlook.com','655-330-5514','BLACKBERRY','AXEL','0','1'),
('8','ROM6520','ROMAN','H','2','roman@gmail.com','655-330-3263','LG','IUSACELL','50','1'),
('9','BLA9739','BLAS','H','0','blas@hotmail.com','655-330-3871','LG','UNEFON','100','1'),
('10','JES4752','JESSICA','M','1','jessica@hotmail.com','655-143-6861','SAMSUNG','TELCEL','500','1'),
('11','DIA6570','DIANA','M','1','diana@live.com','655-143-3952','SONY','UNEFON','100','0'),
('12','RIC8283','RICARDO','H','2','ricardo@hotmail.com','655-145-6049','MOTOROLA','IUSACELL','150','1'),
('13','VAL6882','VALENTINA','M','0','valentina@live.com','655-137-4253','BLACKBERRY','AT&T','50','0'),
('14','BRE8106','BRENDA','M','3','brenda2@gmail.com','655-100-1351','MOTOROLA','NEXTEL','150','1'),
('15','LUC4982','LUCIA','M','3','lucia@gmail.com','655-145-4992','BLACKBERRY','IUSACELL','0','1'),
('16','JUA2337','JUAN','H','0','juan@outlook.com','655-100-6517','SAMSUNG','AXEL','0','0'),
('17','ELP2984','ELPIDIO','H','1','elpidio@outlook.com','655-145-9938','MOTOROLA','MOVISTAR','500','1'),
('18','JES9640','JESSICA','M','3','jessica2@live.com','655-330-5143','SONY','IUSACELL','200','1'),
('19','LET4015','LETICIA','M','2','leticia@yahoo.com','655-143-4019','BLACKBERRY','UNEFON','100','1'),
('20','LUI1076','LUIS','H','3','luis2@live.com','655-100-5085','SONY','UNEFON','150','1'),
('21','HUG5441','HUGO','H','2','hugo@live.com','655-137-3935','MOTOROLA','AT&T','500','1');
   ```

### Bloque 1

##### Consultas

1. Listar los nombres de los usuarios

   ```sql
   # select nombre from tblUsuarios;
   ```

2. Calcular el saldo máximo de los usuarios de sexo “Mujer”

     ```sql
      # select max(saldo) from tblUsuarios where sexo='M';
     ```

3. Listar nombre y teléfono de los usuarios con teléfono NOKIA, BLACKBERRY o SONY

     ```sql
      # select nombre, telefono, marca from tblUsuarios where marca = 'NOKIA' OR marca = 'BLACKBERRY' OR marca = 'SONY';
     ```

4. Contar los usuarios sin saldo o inactivos

     ```sql
      # select count(usuario) from tblUsuarios where saldo = 0 OR activo = 0;
     ```

5. Listar el login de los usuarios con nivel 1, 2 o 3

     ```sql
      # select usuario from tblUsuarios where nivel=1 or nivel=2 or nivel=3;
     ```

6. Listar los números de teléfono con saldo menor o igual a 300

     ```sql
      # select telefono, saldo from tblUsuarios where saldo <=300;
     ```

7. Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL

     ```sql
      # select SUM(saldo) from tblUsuarios where compañia = 'NEXTEL';
     ```

8. Contar el número de usuarios por compañía telefónica

     ```sql
      # select compañia, count(compañia) from tblUsuarios GROUP BY compañia;
     ```

9. Contar el número de usuarios por nivel

     ```sql
      # select nivel, count(nivel) from tblUsuarios GROUP BY nivel;
     ```

10. Listar el login de los usuarios con nivel 2

      ```sql
       # select usuario from tblUsuarios where nivel=2;
      ```

11. Mostrar el email de los usuarios que usan gmail

      ```sql
       # select email from tblUsuarios where email like '%@gmail%';
      ```

12. Listar nombre y teléfono de los usuarios con teléfono LG, SAMSUNG o MOTOROLA

      ```sql
       # select nombre, telefono, marca from tblUsuarios where marca = 'LG' OR marca = 'SAMSUNG' OR marca = 'MOTOROLA';
      ```

------

### Bloque 2

##### Consultas

1. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG o SAMSUNG

     ```sql
      # select nombre, telefono, marca from tblUsuarios where marca <> 'LG' AND marca <> 'SAMSUNG';
     ```

2. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL

     ```sql
      # select usuario, telefono, compañia  from tblUsuarios where compañia = 'IUSACELL';
     ```

3. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL

     ```sql
      # select usuario, telefono, compañia  from tblUsuarios where compañia <> 'TELCEL';
     ```

4. Calcular el saldo promedio de los usuarios que tienen teléfono marca NOKIA

     ```sql
      # select AVG(saldo) from tblUsuarios where marca = 'NOKIA';
     ```

5. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL

     ```sql
      # select usuario, telefono, compañia  from tblUsuarios where compañia = 'IUSACELL' or compañia = 'AXEL';
     ```

6. Mostrar el email de los usuarios que no usan yahoo

     ```sql
      # select email from tblUsuarios where email not like '%@yahoo%';
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL

     ```sql
      # select usuario, compañia from tblUsuarios where compañia <> 'IUSACELL' and compañia <> 'TELCEL';
     ```

8. Listar el login y teléfono de los usuarios con compañia telefónica UNEFON

     ```sql
      # select usuario, telefono, compañia  from tblUsuarios where compañia = 'UNEFON';
     ```

9. Listar las diferentes marcas de celular en orden alfabético descendentemente

     ```sql
      # select marca from tblUsuarios order by marca desc;
     ```

10. Listar las diferentes compañias en orden alfabético aleatorio

      ```sql
       # select compañia from tblUsuarios group by compañia order by RAND();
      ```

11. Listar el login de los usuarios con nivel 0 o 2

      ```sql
       # select usuario, nivel from tblUsuarios where nivel = 0 or nivel = 2;
      ```

12. Calcular el saldo promedio de los usuarios que tienen teléfono marca LG

      ```sql
       # select avg(saldo) from tblUsuarios where marca = 'LG';
      ```

------

### Bloque 3

##### Consultas

1. Listar el login de los usuarios con nivel 1 o 3

     ```sql
      # select usuario, nivel from tblUsuarios where nivel = 1 or nivel = 3;
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACKBERRY

     ```sql
      # select nombre, telefono, marca from tblUsuarios where marca <> 'BLACKBERRY';
     ```

3. Listar el login de los usuarios con nivel 3

     ```sql
      # select usuario, nivel from tblUsuarios where nivel = 3;
     ```

4. Listar el login de los usuarios con nivel 0

     ```sql
      # select usuario, nivel from tblUsuarios where nivel = 0;
     ```

5. Listar el login de los usuarios con nivel 1

     ```sql
      # select usuario, nivel from tblUsuarios where nivel = 1;
     ```

6. Contar el número de usuarios por sexo

     ```sql
      # select sexo, count(sexo) from tblUsuarios group by(sexo);
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica AT&T

     ```sql
      # select usuario, telefono, compañia from tblUsuarios where compañia = 'AT&T';
     ```

8. Listar las diferentes compañias en orden alfabético descendentemente

     ```sql
      # select compañia from tblUsuarios order by compañia desc;
     ```

9. Listar el login de los usuarios inactivos

     ```sql
      # select usuario, activo  from tblUsuarios where activo = 0;
     ```

10. Listar los números de teléfono sin saldo

      ```sql
       # select telefono, saldo from tblUsuarios where saldo = 0;
      ```

11. Calcular el saldo mínimo de los usuarios de sexo “Hombre”

        ```sql
         # select min(saldo) from tblUsuarios where sexo = 'H';
         # otra opción:
         # select min(saldo) from tblUsuarios where sexo = 'H' and saldo <> 0;
        ```

12. Listar los números de teléfono con saldo mayor a 300

      ```sql
       # select telefono, saldo from tblUsuarios where saldo > 300;
      ```

------

### Bloque 4

##### Consultas

1. Contar el número de usuarios por marca de teléfono

     ```sql
      # select marca, count(marca) from tblUsuarios group by marca;
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG

     ```sql
      # select nombre, telefono, marca from tblUsuarios where marca <> 'lG';
     ```

3. Listar las diferentes compañias en orden alfabético ascendentemente

     ```sql
      # select compañia from tblUsuarios order by compañia asc;
     ```

4. Calcular la suma de los saldos de los usuarios de la compañia telefónica UNEFON

     ```sql
      # select sum(saldo) from tblUsuarios where compañia = 'UNEFON';
     ```

5. Mostrar el email de los usuarios que usan hotmail

     ```sql
      # select email from tblUsuarios where email like '%@hotmail%';
     ```

6. Listar los nombres de los usuarios sin saldo o inactivos

     ```sql
      # select nombre, saldo, activo from tblUsuarios where saldo = 0 or activo = 0;
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o TELCEL

     ```sql
      # select usuario, telefono, compañia from tblUsuarios where compañia = 'IUSACELL' OR compañia = 'TELCEL';
     ```

8. Listar las diferentes marcas de celular en orden alfabético ascendentemente

     ```sql
      # select marca from tblUsuarios order by marca asc;
     ```

9. Listar las diferentes marcas de celular en orden alfabético aleatorio

     ```sql
      # select marca from tblUsuarios group by marca order by RAND();
     ```

10. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o UNEFON

      ```sql
       # select usuario, telefono, compañia   from tblUsuarios where compañia = 'IUSACELL' or compañia = 'UNEFON';
      ```

11. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca MOTOROLA o NOKIA

      ```sql
       # select nombre, telefono, marca  from tblUsuarios where marca <> 'MOTOROLA' and marca <> 'NOKIA';
      ```

12. Calcular la suma de los saldos de los usuarios de la compañia telefónica TELCEL

      ```sql
       # select sum(saldo) from tblUsuarios where compañia = 'TELCEL';
      ```
