# Factory Pipeline Patterns
<!-- TODO: Description of continuous engineering pipeline -->

```mermaid
flowchart LR
  id1(DEFINE)
  id2(BUILD)
  id3(PROMOTE)
  id4(MEASURE)
  id1 --> id2 --> id3 --> id4 --> id1
```

<!-- TOC -->
- [Issue pipeline](#issue-pipeline)
- [Build pipeline](#build-pipeline)
<!-- /TOC -->

## Issue pipeline
<!-- TODO: Description of issue pipeline -->

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

## Build pipeline
<!-- TODO: Description of build pipeline -->

```mermaid
flowchart LR
  id0(Pull issue)
  id1(Create branch)
  id2(Journey & behavour test changes)
  id3(Code & unit test changes)
  id4(Branch pipeline)
  id5(PR pipleline)
  id6(PR merged)
  
  id0 --> id1 --> id2 --> id3 --> id4 --> id5 --> id6
```

#### State diagram
```mermaid
stateDiagram-v2
  s0 : Pull issue
  s1 : Create issue branch
  s2 : Journey & behaviour test changes
  s3 : Trigger issue pipeline
  s4 : Unit test & code changes
  s9 : Commit to issue branch
  s5 : Create or update PR
  s6 : Submit PR
  s7 : Trigger PR pipleine
  s8 : Merge PR
  s10 : Remove issue branch
  
  [*] --> s0
  s0 --> s1
  s1 --> s2
  s2 --> s3
  s3 --> s4 : Failed
  s4 --> s9
  s9 --> s3
  s3 --> s5 : Passed
  s5 --> s6
  s6 --> s7
  s7 --> s5 : Failed
  s7 --> s8 : Passed
  s8 --> s10
  s10 --> [*]
```
