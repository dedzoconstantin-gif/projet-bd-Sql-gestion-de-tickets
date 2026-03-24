CREATE DATABASE GestionSupport;
USE GestionSupport;

CREATE TABLE Utilisateur (
    idUtilisateur INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE NOT NULL
);

CREATE TABLE AgentSupport (
    idAgent INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(100) NOT NULL,
    specialite VARCHAR(100)
);

CREATE TABLE ResponsableSupport (
    idResponsable INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(100) NOT NULL
);

CREATE TABLE Administrateur (
    idAdmin INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(100) NOT NULL
);

CREATE TABLE Ticket (
    idTicket INT AUTO_INCREMENT PRIMARY KEY,
    titre VARCHAR(200) NOT NULL,
    description TEXT,
    dateCreation DATETIME DEFAULT CURRENT_TIMESTAMP,
    statut VARCHAR(50),
    priorite VARCHAR(50),
    idUtilisateur INT,
    idAgent INT,
    
    FOREIGN KEY (idUtilisateur) REFERENCES Utilisateur(idUtilisateur),
    FOREIGN KEY (idAgent) REFERENCES AgentSupport(idAgent)
);

CREATE TABLE Commentaire (
    idCommentaire INT AUTO_INCREMENT PRIMARY KEY,
    texte TEXT,
    date DATETIME DEFAULT CURRENT_TIMESTAMP,
    idTicket INT,
    
    FOREIGN KEY (idTicket) REFERENCES Ticket(idTicket)
);

CREATE TABLE FichierJoint (
    idFichier INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(200),
    type VARCHAR(50),
    taille INT,
    idTicket INT,
    
    FOREIGN KEY (idTicket) REFERENCES Ticket(idTicket)
);

INSERT INTO Utilisateur (nom, email)
VALUES ('Ali', 'ali@email.com');

INSERT INTO AgentSupport (nom, specialite)
VALUES ('Sara', 'Réseau');

INSERT INTO Ticket (titre, description, statut, priorite, idUtilisateur, idAgent)
VALUES ('Problème connexion', 'Impossible de se connecter', 'Ouvert', 'Haute', 1, 1);

INSERT INTO Commentaire (texte, idTicket)
VALUES ('Nous analysons le problème', 1);




