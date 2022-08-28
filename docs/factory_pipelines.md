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
- [Issue state pipeline](#issue-state-pipeline)
- [Build pipeline](#build-pipeline)
- [Issue branch pipeline](#issue-branch-pipeline)
<!-- /TOC -->

## Issue state pipeline
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
  s0 : Set issue state to Build
  s1 : Create issue branch
  s2 : Journey & behaviour test changes
  s3 : Trigger issue pipeline
  s4 : Unit test & code changes
  s9 : Commit to issue branch
  s11 : Set issue state to PR
  s5 : Create or update PR
  s6 : Submit PR
  s7 : Trigger PR pipleine
  s8 : Merge PR
  s10 : Remove issue branch
  s12 : Set issue state to Merged
  
  [*] --> s0
  s0 --> s1
  s1 --> s2
  s2 --> s3
  s3 --> s4 : Failed
  s4 --> s9
  s9 --> s3
  s3 --> s11 : Passed
  s11 --> s5
  s5 --> s6
  s6 --> s7
  s7 --> s5 : Failed
  s7 --> s8 : Passed
  s8 --> s5 : Failed
  s8 --> s10 : Completed
  s10 --> s12
  s12 --> [*]
```

### Issue branch pipeline
<!-- TODO: Description of issue branch pipeline -->

```mermaid
flowchart LR
  id0(Commit to branch)
  id1(Run unit tests)
  id2(Verify issue unit test coverage)
  id3(Run issue behaviour tests)
  
  id0 --> id1 --> id2 --> id3
```
