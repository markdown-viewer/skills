# Interaction Overview Diagram

Combines activity diagram control flow with sequence diagram interaction fragments.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Start node | `start` | Initial node (filled circle) |
| End node | `stop` | Final node |
| Decision | `if/else/endif` | Branch point (diamond) |
| Fork/Join | `fork/fork again/end fork` | Parallel execution |
| Group | `group Label ... end group` | Frame container for grouping steps |
| Partition | `partition #color "Label" { }` | Colored partition container |
| Guard condition | `if (condition)` | Condition on branch |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Interaction frame | `#dae8fc` (light blue) | Sequence fragments |
| Reference frame | `#d5e8d4` (light green) | Referenced interactions |
| Decision | `#fff2cc` (light yellow) | Branch points |
| Error path | `#f8cecc` (light red) | Error handling flows |
| Final result | `#e1d5e7` (light purple) | Output/result |

## Example 1

Library system interaction overview with mixed activity and sequence flows:

```plantuml
@startuml
skinparam activity {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
  DiamondBackgroundColor #fff2cc
  DiamondBorderColor #d6b656
}

start

:User opens library system;

group Authentication
  :Login Sequence;
  note right
    ref: See Authentication
    sequence diagram
  end note
end group

if (Authenticated?) then (yes)
  fork
    partition #dae8fc "Search Books" {
      :User searches catalog;
      :System returns results;
      :User selects book;
    }
  fork again
    partition #dae8fc "Check Account" {
      :System checks borrowing limit;
      :System verifies no overdue books;
    }
  end fork

  if (Book available?) then (yes)
    partition #d5e8d4 "Borrow Book" {
      :User requests borrow;
      :System creates loan record;
      :System updates inventory;
      #e1d5e7:Return due date confirmation;
    }
  else (no)
    partition #fff2cc "Reserve Book" {
      :User places reservation;
      :System queues request;
      #e1d5e7:Return reservation confirmation;
    }
  endif
else (no)
  #f8cecc:Show login error;
endif

stop
@enduml
```
