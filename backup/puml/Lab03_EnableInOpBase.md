@startuml

[*] --> Idle
Idle --> Init : Enable①
note left of Idle
    InOperation := FALSE
    Error := FALSE
end note

Init --> Idle : Enable⓪
Init --> Error : SetError
Init --> InOp

note right of Init
    InOperation := FALSE
    Error := FALSE
end note

InOp --> Idle : Enable⓪
InOp --> Error : SetError
note right of InOp
    InOperation := TRUE
    Error := FALSE
end note

Error --> Idle : Enable⓪
note left of Error
    InOperation := FALSE
    Error := TRUE
end note


@enduml


```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Init : Enable①
    note left of Idle
        InOperation := FALSE
        Error := FALSE
    end note

    Init --> Idle : Enable⓪
    Init --> Error : SetError
    Init --> InOp
    note right of Init
        InOperation := FALSE
        Error := FALSE
    end note

    InOp --> Idle : Enable⓪
    InOp --> Error : SetError
    note right of InOp
        InOperation := TRUE
        Error := FALSE
    end note

    Error --> Idle : Enable⓪
    note left of Error
        InOperation := FALSE
        Error := TRUE
    end note
```

```mermaid
stateDiagram-v2
    [*] --> Idle
        
    Idle --> Init : Enable①

    Init --> Idle : Enable⓪
    Init --> Error : SetError
    Init --> InOp
        
    InOp --> Idle : Enable⓪
    InOp --> Error : SetError
        
    Error --> Idle : Enable⓪
    

    note left of Idle
        InOperation := FALSE
        Error := FALSE
    end note

    note left of Init
        InOperation := FALSE
        Error := FALSE
    end note

    note right of InOp
        InOperation := TRUE
        Error := FALSE
    end note
 
    note left of Error
        InOperation := FALSE
        Error := TRUE
    end note
```


