# Factory Pipeline Patterns

```mermaid
flowchart LR
  id1(DEFINE)
  id2(BUILD)
  id3(PROMOTE)
  id4(MEASURE)
  id1 --> id2 --> id3 --> id4 --> id1
  id1 & id2 & id3 -.-> id4
```

<!-- TOC -->
- [Issue pipeline](#issue-pipeline)
- [Engineering pipeline](#engineering-pipeline)
<!-- /TOC -->

## Issue pipeline
<!-- TODO: Desc - Issue pipeline -->

```mermaid
flowchart LR
  id1(Triage)
  id2(Review)
  id3(Ready)
  id4(Build)
  id5(PR)
  id6(Merged)
  id7(Promoted)
  id1 --- id2 --- id3 --- id4 --- id5 --- id6 --- id7
```

## Engineering pipeline
<!-- TODO: Desc - Engineering pipeline -->

```mermaid
flowchart LR
  id1(Create branch)
  id2(Create journey & behavour tests)
  id3(TDD)
  id4(Commit to branch)
  id5(Branch pipeline)
  id6(PR submited)
  id7(PR merged)
  id1 --- id2 --- id3 --- id4 --- id5 --- id6 --- id7
```
