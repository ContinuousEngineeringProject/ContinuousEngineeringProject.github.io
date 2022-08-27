# Factory Pipeline Patterns

```mermaid
flowchart TD
  id1(DEFINE) --> id2(BUILD)
  id2 --> id3(PROMOTE)
  id3 --> id4(MEASURE)
  id4 --> id1
  id1 -.-> id4
  id2 -.-> id4
  id3 -.-> id4
```

<!-- TOC -->
- [Issue pipeline](#issue-pipeline)
- [Engineering pipeline](#engineering-pipeline)
<!-- /TOC -->

## Issue pipeline
<!-- TODO: Desc - Issue pipeline -->

```mermaid
flowchart LR
  id1(Triage) --> id2(Review)
  id2 --> id3(Ready)
  id3 --> id4(Build)
  id4 --> id5(PR)
  id5 --> id6(Merged)
  id6 --> id7(Promoted)
```

## Engineering pipeline
<!-- TODO: Desc - Engineering pipeline -->

```mermaid
flowchart LR

```
