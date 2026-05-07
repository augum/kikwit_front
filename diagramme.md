erDiagram
    ETABLISSEM ||--|| CATEO : appartient
    ETABLISSEM ||--o| Cartographis_struct : decrit
    ETABLISSEM ||--o{ Finace_di : possede
    ETABLISSEM ||--o{ Indicateur_Tech : genere
    ETABLISSEM ||--o{ Personnel : emploie
    ETABLISSEM ||--o{ Source : utilise

    ETABLISSEM {
        int id PK
        string nom
        string zone
        string province
        int id_CATEO FK
    }

    CATEO {
        int id PK
        string nom
    }

    Cartographis_struct {
        int id_ESS FK
        string zone_couverte
        boolean presence_bloc
        int capacite_transfusion
        string equipe_biomed
    }

    Finace_di {
        int id PK
        int id_ESS FK
        string periode
        float capital_depart
        float capital_fin_mois
    }

    Indicateur_Tech {
        int id PK
        int id_ESS FK
        string periode
        int ncc
        int cpa
        int accouchement_pf
        int transfusion_totale
        int cesarienne
        int infection
    }

    Personnel {
        int id PK
        int id_ESS FK
        string agent_matricule
        string nom_agent
        string nouveau_maitre
    }

    Source {
        int id PK
        string type_source
    }