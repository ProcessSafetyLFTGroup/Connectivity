# Chapter 1
```
@startuml
title Factory Line: Process Overview

' Stations in the production line
[Distributing Station] --> [Measuring Station 2.0] : Processed Materials
[Measuring Station 2.0] --> [Sorting Station] : Measured Data
[Sorting Station] --> [Packaging Station (LFT Handling Mechanism)] : Sorted Products
[Packaging Station (LFT Handling Mechanism)] --> [Storage Station] : Packaged Units

' Notes for each station
note right of [Distributing Station]
- Distributes raw materials.
- Components: Conveyors, sensors, actuators.
- Interfaces: Modbus, EtherCAT.
end note

note right of [Measuring Station 2.0]
- Measures size, weight, etc.
- Components: Measurement tools, PLCs.
- Interfaces: IO-Link, Modbus.
end note

note right of [Sorting Station]
- Sorts products by type/quality.
- Components: Sorting mechanisms, classification sensors.
- Interfaces: IO-Link, Modbus.
end note

note right of [Packaging Station (LFT Handling Mechanism)]
- Packages sorted products.
- Inputs: Sorted Products, Packaging Materials.
- Outputs: Packaged Units.
- Interfaces: SCADA, Ethernet.
end note

note right of [Storage Station]
- Stores finished packaged products.
- Components: Shelving, conveyor belts.
- Interfaces: Modbus, EtherCAT.
end note

@enduml
```
```
@startuml
title LFT Handling Mechanism: Station Overview

' Inputs and Outputs of the station
[Sorted Products] --> [Packaging Station] : Input
[Packaging Materials] --> [Packaging Station] : Input
[Packaging Station] --> [Packaged Units] : Output

' SCADA interaction
[Packaging Station] --> SCADA : Sends Operational Data
SCADA --> [Packaging Station] : Sends Commands

' Note for functionality
note right of [Packaging Station]
- Packages sorted products for storage/shipment.
- Inputs: 
  - Products from sorting station.
  - Packaging materials (e.g., boxes, labels).
- Outputs:
  - Packaged units ready for storage.
- Components: Sealing machines, labeling devices, sensors.
- Interfaces:
  - Sends data to SCADA for real-time monitoring.
  - Receives commands from SCADA.
end note

@enduml
```

# Overzicht van Inputs en Outputs

## Digitale Inputs (Ingangen)
| *Naam*                             | *Kleur*        | *Beschrijving*                              |
|--------------------------------------|------------------|----------------------------------------------|
| Werkstuk aan begin van de transportband | Grijs-roze (I0)  | Detecteert een werkstuk aan het begin van de transportband. |
| Werkstuk in het midden van de transportband | Rood-blauw (I1)  | Detecteert een werkstuk in het midden van de transportband. |
| Werkstuk aan het einde van de transportband | Wit-groen (I2)   | Detecteert een werkstuk aan het einde van de transportband. |
| Voedingscilinder in uitgangspositie  | Wit-geel (I4)    | Controleert of de voedingscilinder in de uitgangspositie staat. |
| Oprichtcilinder in uitgangspositie   | Bruin-geel (I5)  | Controleert of de oprichtcilinder in de uitgangspositie staat. |
| Vouwmechanisme in uitgangspositie    | Wit-grijs (I6)   | Controleert of het vouwmechanisme in de uitgangspositie staat. |
| Magazijn leeg                        | Grijs-bruin (I7) | Geeft aan dat het magazijn leeg is. |

---

## Digitale Outputs (Uitgangen)
| *Naam*                             | *Kleur*        | *Beschrijving*                              |
|--------------------------------------|------------------|----------------------------------------------|
| Transportband vooruit                | Wit (Q0)         | Start de transportband in de voorwaartse richting. |
| Transportband achteruit              | Bruin (Q1)       | Start de transportband in de achterwaartse richting. |
| Stopper inschuiven                   | Groen (Q2)       | Laat de stopper inschuiven.                  |
| Voedingscilinder uitschuiven         | Grijs (Q4)       | Laat de voedingscilinder uitschuiven.        |
| Oprichtcilinder uitschuiven          | Roze (Q5)        | Laat de oprichtcilinder uitschuiven.         |
| Arreteercilinder uitschuiven         | Blauw (Q6)       | Laat de arreteercilinder uitschuiven.        |
| Start vouwmechanisme                 | Rood (Q7)        | Start het vouwmechanisme.                    |

---

## Specificaties
| *Parameter*          | *Waarde*                 |
|------------------------|---------------------------|
| Aansluitingen          | 2 x 24-polige IEEE-488 stekker (SysLink) |
| Spanningsvereisten     | 24 V DC, maximaal 4,5 A  |
| Drukluchtverbruik      | 10 l/min bij 600 kPa      |
| Pneumatische aansluitingen | Kunststofslangen van 6 mm buitendiameter |

---

## Functies
- *Detectie*: Ingangen detecteren de aanwezigheid en positie van werkstukken en controleert de status van cilinders en mechanische onderdelen.
- *Besturing*: Uitgangen sturen actuatoren aan, zoals transportbanden, cilinders en vouwmechanismen.
- *Automatisering*: De station kan werkstukken volledig geautomatiseerd verpakken en transporteren.

## Toepassing
De inputs en outputs maken deel uit van het MPS-verpakkingsstation, ontworpen voor gebruik in een leeromgeving om vaardigheden in automatisering en mechatronica te oefenen.

---