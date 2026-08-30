# Design review checklist

## Workflow integrity

- [ ] A draft can be resumed without creating duplicate reports.
- [ ] Required steps are visible before submission.
- [ ] Submitted reports are immutable through the normal user flow.
- [ ] Document generation reads the submitted snapshot rather than editable form state.

## Data and evidence

- [ ] Repeating workforce and service data are stored as child records.
- [ ] Attachment metadata is linked to the report without exposing a private URL.
- [ ] A failed save can be retried without silent data loss.

## Experience and release

- [ ] The workflow is usable in desktop and mobile layouts.
- [ ] Labels and validation messages are understandable without color alone.
- [ ] Test evidence and unresolved risks are reviewed before a release decision.
