# Activity Diagram

Shows workflow with activities, decisions, loops, and parallel processing.

## Key Elements

- **Start**: `start` — solid black circle
- **Stop**: `stop` — bullseye circle
- **End**: `end` — circle with X (terminates flow only)
- **Activity**: `:action;` — rounded rectangle
- **Decision**: `if (condition) then (yes) ... else (no) ... endif`
- **Switch**: `switch (var) ... case (val) ... endswitch`
- **Fork/Join**: `fork ... fork again ... end fork`
- **While loop**: `while (condition) ... endwhile`
- **Repeat loop**: `repeat ... repeat while (condition)`

## Edge Styles

| Type | Syntax | Description |
|---|---|---|
| Control flow | `->` (implicit) | Default solid arrow |
| Labeled flow | `->[label]` | Arrow with guard label |
| Colored arrow | `-[#color]->` | Arrow with custom color |
| Detach | `detach` | Terminate a branch |
| Kill | `kill` | Force stop a branch |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Start activity | `#d5e8d4` (light green) | Input/receive actions |
| Process activity | `#dae8fc` (light blue) | Processing steps |
| Decision | `#fff2cc` (light yellow) | Branch points |
| Error/Cancel | `#f8cecc` (light red) | Error handling |
| Output | `#e1d5e7` (light purple) | Results/output |

## Example 1

CI/CD pipeline with decisions, loops, and parallel stages:

```plantuml
@startuml
skinparam activity {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  ArrowColor #333333
  FontName Arial
  DiamondBackgroundColor #fff2cc
  DiamondBorderColor #d6b656
}

start
#d5e8d4:Developer pushes code;

:Run Linter & Static Analysis;
if (Lint OK?) then (yes)
  :Compile Project;
else (no)
  #f8cecc:Notify: Fix lint errors;
  stop
endif

:Run Unit Tests;
if (Tests Pass?) then (yes)
  :Build Docker Image;
else (no)
  #f8cecc:Notify: Tests failed;
  stop
endif

fork
  :Security Scan;
fork again
  :Integration Tests;
fork again
  :Performance Tests;
end fork

if (All checks pass?) then (yes)
  :Deploy to Staging;

  repeat
    :Run Smoke Tests;
    if (Smoke OK?) then (yes)
      -[#green]->
      break
    else (no)
      :Retry deploy;
    endif
  repeat while (Retries < 3?) is (yes) not (no)

  :Await Manual Approval;
  if (Approved?) then (yes)
    #d5e8d4:Deploy to Production;
    #e1d5e7:Send Release Notification;
  else (no)
    #f8cecc:Rollback Staging;
  endif
else (no)
  #f8cecc:Block deploy pipeline;
endif

stop
@enduml
```
