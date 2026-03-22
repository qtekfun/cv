# Cipriano Moreno

**Engineering Lead · DevOps · Systems**
`cmorenomateos@gmail.com` · `github.com/qtekfun` · `qtekfun.com` · `Spain`

---

## Technical Skills

| Category           | Technologies                                                                   |
|--------------------|--------------------------------------------------------------------------------|
| Languages          | C++23, Python, Ada95, Bash, PHP, JavaScript, Java, LabVIEW, Visual Basic      |
| Infrastructure     | Kubernetes, Docker, AWS EC2, Proxmox, Ansible, Terraform                       |
| CI/CD              | Jenkins (Shared Libraries/Groovy), GitHub Actions, Spinnaker, SonarQube        |
| Networking & Sec   | Traefik, WireGuard, Tailscale, Istio, mTLS, VPN                                |
| Observability      | Prometheus, Grafana, Kibana, Splunk                                             |
| Protocols          | Kafka, HTTP/2, Diameter, Wireshark/pcap                                         |
| Databases          | SQL, PostgreSQL                                                                 |
| Methodologies      | Scrum, Kanban, Shift-Left, GitOps, DevEx                                        |
| Management         | Engineering Management, Roadmapping, Mentoring, Stakeholder Management         |

---

## Experience

### Team Lead Software & Engineering Services · Jungheinrich Digital Solutions Spain
`Feb 2026 – Present · Madrid, Spain`

- Direct management of a 24-engineer multidisciplinary department across Legacy (C++/Python), Web (PHP/JS), and critical systems (PLM/ALM) stacks.
- Scaled Agile methodologies (Scrum/Kanban): ceremonies, estimation sessions, and capacity planning.
- Technical and operational coordination with headquarters in **Germany and Austria**.
- Focus on Time-to-Market reduction and embedding DevOps culture across the full SDLC.
- Career path definition and technical mentoring across the team.

### Product Development Team Lead & DevOps Ambassador · Jungheinrich Digital Solutions Spain
`Jun 2024 – Feb 2026 (1 year 9 months) · Madrid, Spain`

- Cross-functional technical leadership across C++, Python, PHP, and JS profiles.
- Designed and implemented the **global DevOps strategy**: full VCS migration to GitHub.
- CI/CD pipeline optimisation with a **Shift-Left** approach (pre-merge validation), significantly reducing production defects.
- Led **GenAI/Prompt Engineering** adoption for full-stack development of an internal pipeline orchestration tool (Python/JS), drastically cutting deployment and validation times.

### DevOps Lead · Jungheinrich Digital Solutions Spain
`Jan 2023 – Jun 2024 (1 year 6 months) · Madrid, Spain`

- Automated build and deployment nodes on **Windows** environments using Ansible.
- Managed **AWS EC2** instances for toolchain update orchestration.
- Redesigned **Jenkins** architecture using Shared Libraries (Groovy) with integrated static analysis and vulnerability scanning.
- Supported C++ package management migration and CMake toolchain updates on Windows.

### IT Manager (Part-Time Consultancy) · TESTAMENTARIA SL
`Dec 2022 – Present · Madrid, Spain`

- Technology strategy and Digital Workplace modernisation.
- Designed and deployed corporate VPN with **Tailscale**. NAS backup management and health monitoring.
- Python/Bash automation: migration of 25,000+ contacts to Google Workspace.
- IT Procurement: hardware lifecycle management and asset acquisition.

### R&D Microservices SW Engineer · 5G Core · Ericsson (via Blue Telecom)
`Apr 2021 – Jan 2023 (1 year 10 months) · Madrid, Spain`

- Development and maintenance of **two mission-critical microservices** for Ericsson's 5G Core in C++17.
- Inter-service communication via **Kafka, HTTP, HTTP/2, and Diameter**.
- Deployment on **Kubernetes** clusters with Istio (Service Mesh) and mTLS.
- Network troubleshooting with Wireshark (pcap). Monitoring with Prometheus, Grafana, and Kibana.
- CI/CD pipelines in **Jenkins + SonarQube** and deployment via **Spinnaker**. Scrum + Gerrit.

### Senior Software Engineer · Airbus Defence and Space (via CT Ingenieros)
`Oct 2018 – Apr 2021 (2 years 7 months) · Madrid, Spain`

- Development of the **Flight Mission Planning System** in C++14 / SQL on Windows.
- Responsible for the **Windows 10 migration** of a video player synchronised with aircraft routes, maintaining strict legacy compatibility.
- On-site deployment at operational units. Technical documentation under **ISO 9001 and ISO 9100**.

### Senior Software Engineer · Indra
`Oct 2016 – Oct 2018 (2 years 1 month) · Madrid, Spain`

- Development of Indra's **Air Traffic Management (ATM)** system for the DFS client (Germany).
- Technical lead of a 3-person team. SQL / PostgreSQL data model design and internal API development.
- C++ and Ada95 backend on Linux. Automated tagging scripts for IBM Clearcase.

### Software Developer · Airbus Defence and Space (via Orbital Critical Systems)
`Nov 2015 – Oct 2016 (1 year) · Madrid, Spain`

- Development of **certified embedded Fly-By-Wire software** for the Casa C295 aircraft (project FT4B).
- Flight computer programming (ailerons, VTP, HTP) in **Ada95 / GNAT on VxWorks RTOS** (16 ms execution cycle).
- Internal Python tool to automate SEAS test result validation with signal graph generation.

### Software Developer · Indra Group (via Panel Sistemas Informáticos)
`Oct 2014 – Nov 2015 (1 year 2 months) · Madrid, Spain`

- Internal data access API for the ATM system. SQL / PostgreSQL data model design.
- C++ and Ada95 backend on Linux. Unit testing.

### Software Developer & Technical Sales Engineer · Ala2 Ingenieros S.L.
`Oct 2011 – Oct 2014 (3 years 1 month) · Madrid, Spain`

- Custom software development for the aeronautical sector (C++, LabVIEW, VB, Java).
- Project leadership with MS Project planning. Full technical sales cycle management and client training.
- Technical documentation under ISO 9001 and ISO 9100.

---

## Projects / Homelab

### `homelab-2026` — Self-hosted Infrastructure Stack
`github.com/qtekfun · qtekfun.com`

Docker stack of ~35 services on Proxmox + Ubuntu VM, managed as a mono-repo with a custom CI/CD pipeline.

| Layer                 | Services                                                                          |
|-----------------------|-----------------------------------------------------------------------------------|
| Reverse proxy & Auth  | Traefik, Authelia (SSO/2FA), CrowdSec (IDS/IPS)                                  |
| Remote access         | WireGuard (`10.13.13.0/24`), Tailscale                                            |
| Storage               | Nextcloud (×2), Immich, CouchDB (Obsidian LiveSync)                               |
| Automation            | n8n, Guacamole, Portainer                                                         |
| Observability         | Grafana, Prometheus, Splunk (HEC + Traefik JSON logs + CrowdSec + Proxmox syslog)|
| DNS & Connectivity    | ddclient (DDNS), Cloudflare (no proxy — Nextcloud large file compatibility)       |
| CI/CD & Versioning    | Forgejo, Renovate (`datasource=docker`), pre-commit hooks                         |

**Engineering highlights:**

- **Image hardening:** `cap_drop: ALL` with selective `cap_add`, s6-overlay compatibility analysis, custom healthchecks for Portainer and Obsidian.
- **Version-pinning:** `renovate: datasource=docker` annotations on every image; automatic update PRs.
- **GitOps:** branch protection on `master`, atomic commits per service, pre-commit hooks for `docker-compose` validation.
- **Security perimeter:** Authelia middleware audit — identified and remediated exposed services without SSO (n8n, Grafana, Kasm).
- **Observability pipeline:** Splunk ingestion from CrowdSec via HEC, Traefik JSON logs, Proxmox syslog, and FritzBox syslog.

### Privacy & Mobile Infrastructure

- **GrapheneOS** on Pixel 10 Pro Fold — full mobile environment installation and hardening.
- **Gadgetbridge** integrated with Garmin Fenix 7S Pro Solar (no proprietary app or telemetry).
- Brave Flatpak with custom NSS store (`~/.var/app/com.brave.Browser/.pki/nssdb`).

---

## Education

### Diploma in Aeronautical Engineering · Universidad Politécnica de Madrid
`2008 – 2012`

### Bachelor's Degree in Computer Science · UNED
`2012`

### Additional Training

| Course / Certification                    | Institution                    | Year |
|-------------------------------------------|--------------------------------|------|
| GitOps Fundamentals                       | Codefresh / CNCF               |      |
| Kubernetes: Beginner to Expert            | Udemy                          | 2020 |
| Docker: Beginner to Expert                | Udemy                          | 2020 |
| Cloud Computing Course                    | Escuela de Organización Ind.   | 2014 |
| EF SET English Certificate 81/100 (C2)   | EF Education First             |      |
| Introduction to Cybersecurity             | Cisco Networking Academy       |      |

---

**Languages:** Spanish (native) · English (C2 — bilingual)

*Generated from [`cv.md`](https://github.com/qtekfun/cv) · last updated: \today*
