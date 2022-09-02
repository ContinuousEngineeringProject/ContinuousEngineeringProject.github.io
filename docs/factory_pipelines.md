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
- [Issue states](#issue-states)
- [Build pipeline](#build-pipeline)
- [Issue branch pipeline](#issue-branch-pipeline)
- [PR pipeline](#pr-pipeline)
- [Publish pipeline](#publish-pipeline)
<!-- /TOC -->

## Issue states
<!-- TODO: Description of issue states -->

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
  id1(Pull issue)
  id2(Journey & behavour test changes)
  id3(Code & unit test changes)
  id4(Issue branch pipeline)
  id5(PR pipleline)
  id6(PR merged)
  id7(Publish pipeline)
  
  id1 --> id2 --> id3 --> id4 --> id5 --> id6
```

#### State diagram
```mermaid
stateDiagram-v2
  s0 : Set issue state to Build
  s1 : Create issue branch
  s2 : Journey & behaviour test changes
  s3 : Trigger issue branch pipeline
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
  s8 --> s12 : Completed
  s12 --> s10
  s10 --> [*]
```

### Issue branch pipeline
<!-- TODO: Description of issue branch pipeline -->

```mermaid
flowchart LR
  id1(Unit tests)
  id2(Static code analysis)
  id3(Build binaries)
  id4(Issue behaviour verification)
  
  id1 --> id2 --> id3 --> id4
```

#### State diagram
```mermaid
stateDiagram-v2
  s1 : Unit tests
  s2 : Linting
  s3 : Code coverage
  s4 : Build binaries
  s5 : Issue behaviour test suite
  
  state f1 <<fork>>
  state j1 <<join>>
  
  [*] --> s1
  s1 --> f1
  f1 --> s2
  f1 --> s3
  s2 --> j1
  s3 --> j1
  j1 --> s4
  s4 --> s5
  s5 --> [*]
```

### PR pipeline
<!-- TODO: Description of PR pipeline -->

```mermaid
flowchart LR
  id1(Unit tests)
  id2(Static code analysis)
  id3(Build binaries)
  id4(Issue behaviour verification)
  id4(Journey verification)
  
  id1 --> id2 --> id3 --> id4
```

#### State diagram
```mermaid
stateDiagram-v2
  s0 : Unit tests
  s1 : Linting
  s2 : Code coverage
  s3 : SAST
  s4 : Build binaries
  s5 : Issue behaviour test suite
  s6 : Journey step behaviour test suite
  s7 : Issue journey test suite
  s8 : Journey test suite
  
  state f1 <<fork>>
  state j1 <<join>>
  state f2 <<fork>>
  state j2 <<join>>
  state f3 <<fork>>
  state j3 <<join>>
  
  [*] --> s0
  s0 --> f1
  f1 --> s1
  f1 --> s2
  f1 --> s3
  s1 --> j1
  s2 --> j1
  s3 --> j1
  j1 --> s4
  s4 --> f2
  f2 --> s5
  f2 --> s6
  s5 --> j2
  s6 --> j2
  j2 --> f3
  f3 --> s7
  f3 --> s8
  s7 --> j3
  s8 --> j3
  j3 --> [*]
```

### Publish pipeline
<!-- TODO: Description of issue branch pipeline -->
