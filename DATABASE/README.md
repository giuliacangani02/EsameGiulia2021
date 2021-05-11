# Diagramma ER
![image](https://user-images.githubusercontent.com/72736319/117885369-0ef62c80-b2ae-11eb-9f30-7b0618934e8a.png)
#  sql

CREATE TABLE Nave (
Id_nave INT NOT NULL,
Id_banchina INT NOT NULL,
nome_comandante VARCHAR(45),
nome_armatore VARCHAR(45),
porto_provenienza VARCHAR(45),
porto_destinazione VARCHAR(45),
primary key(Id_nave),
foreign key(Id_banchina) references Banchina(Id_banchina) on delete cascade)
engine=InnoDB;


CREATE TABLE Lista_appuntamento_nave(
Id_listapp_nave INT NOT NULL,
Id_operatore INT NOT NULL,
Id_banchina INT NOT NULL,
nome_arrivo_nave VARCHAR(45),
ora_arrivo_nave VARCHAR(45),
data_arrivo_nave VARCHAR(45),
primary key(Id_listapp_nave),
foreign key(Id_operatore) references Operatore (Id_operatore) on delete cascade)
engine=InnoDB;


CREATE TABLE Banchina (
Id_banchina INT NOT NULL,
Id_operatore INT NOT NULL,
n_banchina VARCHAR(45),
carico_container VARCHAR(45),
scarico_container VARCHAR(45),
primary key(Id_banchina),
foreign key(Id_operatore) references Operatore(Id_operatore) on delete cascade)
engine=InnoDB;


CREATE TABLE Operatore(
Id_operatore INT NOT NULL,
nome VARCHAR(45),
cognome VARCHAR(45),
matricola VARCHAR(45),
primary key(Id_operatore))
engine=InnoDB;


CREATE TABLE Container (
Id_container INT NOT NULL,
Id_nave INT NOT NULL,
Id_tir INT NOT NULL,
categoria VARCHAR(45),
codice_iso_6344 VARCHAR(45),
info_generali VARCHAR(45),
peso_totale  VARCHAR(45),
posizione VARCHAR(45),
primary key(Id_container),
foreign key(Id_nave) references Nave (Id_nave) on delete cascade,
foreign key(Id_tir) references Tir(Id_tir) on delete cascade)
engine=InnoDB;



CREATE TABLE Merce(
Id_merce INT NOT NULL,
Id_container INT NOT NULL,
tipo_merce VARCHAR(45),
peso_merce VARCHAR(45),
categoria_merce VARCHAR(45),
primary key(Id_merce),
foreign key(Id_container) references Container(Id_container) on delete cascade)
engine=InnoDB;


CREATE TABLE Tir(
Id_tir INT NOT NULL,
dimensione VARCHAR(45),
modello VARCHAR(45),
targa VARCHAR(45),
primary key(Id_tir))
engine=InnoDB;



CREATE TABLE Richiesta_tir_lista (
Id_richiesta_Container INT NOT NULL,
Id_camionista INT NOT NULL,
Id_tir INT NOT NULL,
data_ritiroContainer VARCHAR(45),
ora_ritiroContainer VARCHAR(45),
luogo VARCHAR(45),
primary key(Id_richiesta_Container),
foreign key(Id_camionista) references Camionista (Id_camionista) on delete cascade,
foreign key(Id_tir) references Tir(Id_tir) on delete cascade)
engine=InnoDB;


CREATE TABLE Carrello(
Id_interfacciaCarrello INT NOT NULL,
n_carrello VARCHAR(45),
n_banchina VARCHAR(45),
primary key(Id_interfacciaCarrello))
engine=InnoDB;



CREATE TABLE StackingArea(
Id_StackingArea INT NOT NULL,
Id_container INT NOT NULL,
Id_interfacciaCarrello INT NOT NULL,
n_posti VARCHAR(45),
posti_disponibili VARCHAR(45),
primary key(Id_StackingArea),
foreign key(Id_container) references Container(Id_container) on delete cascade,
foreign key(Id_interfacciaCarrello) references Carrello(Id_interfacciaCarrello) on delete cascade)
engine=InnoDB;


CREATE TABLE Camionista(
Id_camionista INT NOT NULL,
nome VARCHAR(45),
cognome VARCHAR(45),
p_parcheggioassegnato VARCHAR(45),
primary key(Id_camionista))
engine=InnoDB;
