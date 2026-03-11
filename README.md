# Database Relational Diagram



```mermaid

erDiagram

    TYPE ||--o{ HOTEL : "is"

    HOTEL ||--o{ ROOM : "is composed"

    CATEGORY ||--o{ ROOM : "is of"

    HOTEL ||--o{ EMPLOYEE : "works"

    EMPLOYEE ||--o{ EMPLOYEE : "leads (recursive)"



    TYPE {

        int Type_Id PK

        string Type_Name

    }



    HOTEL {

        int Hotel_Id PK

        string Hotel_name

        int Type_Id FK

    }



    CATEGORY {

        int Category_Id PK

        string Category_Name

        float Price

        int Beds_numbers

    }



    ROOM {

        int Room_Id PK

        int Floor

        int Hotel_Id FK

        int Category_Id FK

    }



    EMPLOYEE {

        int Employee_Id PK

        string Employee_Name

        string Employee_Speciality

        int Hotel_Id FK

        int Manager_Id FK

    }
