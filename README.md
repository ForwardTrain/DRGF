# DRGF Database System
[![Website](https://img.shields.io/badge/website-drgf--wmu.org-blue)](https://www.drgf-wmu.org)
[![Vue](https://img.shields.io/badge/Vue-3.2-green)](https://vuejs.org/)
[![Element
Plus](https://img.shields.io/badge/Element%20Plus-2.2-409EFF)](https://element-plus.org/)
[![Spring](https://img.shields.io/badge/Spring-4.2.5-brightgreen)](https://spring.io/)
[![Java](https://img.shields.io/badge/Java-1.8-orange)](https://www.oracle.com/java/)

DRGF (Database Resource of Growth Factors) is an online platform that integrates manually curated and validated cell growth factor-related data, drug-target information, clinical trial records, and literature. It provides browsing, search, visualization, and literature retrieval capabilities for researchers.

Online access: **https://www.drgf-wmu.org**

This project adopts a separated front-end and back-end architecture consisting of two sub-projects:

-   **Front-end**: A single-page application (SPA) built with Vue 3, providing interfaces for growth factor data browsing, searching, statistical visualization, and administrative management.
-   **Back-end**: A Maven multi-module Java Web application (WAR package) based on Spring 4, providing data services and business logic support.

## Project Structure 

    DRGF/
    ├── DRGF-Web/          # Front-end (Vue 3)
    │   ├── package.json     # Dependencies and scripts
    │   ├── vue.config.js    # Build and proxy configuration
    │   ├── public/          # Static resources
    │   └── src/             # Source code
    └── DRGF-Java/           # Back-end (Maven multi-module)
        ├── pom.xml          # Parent POM
        ├── web/             # Web layer
        ├── service/         # Business logic layer
        ├── model/           # Domain model layer
        ├── dao/             # Data access layer (MyBatis)
        └── common/          # Common utilities and configuration

## Technology Stack
### Front-end (DRGF-Web)

| Category             | Technology                              |
| -------------------- | --------------------------------------- |
| Framework            | Vue 3.2 + Vue Router 4 + Vuex 4         |
| UI Component Library | Element Plus 2.2, Vant 4                |
| Visualization        | ECharts 4.9, ECharts GL, World Map      |
| HTTP                 | Axios                                   |
| Rich Text            | @vueup/vue-quill                        |
| Others               | qiniu-js, qrcode.vue                    |
| Build                | Vue CLI 5, Babel, Sass                  |

### Back-end (DRGF-Java)

| Category                 | Technology                                                                              |
| ------------------------ | --------------------------------------------------------------------------------------- |
| Framework                | Spring 4.2.5, Spring MVC, Spring Security                                               |
| ORM                      | MyBatis 3.3.1 + MyBatis-Spring                                                          |
| Data Storage             | MySQL, Redis (Jedis), MongoDB (Spring Data)                                             |
| Authentication           | Spring Security, JWT, Kaptcha                                                           |
| Search/Template          | Thymeleaf 3                                                                             |
| Task Scheduling          | Quartz                                                                                  |
| Tools                    | Lombok, Hutool, Fastjson, Jackson, Apache Commons, Apache POI, dom4j                    |
| Database Connection Pool | Druid                                                                                   |


## Installation and Running

### Requirements

-   **Node.js**: Recommended 18+ with Vue CLI 5 support
-   **Java JDK**: 1.8
-   **Maven**: 3.x
-   **MySQL / Redis / MongoDB**: Required for data storage and caching

### Core Functions
DRGF provides an integrated platform for growth factor research, covering data browsing, literature retrieval, clinical trial tracking, and statistical analysis.

-   **Knowledge Base**: Growth factor browsing, drug retrieval, advanced search, literature details, clinical research records, and summary statistics.
-   **Data Management**: Data acquisition, category management, data maintenance, and backup management.
-   **Visualization**: Interactive statistical charts powered by ECharts.
-   **Literature Retrieval**: Integrated literature search from GeenMedical, The Lens, and ClinicalTrials.
-   **Content Management**: Website content maintenance including articles, videos, popular content, help documents, about us, and user feedback.
-   **Search Management**: Search keyword management, query examples, word clouds, and access control configuration.
-   **System Management**: Menu, role, organization, personnel, position, parameter, agreement, alert, and system service management.
-   **User and Workspace**: Authentication, password modification, customer management, and workspace functions.

### Data Statistics
| Data Category   | Source             | Quantity    |
| --------------- | ------------------ | ----------- |
| Literatures     | PubMed             | 1,600,000+  |
| Patents         | The Lens           | 1,700,000+  |
| Clinical Trials | ClinicalTrials.gov | 11,000+     |
| Drugs & Targets | Internal Database  | 1,700+      |

### Data Overview

**Literatures**

The platform collects articles from PubMed. Each record includes the article title, impact factor, PMID, journal name, publication date, volume and page information, author list, abstract, and links to PubMed or DOI resources.

**Patents**

Patent data are obtained from The Lens platform. Records include LensID, patent title, legal status, publication date, application number, inventors, and links to original patent details.

**Clinical Trials**

Clinical trial registration data are obtained from ClinicalTrials.gov. Records include study title, NCT number, study status, study type, sponsor, official publication date, and links to the original records.

**Drugs & Targets**

The system maintains structured data for growth factors and their targeted drugs. It supports fuzzy searching by Chinese and English drug names, sorting by approval date, Excel batch import, and paginated display.

Drug information is organized into three sections:
1. Basic information: drug names, trade names, dosage forms, specifications, targets, active ingredients, ATC classification, and indications.
2. Marketing information: approval numbers, approval dates, marketing authorization holders and addresses, manufacturers and addresses, and marketed countries/regions.
3. Insurance information: reimbursement classification, insurance numbers, restricted-use scope, and OTC/prescription classification.

## License

This repository is publicly accessible for reference only. Commercial use or redistribution requires written permission. Copyright belongs to the Growth Factor Research Group of Wenzhou Medical University.
