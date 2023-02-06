


 DROP database TESTE

 CREATE DATABASE TESTE

  USE TESTE

CREATE TABLE PAISES (
ID INT PRIMARY KEY,
NOME_PAIS VARCHAR(50),
MOEDA_LOCAL VARCHAR(50),
TAXA_IMPOSTO DECIMAL (10,2)
);

CREATE TABLE CARGO (
ID INT PRIMARY KEY,
NOME_CARGO VARCHAR(50),
VALOR_SALARIO MONEY
);

CREATE TABLE FUNCIONARIOS (
ID INT PRIMARY KEY,
NOME VARCHAR(50),
CARGO INT,
IDADE INT,
SEXO CHAR(1),
TELEFONE VARCHAR(20),
PAIS_DE_NASCIMENTO VARCHAR(50),
PAIS_DE_TRABALHO INT,
ENDERECO_RESIDENCIAL VARCHAR(100),
FOREIGN KEY (PAIS_DE_TRABALHO) REFERENCES PAISES(ID),
FOREIGN KEY (CARGO) REFERENCES CARGO (ID)
);

CREATE TABLE EMPRESAS (
ID INT PRIMARY KEY,
NOME VARCHAR(50),
ENDERECO VARCHAR(100),
TELEFONE VARCHAR(20),
PAIS INT,
FOREIGN KEY (PAIS) REFERENCES PAISES(ID)
);

CREATE TABLE CONTAS_BANCARIAS (
ID INT PRIMARY KEY,
AGENCIA VARCHAR(20),
BANCO VARCHAR(50),
CONTA_CORRENTE VARCHAR(20),
FUNCIONARIO INT,
PAIS INT,
FOREIGN KEY (FUNCIONARIO) REFERENCES FUNCIONARIOS(ID),
FOREIGN KEY (PAIS) REFERENCES PAISES(ID)
);

CREATE TABLE SALARIOS (
ID INT PRIMARY KEY,
SALARIO_BRUTO DECIMAL(10, 2),
TAXA_DE_IMPOSTO DECIMAL,
SALARIO_LIQUIDO DECIMAL(10, 2),
FUNCIONARIO INT,
EMPRESA INT,
PAIS INT,
FOREIGN KEY (FUNCIONARIO) REFERENCES FUNCIONARIOS(ID),
FOREIGN KEY (EMPRESA) REFERENCES EMPRESAS(ID),
FOREIGN KEY (PAIS) REFERENCES PAISES(ID),
);


INSERT INTO Paises (ID, NOME_PAIS, MOEDA_LOCAL, TAXA_IMPOSTO)
VALUES (1, 'Espanha', 'Euro', 6.35 ),
(2, 'França', 'Euro', 25.85),
(3, 'Portugal', 'Euro', 23.91),
(4, 'Irlanda', 'Euro', 0.00),
(5, 'Itália', 'Euro', 32.10),
(6, 'Reino Unido', 'Libra Esterlina', 0.00 );

INSERT INTO EMPRESAS (ID, NOME, ENDERECO, TELEFONE, PAIS)
VALUES
(1, 'TechCo', '123 Main St', '+1 123 456 789', 1),
(2, 'DataPro', '456 Park Ave', '+1 987 654 321', 2),
(3, 'Networks Inc', '789 Oak St', '+1 111 222 333', 3),
(4, 'CloudTech', '246 Elm St', '+1 444 555 666', 4),
(5, 'Software Solutions', '369 Maple Rd', '+1 777 888 999', 5),
(6, 'Cyber Systems', '159 Pine St', '+1 123 231 321', 1),
(7, 'IT Innovations', '753 Cedar Blvd', '+1 111 222 333', 2),
(8, 'Digital Dynamics', '951 Rose St', '+1 555 666 777', 3),
(9, 'TechThink', '147 Tulip Ave', '+1 999 888 777', 4),
(10, 'Innovate IT', '753 Daisy Rd', '+1 555 555 555', 5);


INSERT INTO CARGO (ID, NOME_CARGO, VALOR_SALARIO)
VALUES
(1, 'Desenvolvedor de Software', 75000),
(2, 'Gerente de TI', 115000),
(3, 'Analista de Sistemas', 90000),
(4, 'Administrador de Banco de Dados', 95000),
(5, 'Arquiteto de Soluções', 125000),
(6, 'Engenheiro de Software', 80000),
(7, 'Técnico em Segurança da Informação', 72000),
(8, 'Consultor de TI', 100000),
(9, 'Desenvolvedor de Aplicativos Móveis', 78000),
(10, 'Engenheiro de Rede', 92000);


INSERT INTO FUNCIONARIOS (ID, NOME, CARGO, IDADE, SEXO, TELEFONE, PAIS_DE_NASCIMENTO, PAIS_DE_TRABALHO, ENDERECO_RESIDENCIAL)
VALUES
(1, 'João da Silva', 1, 32, 'M', '+55 11 98765-4321', 'Brasil', 1, 'Rua das Flores, 123'),
(2, 'Maria Pereira', 2, 41, 'F', '+33 6 12345-6789', 'França', 2, 'Avenue des Champs-Élysées, 789'),
(3, 'Pedro Rodrigues', 3, 28, 'M', '+351 9 12345-6789', 'Portugal', 3, 'Rua de Lisboa, 246'),
(4, 'Ana Oliveira', 4, 35, 'F', '+353 1 12345-6789', 'Irlanda', 4, 'Dublin Street, 369'),
(5, 'Luís Sousa', 5, 45, 'M', '+39 3 12345-6789', 'Itália', 5, 'Roma Street, 159'),
(6, 'Isabel Silva', 6, 50, 'F', '+44 20 12345-6789', 'Reino Unido', 6, 'London Road, 753'),
(7, 'Fábio Pereira', 1, 25, 'M', '+55 11 12345-6789', 'Brasil', 1, 'Rua das Palmas, 258'),
(8, 'Carla Oliveira', 2, 30, 'F', '+33 6 98765-4321', 'França', 2, 'Avenue des Tuileries, 147'),
(9, 'Ricardo Silva', 3, 40, 'M', '+351 9 98765-4321', 'Portugal', 3, 'Rua de Porto, 852'),
(10, 'Sofia Rodrigues', 4, 27, 'F', '+353 1 98765-4321', 'Irlanda', 4, 'Galway Road, 963');



SELECT * FROM FUNCIONARIOS


