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
  id2(Journey & behavour test changes)
  id3(Code & unit test changes)
  id4(Commit to branch)
  id5(Branch pipeline)
  id6(PR submited)
  id7(PR merged)
  
  id1 --- id2 --- id3 --- id4 --- id5 --- id6 --- id7
```

```mermaid
stateDiagram-v2
  s1 : Issue branch created
  s2 : Journey & behaviour test changes
  s3 : Issue branch pipeline
  s4 : Unit test & code changes
  s5 : Create or update PR
  s6 : Submit PR
  s7 : PR pipleine
  s8 : Merge PR
  
  [*] --> s1
  s1 --> s2
  s2 --> s3
  s3 --> s4 : Failed
  s4 --> s3
  s3 --> s5 : Passed
  s5 --> s6
  s6 --> s7
  s7 --> s5 : Failed
  s7 --> s8 : Passed
  s8 --> [*]
```
