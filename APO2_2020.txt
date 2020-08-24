CREATE DATABASE banco;
CREATE TABLE tb_curso
(
	cod_curso INT NOT NULL AUTO_INCREMENT,
    nome_curso VARCHAR(60) NOT NULL,
    periodo INT NOT NULL,
    CONSTRAINT tb_curso_pk PRIMARY KEY (cod_curso)
);

CREATE TABLE tb_disciplina
(
	cod_disciplina INT NOT NULL AUTO_INCREMENT,
	nome_disciplina VARCHAR(60) NOT NULL,
    nome_professor VARCHAR(60) NOT NULL,
	CONSTRAINT tb_disciplina_pk PRIMARY KEY (cod_disciplina)
);

CREATE TABLE tb_professor
(
	cod_professor INT NOT NULL AUTO_INCREMENT,
    nome VARCHAR(30) NOT NULL,
    salario VARCHAR(60) NOT NULL,
    CONSTRAINT tb_professor PRIMARY KEY (cod_professor)
);

CREATE TABLE tb_aluno
(
	cod_aluno INT NOT NULL AUTO_INCREMENT,
    nome_aluno VARCHAR(60) NOT NULL,
    CONSTRAINT tb_aluno_pk PRIMARY KEY (cod_aluno)
);

CREATE TABLE tb_periodo
(
	cod_periodo INT NOT NULL AUTO_INCREMENT,
    periodo VARCHAR(30) NOT NULL,
    nome_aluno VARCHAR(60) NOT NULL,
    CONSTRAINT tb_periodo PRIMARY KEY (cod_periodo)
);

CREATE TABLE tb_nota
(
	cod_nota INT NOT NULL AUTO_INCREMENT,
    nota VARCHAR(30) NOT NULL,
    nome_disciplina VARCHAR(60) NOT NULL,
    nome_curso VARCHAR(60) NOT NULL,
    nome_aluno VARCHAR(60) NOT NULL,
    periodo VARCHAR(60) NOT NULL,
    CONSTRAINT tb_nota PRIMARY KEY (cod_nota)
);



SELECT count(nome_aluno) FROM tb_periodo 
WHERE periodo = "8";


SELECT P.nome_aluno
FROM tb_periodo AS P
JOIN tb_curso AS C ON C.periodo = "8";



SELECT P.nome As MaiorSalario, COUNT(C.nome_professor) AS MaiorQntDeAulas
FROM tb_professor AS P,
tb_disciplina AS C
WHERE salario = (SELECT MAX(salario) FROM tb_professor);



    
    
    
    