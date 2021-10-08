# Banco de Dados do Universo Star Wars

## Banco de dados contendo informações sobre naves, pilotos e planetas do Universo Star Wars.

    CREATE DATABASE DBStarWars;

    CREATE TABLE Planetas(
      idPlaneta INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
      Nome VARCHAR (50) NOT NULL,
      Rotacao FLOAT NOT NULL,
      Orbita FLOAT NOT NULL,
      Diametro FLOAT NOT NULL,
      Clima VARCHAR(50) NOT NULL,
      População int NOT NULL
    )
    
    CREATE TABLE Naves(
      idNave INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
      Nome VARCHAR(100) NOT NULL,
      Modelo VARCHAR(150) NOT NULL,
      Passageiros INT NOT NULL,
      Carga FLOAT NOT NULL,
      Classe VARCHAR(100) NOT NULL
    )

    CREATE TABLE Pilotos(
      idPiloto INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
      Nome VARCHAR(200),
      AnoNascimento VARCHAR(10),
      idPlaneta INT NOT NULL,
      FOREIGN KEY (idPiloto) REFERENCES Pilotos(idPiloto)
    )

    CREATE TABLE PilotosNaves(
      idPiloto INT NOT NULL,
      idNave INT NOT NULL,
      FlagAutorizado BIT NOT NULL,
      PRIMARY KEY (idPiloto, idNave),
      FOREIGN KEY (idPiloto) REFERENCES Pilotos(idPiloto),
      FOREIGN KEY (idNave) REFERENCES Naves(idNave)
    )
