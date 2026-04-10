# Swimlane Activity Diagram

Shows workflow partitioned by roles or services using vertical swimlanes.

## Key Elements

- **Swimlane**: `|Lane Name|` — vertical partition by role/service
- **Colored lane**: `|#color|Lane Name|` — lane with background color
- **All activity elements** from Activity Diagram apply inside lanes
- Activities after a `|Lane|` marker belong to that lane until the next marker

## Swimlane Syntax

| Syntax | Description |
|---|---|
| `\|Lane\|` | Define or switch to a lane |
| `\|#f5f5f5\|Lane\|` | Lane with background color |
| Multiple `\|Lane\|` markers | Activities flow across lanes |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Swimlane background | `#f5f5f5` (light gray) | Default lane fill |
| Start activity | `#d5e8d4` (light green) | Input/receive actions |
| Process activity | `#dae8fc` (light blue) | Processing steps |
| Decision | `#fff2cc` (light yellow) | Branch points |
| Error/Cancel | `#f8cecc` (light red) | Error handling |
| Output | `#e1d5e7` (light purple) | Results/output |

## Example 1

Employee onboarding across HR, IT, Manager, and New Employee lanes:

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
skinparam swimlane {
  BorderColor #999999
  TitleBackgroundColor #f5f5f5
  TitleFontSize 14
}

|#f5f5f5|HR|
start
#d5e8d4:Receive Signed Offer;
:Create Employee Record;
:Send Welcome Email;

fork
  |#f5f5f5|IT|
  :Provision Laptop;
  :Create Email Account;
  :Grant System Access;
fork again
  |#f5f5f5|HR|
  :Prepare Onboarding Kit;
  :Schedule Orientation;
end fork

|#f5f5f5|New Employee|
#d5e8d4:Complete Tax & Benefits Forms;
:Upload ID Documents;

|#f5f5f5|HR|
:Verify Documents;
if (Documents Valid?) then (yes)
  :Finalize Enrollment;
else (no)
  #f8cecc:Request Corrections;
  |#f5f5f5|New Employee|
  #f8cecc:Resubmit Documents;
  |#f5f5f5|HR|
  :Verify Documents;
endif

|#f5f5f5|Manager|
:Assign Mentor;
:Set 30/60/90 Day Goals;
:Schedule 1-on-1 Meetings;

|#f5f5f5|New Employee|
:Attend Orientation;
:Complete Training Modules;

|#f5f5f5|Manager|
if (Probation Review OK?) then (yes)
  #d5e8d4:Confirm Employment;
  |#f5f5f5|HR|
  #e1d5e7:Update Status to Permanent;
else (no)
  #f8cecc:Extend Probation;
endif

stop
@enduml
```
