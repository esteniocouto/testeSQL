


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
(6, 'Cyber Systems', '159 Pine St', '+1 123 231 321', 1);


INSERT INTO CARGO (ID, NOME_CARGO, VALOR_SALARIO)
VALUES
(1, 'Desenvolvedor de Software', 75000),
(2, 'Gerente de TI', 115000),
(3, 'Analista de Sistemas', 90000),
(4, 'Administrador de Banco de Dados', 95000),
(5, 'Arquiteto de Soluções', 125000),
(6, 'Engenheiro de Software', 80000);


INSERT INTO FUNCIONARIOS (ID, NOME, CARGO, IDADE, SEXO, TELEFONE, PAIS_DE_NASCIMENTO, PAIS_DE_TRABALHO, ENDERECO_RESIDENCIAL)
VALUES
(1, 'João da Silva', 1, 32, 'M', '+55 11 98765-4321', 'Brasil', 1, 'Rua das Flores, 123'),
(2, 'Maria Pereira', 2, 41, 'F', '+33 6 12345-6789', 'França', 2, 'Avenue des Champs-Élysées, 789'),
(3, 'Pedro Rodrigues', 3, 28, 'M', '+351 9 12345-6789', 'Portugal', 3, 'Rua de Lisboa, 246'),
(4, 'Ana Oliveira', 4, 35, 'F', '+353 1 12345-6789', 'Irlanda', 4, 'Dublin Street, 369'),
(5, 'Luís Sousa', 5, 45, 'M', '+39 3 12345-6789', 'Itália', 5, 'Roma Street, 159'),
(6, 'Isabel Silva', 6, 50, 'F', '+44 20 12345-6789', 'Reino Unido', 6, 'London Road, 753');

INSERT INTO CONTAS_BANCARIAS (ID, AGENCIA, BANCO, CONTA_CORRENTE, FUNCIONARIO, PAIS)
VALUES (1, '1234', 'Banco do Brasil', '123456789', 1, 1),
(2, '2345', 'Itau', '987654321', 2, 2),
(3, '3456', 'Santander', '654321987', 3, 3),
(4, '4567', 'Bradesco', '456789123', 4, 4),
(5, '5678', 'Caixa', '789123456', 5, 5),
(6, '6789', 'Banco Inter', '369258147', 6, 6);



SELECT
FUNCIONARIOS.NOME AS NOME_FUNCIONARIO,
CARGO.NOME_CARGO AS CARGO,
EMPRESAS.NOME AS NOME_EMPRESA,
PAISES.NOME_PAIS AS PAIS,
CARGO.VALOR_SALARIO AS VALOR_SALARIO,
(CARGO.VALOR_SALARIO - (CARGO.VALOR_SALARIO * (PAISES.TAXA_IMPOSTO/100))) AS SALARIO_LIQUIDO
FROM FUNCIONARIOS
INNER JOIN CARGO ON FUNCIONARIOS.CARGO = CARGO.ID
INNER JOIN EMPRESAS ON FUNCIONARIOS.PAIS_DE_TRABALHO = EMPRESAS.PAIS
INNER JOIN PAISES ON FUNCIONARIOS.PAIS_DE_TRABALHO = PAISES.ID;

SELECT * FROM FUNCIONARIOS


(S.SALARIO_BRUTO - (S.SALARIO_BRUTO * (P.TAXA_IMPOSTO/100)))
(CARGO.VALOR_SALARIO - (CARGO.VALOR_SALARIO * (PAISES.TAXA_IMPOSTO/100)))




Portugal() {
    salary = document.getElementById("salario").value;
    var tax_one = 14.5  < 7112
    var tax_two = 23.0 >= 7112
    var tax_three = 28.5 >= 10732 E < 20332
    var tax_fourth = 35.0 >= 20322 && salary < 25075
    var tax_fifth = 37.0 >= 25075 && salary < 36967
    var tax_sixth = 45.0 > 36967 && salary < 80882
    var tax_seventh = 48.0  >= 80882


 

Irlanda() {
    var text = "Se gasta pouco na Irlanda";
    salary = document.getElementById("salario").value;
    var tax_one = 20 <= 36800
    var tax_two = 40 > 12012 && salary <= 21295

ReinoUnido() {
   
    var tax_one = 0 < 9880  
    var tax_two = 20 <= 12570
    var tax_three = 40 <= 50270
    var tax_fourth = 45 >= 150000



 Italia() {
    
    var tax_one = 23 <= 15000
    var tax_two = 25 > 15000 && salary <= 28000
    var tax_three = 35 >= 28001 && salary < 55000
    var tax_fourth = 43 > 55001



Espanha() {
               = 0 < 5550
    var tax_one = 19 > 5550 && salary <= 12450
    var tax_two = 24 > 12450 && salary <= 20200
    var tax_three = 30 > 20200 && salary <= 35200
    var tax_fourth = 37 > 35200 && salary <= 60000
    var tax_fifth = 45 >= 60000


Franca() salary <= 35000)  - 9043
 (salary > 35000 && salary <= 40000)  



