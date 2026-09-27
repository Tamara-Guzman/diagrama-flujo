flowchart TD
    classDef okNode fill:#90EE90,stroke:#228B22,stroke-width:3px
    classDef advertencia fill:#FF6347,stroke:#8B0000,stroke-width:3px

    A([Usuario abre la aplicación]) --> B[Capturar hora de entrada y coordenadas]
    B --> C{¿Hora es antes de las 08:00?}
    C -->|No| E([Advertencia: Hora de ingreso tardía])
    C -->|Sí| D{¿Está dentro de 50m del área de trabajo?}
    D -->|No| G([Advertencia: Fuera del área autorizada])
    D -->|Sí| H{¿El usuario está registrado?}
    H -->|No| I([Advertencia: Usuario no registrado])
    H -->|Sí| J[Registrar hora en app y en base de datos]
    J --> F([OK: Registro validado])
    E:::advertencia --> Z([Fin])
    G:::advertencia --> Z
    I:::advertencia --> Z
    F:::okNode --> Z
