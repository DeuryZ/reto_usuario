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
