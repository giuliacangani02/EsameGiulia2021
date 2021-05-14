# Diagramma ER
![image](https://user-images.githubusercontent.com/72736319/118286658-f74bbd80-b4d2-11eb-83ba-b5a7ca872c4a.png)

#  sql
Nave(Id_nave,nome_comandante,nome_armatore,porto_provenienza,porto_destinazione,capacita_n_container,calendario,Id_banchina)
CREATE TABLE Nave (
Id_nave INT NOT NULL,
Id_banchina INT NOT NULL,
nome_comandante VARCHAR(45),
nome_armatore VARCHAR(45),
porto_provenienza VARCHAR(45),
porto_destinazione VARCHAR(45),
capacita_n_container INT NOT NULL,
primary key(Id_nave),
foreign key(Id_banchina) references Banchina(Id_banchina) on delete cascade)
engine=InnoDB;


INSERT INTO Nave(Id_nave,nome_comandante,nome_armatore,porto_provenienza,porto_destinazione,capacita_n_container,calendario,Id_banchina)
Values(001,111,'Comandante 1','Armatore 1','Cagliari','Bari',20),(002,222,'Comandante 2','Armatore 2','Cagliari','Roma',20),
(003,333,'Comandante 3','Armatore 3','Roma','Madrid',26);


Lista_appuntamento_nave(Id_listapp_nave,nome_arrivo_nave,ora_arrivo_nave,data_arrivo_nave,Id_operatore)
CREATE TABLE Lista_appuntamento_nave(
Id_listapp_nave INT NOT NULL,
Id_operatore INT NOT NULL,
nome_arrivo_nave VARCHAR(45),
ora_arrivo_nave DATETIME,
data_arrivo_nave date,
primary key(Id_listapp_nave),
foreign key(Id_operatore) references Operatore (Id_operatore) on delete cascade)
engine=InnoDB;



INSERT INTO Lista_appuntamento_nave(Id_listapp_nave,nome_arrivo_nave,ora_arrivo_nave,data_arrivo_nave,Id_operatore)
Values(101,1111,'Msc','16','03-05-2021'),(102,2222,'Msc Meraviglia','15','03-06-2021'),
(103,3333,'Msc Splendi','11','11-06-2021');

Banchina(Id_banchina,carico_container,scarico_container,Id_operatore)
CREATE TABLE Banchina (
Id_banchina INT NOT NULL,
Id_operatore INT NOT NULL,
carico_container VARCHAR(45),
scarico_container VARCHAR(45),
primary key(Id_banchina),
foreign key(Id_operatore) references Operatore(Id_operatore) on delete cascade)
engine=InnoDB;


INSERT INTO Banchina(Id_banchina,n_banchina,carico_container,scarico_container,Id_operatore)
Values(99,100,12,'carico','scarico'),(98,200,10,'carico','scarico'),
(97,300,19,'carico','scarico');



Operatore(Id_operatore,nome,cognome,matricola)
CREATE TABLE Operatore(
Id_operatore INT NOT NULL,
nome VARCHAR(45),
cognome VARCHAR(45),
matricola VARCHAR(45),
primary key(Id_operatore))
engine=InnoDB;


INSERT INTO Operatore(Id_operatore,nome,cognome,matricola)
Values(444,'Carlo','Alberto','matricola 1'),(555,'Carletto','Pippo','matricola 2'),
(666,'Giulia','Piccione','matricola 3');



Container(Id_container,categoria,codice_iso_6344,info_generali,peso_totale,posizione,n_moloScarico,n_moloCarico,Id_nave,Id_tir,Id_StackingArea)
CREATE TABLE Container (
Id_container INT NOT NULL,
Id_nave INT NOT NULL,
Id_tir INT NOT NULL,
Id_StackingArea INT NOT NULL,
categoria VARCHAR(45),
codice_iso_6344 VARCHAR(45),
info_generali VARCHAR(45),
peso_totale  float(4,5),
posizione VARCHAR(45),
n_moloScarico INT NOT NULL,
n_moloCarico INT NOT NULL,
primary key(Id_container),
foreign key(Id_nave) references Nave (Id_nave) on delete cascade,
foreign key(Id_StackingArea) references StackingArea (Id_StackingArea) on delete cascade,
foreign key(Id_tir) references Tir(Id_tir) on delete cascade)
engine=InnoDB;


INSERT INTO Container(Id_container,categoria,codice_iso_6344,info_generali,peso_totale,posizione,n_moloScarico,n_moloCarico,Id_nave,Id_tir,Id_StackingArea)
Values(777,001,234,987,'sportiva','DDDE','informazione',12.5,'posizione 1',1,1),(888,002,456,876,'elegante','DDDE','informazione',10.5,'posizione 2',2,2),
(999,003,678,765,'elegante','DDDE','informazione',9.5,'posizione 3',3,3);


Merce(Id_merce,tipo_merce,peso_merce,categoria_merce,Id_container)
CREATE TABLE Merce(
Id_merce INT NOT NULL,
Id_container INT NOT NULL,
tipo_merce VARCHAR(45),
peso_merce float(4,5),
categoria_merce VARCHAR(45),
primary key(Id_merce),
foreign key(Id_container) references Container(Id_container) on delete cascade)
engine=InnoDB;

INSERT INTO Merce(Id_merce,tipo_merce,peso_merce,categoria_merce,Id_container)
Values(321,777,'sportiva',7.3,'categoria 1'),(432,888,'sportiva 2',7.8,'categoria 2'),
(543,999,'sportiva 3',9.8,'categoria 3');



Tir(Id_tir,dimensione,modello,targa)
CREATE TABLE Tir(
Id_tir INT NOT NULL,
dimensione float(4,5),
modello VARCHAR(45),
targa VARCHAR(45),
primary key(Id_tir))
engine=InnoDB;

INSERT INTO Tir(Id_tir,dimensione,modello,targa)
Values(445,20.1,'nuovo','FR56TY7U'),(446,20.0,'VECCHIO','FR58IY7U'),
(447,20.9,'nuovo','FR560OI87U');

Richiesta_tir_lista(Id_richiesta_Container,data_ritiroContainer,ora_ritiroContainer,luogo,Id_camionista,Id_tir)
CREATE TABLE Richiesta_tir_lista (
Id_richiesta_Container INT NOT NULL,
Id_camionista INT NOT NULL,
Id_tir INT NOT NULL,
data_ritiroContainer date,
ora_ritiroContainer DATETIME,
luogo VARCHAR(45),
primary key(Id_richiesta_Container),
foreign key(Id_camionista) references Camionista (Id_camionista) on delete cascade,
foreign key(Id_tir) references Tir(Id_tir) on delete cascade)
engine=InnoDB;

INSERT INTO Richiesta_tir_lista(Id_richiesta_Container,data_ritiroContainer,ora_ritiroContainer,luogo,Id_camionista,Id_tir) 
Values(1000,777,'sportiva',7.3,'categoria 1'),(432,888,'sportiva 2',7.8,'categoria 2'),
(543,999,'sportiva 3',9.8,'categoria 3');

Carrello(Id_interfacciaCarrello,n_carrello,n_banchina)
CREATE TABLE Carrello(
Id_interfacciaCarrello INT NOT NULL,
n_carrello int not null,
n_banchina int not null,
primary key(Id_interfacciaCarrello))
engine=InnoDB;


StackingArea(Id_StackingArea,n_posti_tot,posti_disponibili,Id_interfacciaCarrello)
CREATE TABLE StackingArea(
Id_StackingArea INT NOT NULL,
Id_interfacciaCarrello INT NOT NULL,
n_posti int not null,
posti_disponibili int not null,
primary key(Id_StackingArea),
foreign key(Id_interfacciaCarrello) references Carrello(Id_interfacciaCarrello) on delete cascade)
engine=InnoDB;


Camionista(Id_camionista,nome,cognome,p_parcheggioassegnato,username,email,indirizzo,password)
CREATE TABLE Camionista(
Id_camionista INT NOT NULL,
nome VARCHAR(45),
cognome VARCHAR(45),
p_parcheggioassegnato VARCHAR(45),
username VARCHAR(50) NOT NULL UNIQUE,
email varchar(45),
indirizzo varchar(45),
password VARCHAR(255) NOT NULL,
primary key(Id_camionista))
engine=InnoDB;


