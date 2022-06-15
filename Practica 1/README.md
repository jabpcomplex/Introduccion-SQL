**Schema (MySQL v5.7)**

    CREATE DATABASE escuela;
    
    CREATE TABLE cursos(
    IDcurso int(50) NOT NULL PRIMARY KEY,
    num_aula varchar(50) NOT NULL,
    horario varchar(50) NOT NULL,
    modalidad varchar(50),
    nombre_curso varchar(50),
    fecha_inicio varchar(50),
    capacidad_alumnos int(3));

    CREATE TABLE alumno(
    IDalumno varchar(50) NOT NULL PRIMARY KEY,
    nombre_alumno varchar(50) NOT NULL,
    edad int(3) NOT NULL,
    telefono numeric(20),
    IDcurso int(50),
    CONSTRAINT FK_cursos_id_alumno
    FOREIGN KEY(IDcurso) REFERENCES cursos(IDcurso));


    CREATE TABLE profesor(
    IDprofesor varchar(50) NOT NULL PRIMARY KEY,
    nombre_profesor varchar(50) NOT NULL,
    edad int(5) NOT NULL,
    telefono numeric(20),
    sexo varchar(20),
    IDcurso int(50),
    CONSTRAINT FK_cursos
    FOREIGN KEY(IDcurso) REFERENCES cursos(IDcurso))

    INSERT INTO
    cursos VALUES
    (1,"A-001","12pm-2pm", "presencial", "mecanica vectorial","23-Abril-2022",50);
    
    
    INSERT INTO
    cursos VALUES
    (2,"A-002","3pm-4pm", "presencial", "filosofia contemporanea","26-Mayo-2022",50);
     
     INSERT INTO
     cursos VALUES
     (3,"B-003","3pm-5pm", "presencial", "derecho constitucional","23-Mayo-2022",34);
    
    INSERT INTO
    cursos VALUES
    (4,"A-010","8:30am-10:30am", "presencial", "mecanica clasica","23-Abril-2022",40);
    
    INSERT INTO
    cursos VALUES
    (5,"B-010","3:30pm-5:30pm", "virtual", "psicologia social","23-Abril-2022",33);
    
    
    INSERT INTO
    cursos VALUES
    (6,"A-010","8:30am-10:30am", "virtual", "mecanica vectorial","23-Abril-2022",50);
    
    INSERT INTO
    cursos VALUES
    (7,"A-002","9:00am-11:00am", "virtual", "sociologia contemporaneal","22-Septiembre-2022",50);
    
    INSERT INTO
    cursos VALUES
    (8,"B-003","2:00pm-4pm", "presencial", "matematicas discretas","23-Enero-2022",34);
    
    INSERT INTO
    cursos VALUES
    (9,"A-011","10:30am-12:30pm", "presencial", "fisica cuantica","22-Agostol-2022",40);
    
    INSERT INTO
    cursos VALUES
    (10,"A-004","7:00am-09:00pm", "presencial", "filosofia de la ciencia","12-Diciembre-2022",50);
    
    
    INSERT INTO
    alumno VALUES
    ("919RNA61","Antonio Yamir Ledesma Briones",22,5540443310,2);
    
    INSERT INTO
    alumno VALUES
    ("839NS032","Luis Alberto Vazquez Mendez",29,5581856873,10);
    
    INSERT INTO
    alumno VALUES
    ("839RR04","Carla Judith Sanchez Perez",24,5545527832,7);
    
    INSERT INTO
    alumno VALUES
    ("919LD07","Fidel Segovia Alvarado",52,5514552288,3);
    
    INSERT INTO
    alumno VALUES
    ("919DR090","José Francisco Pacheco Rodríguez",25,5510619038,6);
    
    INSERT INTO
    alumno VALUES
    ("919RS","Isabel julian cruz",34,555521534,4);
    
    INSERT INTO
    alumno VALUES
    ("919NG02","Eugenio de la cruz",44,54268564545,10);
    
    INSERT INTO
    alumno VALUES
    ("919CL001", "Julio Alberto Bautista Pacheco",28, 5538059333, 9);
    
    INSERT INTO
    alumno VALUES
    ("1149RR075","Karen Vianey Butron Juarez", 24, 5543674289,5);
    
    INSERT INTO
    alumno VALUES
    ("919RG090","Diego Santiago", 33, 5682785334,8);
    
    INSERT INTO
    alumno VALUES
    ("529RR09","Gustavo Perez", 23, 5535502209,3);
    
    INSERT INTO
    alumno VALUES
    ("779SN001", "Andres Bernal Espinosa",30,5512938823,8);
    
    INSERT INTO
    alumno VALUES
    ("1149ZS02", "Oscar Rubén Blancas Ruiz", 33, 5521344047 , 7);
    
    INSERT INTO
    alumno VALUES
    ("MARIA919RRAN" , "SEGOVIA MERIDA",17, 5568726032,5);
    
    INSERT INTO
    alumno VALUES
    ("529RR06","Brenda Romero",27, 5526356415,3);
    
    INSERT INTO
    alumno VALUES
    ("879RV010","CEDILLO MARILES IVAN ALBERTO", 33, 5615080415, 6);
    
    INSERT INTO
    alumno VALUES
    ("789LR04"," GARCIA FLORES CRISTHIAN",23, 5539168804,9);
    
    INSERT INTO
    profesor VALUES
    ("unam1","Saul Gudman",32, 556293284, "H",4);
    
    INSERT INTO
    profesor VALUES
    ("unam2","Walter White",38, 556293284, "H",3);
    
    INSERT INTO
    profesor VALUES
    ("unam3","Albertana Camus",34, 556293284, "M",10);
    
    INSERT INTO
    profesor VALUES
    ("unam4","Stephen Strange",29, 556293284, "H",1);
    
    INSERT INTO
    profesor VALUES
    ("unam5","Sofia Sariñama",53, 556293284, "M",2);
    
    INSERT INTO
    profesor VALUES
    ("unam6","Leonel Messi",45, 556293284, "H",9);
    
    INSERT INTO
    profesor VALUES
    ("unam7","Jesus Ernesto",30, 556293284, "H",8);
    
    INSERT INTO
    profesor VALUES
    ("unam8","Saul Picaro",34, 556293284, "H",5);
    
    INSERT INTO
    profesor VALUES
    ("unam9","Andres Manuel",66, 556293284, "H",7);
    
    INSERT INTO
    profesor VALUES
    ("unam10","Enriqueta Peña",40, 556293284, "M",6);
    

---

**Query #1**

    SELECT *
    FROM cursos
    ORDER BY nombre_curso;

| IDcurso | num_aula | horario         | modalidad  | nombre_curso              | fecha_inicio       | capacidad_alumnos |
| ------- | -------- | --------------- | ---------- | ------------------------- | ------------------ | ----------------- |
| 3       | B-003    | 3pm-5pm         | presencial | derecho constitucional    | 23-Mayo-2022       | 34                |
| 2       | A-002    | 3pm-4pm         | presencial | filosofia contemporanea   | 26-Mayo-2022       | 50                |
| 10      | A-004    | 7:00am-09:00pm  | presencial | filosofia de la ciencia   | 12-Diciembre-2022  | 50                |
| 9       | A-011    | 10:30am-12:30pm | presencial | fisica cuantica           | 22-Agostol-2022    | 40                |
| 8       | B-003    | 2:00pm-4pm      | presencial | matematicas discretas     | 23-Enero-2022      | 34                |
| 4       | A-010    | 8:30am-10:30am  | presencial | mecanica clasica          | 23-Abril-2022      | 40                |
| 1       | A-001    | 12pm-2pm        | presencial | mecanica vectorial        | 23-Abril-2022      | 50                |
| 6       | A-010    | 8:30am-10:30am  | virtual    | mecanica vectorial        | 23-Abril-2022      | 50                |
| 5       | B-010    | 3:30pm-5:30pm   | virtual    | psicologia social         | 23-Abril-2022      | 33                |
| 7       | A-002    | 9:00am-11:00am  | virtual    | sociologia contemporaneal | 22-Septiembre-2022 | 50                |

---

**Query #2**

    SELECT *
    FROM profesor
    WHERE edad > 40;

| IDprofesor | nombre_profesor | edad | telefono  | sexo | IDcurso |
| ---------- | --------------- | ---- | --------- | ---- | ------- |
| unam5      | Sofia Sariñama  | 53   | 556293284 | M    | 2       |
| unam6      | Leonel Messi    | 45   | 556293284 | H    | 9       |
| unam9      | Andres Manuel   | 66   | 556293284 | H    | 7       |

---

**Query #3**

    SELECT AVG(edad)
    FROM alumno;

| AVG(edad) |
| --------- |
| 29.4706   |

---

[View on DB Fiddle](https://www.db-fiddle.com/f/3GSARdpsqYV8Ji1W4iMPVV/0)
