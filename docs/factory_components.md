# Factory Components
<!-- TODO: Description of factory components -->

```mermaid
flowchart LR
  id1(PIPELINE ENGINE)
  id2(SOURCE REPOSITORY)
  id3(BINARY REPOSITORY)
  id4[[IM]]
  id5(CODE QUALITY)
  id6[[BACKLOG MANAGEMENT]]
  id7(INFRASTRUCTURE)
  id8[[MONITORING]]
  
  id6 --- id2 & id4
  id2 --- id1 & id4
  id3 --- id1
  id1 --- id4 & id5 & id7
  
  id4 -.- id8
  id1 -.- id8
  id7 -.- id8
  
```


## Tooling Roadmap
<!-- TODO: Description of the tooling roadmap -->


 <!--
```mermaid
flowchart LR
  id0(GitHub Actions)
  id1(Jenkins X)
  id2(GitHub Repository)
  id3(GitHub Packages)
  id4(Slack)
  id5(CODE QUALITY)
  id6(GitHub Issues)
  id7(INFRASTRUCTURE)
  id8[[MONITORING]]
  
  id6 --- id2 & id4
  id2 --- id1 & id4 & id0
  id3 --- id1
  id1 --- id4 & id5 & id7
  id0 --- id5
  
  id4 -.- id8
  id1 -.- id8
  id7 -.- id8
  
```
-->

### Ready 

| [Pipeline Engine](#pipeline-engine) | [Source Repository](#source-repository) | [Binary Repository](#binary-repository) | [IM](#im) | [Code Quality](#code-quality) | [Backlog Management](#backlog-management) | [Infrastructure](#infrastructure) | [Monitoring](#monitoring) |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

### Comming Soon

| [Pipeline Engine](#pipeline-engine) | [Source Repository](#source-repository) | [Binary Repository](#binary-repository) | [IM](#im) | [Code Quality](#code-quality) | [Backlog Management](#backlog-management) | [Infrastructure](#infrastructure) | [Monitoring](#monitoring) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Jenkins X | GitHub Repository | GitHub Packages | Slack | Sonar Cloud | GitHub Issues | GCP | Grafana |
| GitHub Actions |  |  |  | Hound | GitHub Projects |  | jx Dashboard |
|  |  |  |  | Semantic Pull Requests |  |  | Lighthouse UI |
|  |  |  |  | DCO |  |  |  |
|  |  |  |  | dependabot |  |  |  |
|  |  |  |  | guide bot |  |  |  |
|  |  |  |  | sonatype lift |  |  |  |
|  |  |  |  |  |  |  |  |


### Under Review

| [Pipeline Engine](#pipeline-engine) | [Source Repository](#source-repository) | [Binary Repository](#binary-repository) | [IM](#im) | [Code Quality](#code-quality) | [Backlog Management](#backlog-management) | [Infrastructure](#infrastructure) | [Monitoring](#monitoring) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Terraform Cloud |  |  |  |  |  | Azure | Octant |
|  |  |  |  |  |  | AWS | Lens |
|  |  |  |  |  |  |  |  |

---


## Components Overivew

### Pipeline Engine
<!-- TODO: add description of Pipeline Engine component 


```mermaid
flowchart LR
  id0(GitHub Actions)
  id1(Jenkins X)
  id2(GitHub Repository)
  id3(BINARY REPOSITORY)
  id4(IM)
  id5(CODE QUALITY)
  id7(INFRASTRUCTURE)
  id8(MONITORING)
  
  id2 --- id1 & id4 & id0
  id3 --- id1
  id0 --- id5
  id1 --- id4 & id5 & id7
  
  id4 --- id8
  id1 --- id8
  id7 --- id8
  
```
-->

#### Jenkins X
<!-- TODO: add Jenkins X configuraion -->
- jx-pipelines-visualizer
- jxgh/cd-indicators
- jx-slack
- lighthouse-webui-plugin
- jx-observability

#### GitHub Actions
<!-- TODO: add GitHub Actions configuraion -->
- dependabot
- dco
- semantic
- sonarsource/sonarcloud-github-action
- actions/stale@v3

---

### Source Repository
<!-- TODO: add description of Source Repository component -->

#### GitHub Repository
<!-- TODO: add GitHub Repository configuraion -->

---

### Binary Repository
<!-- TODO: add description of Binary Repository component -->

---

### IM
<!-- TODO: add description of IM component -->

---

### Code Quality
<!-- TODO: add description of Code Quality component -->

#### Review
<!-- TODO: add Review configuraion -->

#### SCA
<!-- TODO: add SCA configuraion -->

#### Secutiry Testing
<!-- TODO: add Secutiry Testing configuraion -->

#### Unit Testing
<!-- TODO: add Unit Testing configuraion -->

#### Behaviour Testing
<!-- TODO: add Behaviour Testing configuraion -->

---

### Backlog Management
<!-- TODO: add description of Backlog Management component -->

---

### Infrastructure
<!-- TODO: add description of Infrastructure component -->

---

### Monitoring
<!-- TODO: add description of Monitoring component -->

#### Grafana
<!-- TODO: add Grafana configuraion -->
- Promtail
- Loki
- Tempo
- Prometheus

---

