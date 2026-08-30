# Test scenarios

| ID | Scenario | Expected result |
|---|---|---|
| `TC-01` | Start a new report and save a draft | A draft receives a system-generated identifier. |
| `TC-02` | Resume and update a draft | Previous values are restored without creating a duplicate. |
| `TC-03` | Add workforce and service entries | Child records remain linked to the parent report. |
| `TC-04` | Attach supporting evidence | Attachment metadata is visible before submission. |
| `TC-05` | Submit a complete report | State changes to `submitted` and fields become read-only. |
| `TC-06` | Generate a printable snapshot | Output represents the approved report state. |
| `TN-01` | Submit with incomplete required steps | Submission is blocked with a clear message. |
| `TN-02` | Attempt to edit a submitted report | Editing is blocked and the report remains unchanged. |
| `TN-03` | Lose connectivity while saving a draft | The user sees a recoverable error and can retry safely. |
