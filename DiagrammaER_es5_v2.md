```mermaid
erDiagram
    CLIENTE {
        int ID_Cliente PK
        string Nome
        string Cognome
        string Email
        string Indirizzo
    }
    
    PRODOTTO {
        int ID_Prodotto PK
        string Nome
        string Descrizione
        float Prezzo
        string Categoria
    }
    
    ORDINE {
        int ID_Ordine PK
        date Data_Ordine
        date Data_Consegna_Prevista
        string Stato
        int ID_Cliente FK
    }
    
    RECENSIONE {
        int ID_Recensione PK
        int Punteggio
        date Data
        string Commento
        int ID_Cliente FK
        int ID_Prodotto FK
    }
    
    PRODOTTO_ORDINE {
        int ID_Ordine FK
        int ID_Prodotto FK
        int ID_Ordine_Prodotto PK
    }
    
    CLIENTE ||--o{ ORDINE : effettua
    ORDINE ||--o{ PRODOTTO_ORDINE : contiene
    PRODOTTO ||--o{ PRODOTTO_ORDINE : contenuto_in
    CLIENTE ||--o{ RECENSIONE : scrive
    PRODOTTO ||--o{ RECENSIONE : riceve