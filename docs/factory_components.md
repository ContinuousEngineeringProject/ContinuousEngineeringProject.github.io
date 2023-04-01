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

### Target Tooling Architecture

```mermaid
flowchart LR
  subgraph grp1 [PIPELINE ENGINE]
    id0(GitHub Actions)
    id1(Jenkins X)
  end
  subgraph grp2 [SOURCE REPOSITORY]
    id2(GitHub Repository)
  end
  subgraph grp3 [BINARY REPOSITORY]
    id3(GitHub Packages)
  end
  subgraph grp4 [IM]
    id4(Slack)
  end
  subgraph grp5 [CODE QUALITY]
    id5(Sonar Cloud)
    id10(Hound)
    id11(Semantic Pull Requests)
    id12(DCO)
    id13(dependabot)
    id14(guide bot)
    id15(sonatype lift)
  end
  subgraph grp6 [BACKLOG MANAGEMENT]
  direction TB
    id6(GitHub Issues)
    id9(GitHub Projects)
    
    id9 --- id6
  end
  subgraph grp7 [INFRASTRUCTURE]
    id7(GCP)
  end
  subgraph grp8 [MONITORING]
    id8(Grafana)
    id16(jx Dashboard)
    id17(Lighthouse UI)
  end
  
  id6 --- id2 & id4
  id2 --- id1 & id4 & id0
  id3 --- id1
  id1 --- id4 & grp5 & grp7
  id0 --- grp5
  
  id4 -.- grp8
  id1 -.- grp8
  grp7 -.- grp8
  
```

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

| Tooling | Intergration | SCA | Unit Testing | Behaviour Testing | Secutiry Testing |
| --- | --- | --- | --- | --- | --- |
| Sonar Cloud | Actions | X |  |  |  |
| Hound | Actions | X |  |  |  |
| Semantic Pull Requests | Actions | X |  |  |  |
| DCO | Actions | X |  |  |  |
| dependabot | Actions |  |  |  | X |
| guide bot | Actions | X |  |  |  |
| sonatype lift | Actions | X |  |  |  |
|  |  |  |  |  |  |

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

