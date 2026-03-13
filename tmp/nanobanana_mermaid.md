
```mermaid
graph TD
    subgraph Logical_Address [Adreça lògica]
        direction LR
        VPN[VPN]
        PO[page offset]
        
        B_LA_20_12[20 bits : 12 bits]
    end

    PT_Reg[Registre de Taula de Pàgines]
    
    subgraph Table_Of_Pages [Taula de Pàgines]
        direction TB
        subgraph PT_H [Headers]
            H_VPN[VPN]
            H_P[P]
            H_D[D]
            H_PPN[PPN]
        end
        
        subgraph Row_0 [Row 0]
            R0_VPN[0]
            R0_P[ ]
            R0_D[ ]
            R0_PPN[ ]
        end

        subgraph Row_1 [Row 1]
            R1_VPN[1]
            R1_P[ ]
            R1_D[ ]
            R1_PPN[ ]
        end

        Ellipsis_Top[...]

        subgraph Row_H [Row High]
            direction LR
            R_H_Dot_P(( ))
            R_H_D[ ]
            R_H_Dot_PPN(( ))
        end

        Ellipsis_Bottom[...]

        subgraph Row_Max [Row 2²⁰-1]
            RM_VPN[2²⁰-1]
            RM_P[ ]
            RM_D[ ]
            RM_PPN[ ]
        end
    end

    Bit_P_Note[Bit de presència (P). Si és 0<br>la pàgina està al disc. Si és<br>1 està a la memòria]

    subgraph Physical_Address [Adreça física]
        direction LR
        PPN[PPN]
        PO_Phys[page offset]
        
        B_PA_2_12[2 bits : 12 bits]
    end

    %% Connections
    VPN -->|index| Row_H
    PT_Reg --> Table_Of_Pages
    
    Row_H -.->|check P bit| R_H_Dot_P
    R_H_Dot_P --> Bit_P_Note
    
    Row_H -.->|extract PPN| R_H_Dot_PPN
    R_H_Dot_PPN --> PPN
    
    PO --> PO_Phys
```
