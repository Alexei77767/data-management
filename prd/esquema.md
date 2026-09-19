
erDiagram
    USERS ||--o{ NOTES : crea
    USERS ||--o{ AUDIT_LOG : registra
    USERS ||--o{ ENTRY_NOTES : crea
    USERS ||--o{ ENTRY_AUDIT_LOG : registra

    CLIENTS ||--o{ NOTES : pertenece
    CLIENTS ||--o{ NOTE_LINES : asignado_a

    NOTES ||--o{ NOTE_LINES : contiene
    NOTES ||--o{ AUDIT_LOG : tiene_historial

    PRODUCTS ||--o{ NOTE_LINES : producto
    COLORS ||--o{ NOTE_LINES : color

    ENTRY_NOTES ||--o{ ENTRY_LINES : contiene
    ENTRY_NOTES ||--o{ ENTRY_AUDIT_LOG : tiene_historial

    PRODUCTS ||--o{ ENTRY_LINES : producto
    COLORS ||--o{ ENTRY_LINES : color

    USERS {
        int id PK
        text name
        text username
        text password_hash
        text role
        int active
    }

    CLIENTS {
        int id PK
        text name
        int active
    }

    PRODUCTS {
        int id PK
        text presentation
        text thickness
        text material
        int active
    }

    COLORS {
        int id PK
        text code
        text name
        int active
    }

    NOTES {
        int id PK
        int note_sequence
        text note_number
        text note_date
        int client_id FK
        int created_by FK
    }

    NOTE_LINES {
        int id PK
        int note_id FK
        int product_id FK
        int color_id FK
        int client_id FK
        text physical_note_number
        text lot
        real kilos
        real price_per_kilo
        text entry_time
    }

    AUDIT_LOG {
        int id PK
        int note_id FK
        int actor_id FK
        text action
        text detail
        text created_at
    }

    ENTRY_NOTES {
        int id PK
        int entry_sequence
        text entry_date
        text presentation_type
        text movement_type
        int created_by FK
    }

    ENTRY_LINES {
        int id PK
        int entry_note_id FK
        int product_id FK
        int color_id FK
        text lot
        real bags
        real recovered_bags
        real kilos
        text observations
        text entry_time
    }

    ENTRY_AUDIT_LOG {
        int id PK
        int entry_note_id FK
        int actor_id FK
        text action
        text detail
        text created_at
    }

    ENTRY_ISSUES {
        int id PK
        text name
        int active
    }
