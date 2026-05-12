# Architecture Overview

This document provides a visual overview of the repository ecosystem and technology composition.

## Repository Architecture

```mermaid
graph TB
    subgraph SVG["SVG Working Group (svgwg)"]
        SVG_HTML["HTML<br/>81.3%"]
        SVG_CSS["CSS<br/>9.4%"]
        SVG_BS["Bikeshed<br/>4.4%"]
        SVG_JS["JavaScript<br/>4.3%"]
        SVG_PY["Python<br/>0.3%"]
    end
    
    subgraph XKCD["XKCD Project (xkcd)"]
        XKCD_CSS["CSS<br/>62%"]
        XKCD_JS["JavaScript<br/>22.4%"]
        XKCD_HTML["HTML<br/>15.6%"]
    end
    
    subgraph CC_LEGAL["CC Legal Tools (cc-legal-tools-app)"]
        CC_PY["Python<br/>66.6%"]
        CC_HTML["HTML<br/>16.2%"]
        CC_CSS["CSS<br/>9.1%"]
        CC_SH["Shell<br/>5.4%"]
        CC_JS["JavaScript<br/>2.7%"]
    end
    
    subgraph CC_ORG["Creative Commons Legacy (creativecommons.org)"]
        CC_ORG_HTML["HTML<br/>99.9%"]
        CC_ORG_OTHER["Other<br/>0.1%"]
    end
    
    SVG -->|Specifications| XKCD
    CC_LEGAL -->|Implements| CC_ORG
    
    style SVG fill:#e1f5ff
    style XKCD fill:#f3e5f5
    style CC_LEGAL fill:#e8f5e9
    style CC_ORG fill:#fff3e0
```

## Technology Stack by Repository

### SVG Working Group (svgwg)
- **Primary Language**: HTML (81.3%) - Specification documents
- **Styling**: CSS (9.4%)
- **Documentation**: Bikeshed (4.4%) - Specification format
- **Scripting**: JavaScript (4.3%)
- **Build Tools**: Python (0.3%), Makefile (0.1%)
- **Description**: SVG Working Group specifications

### XKCD Project (xkcd)
- **Primary Language**: CSS (62%) - Styling focus
- **Interactivity**: JavaScript (22.4%)
- **Markup**: HTML (15.6%)

### CC Legal Tools Application (cc-legal-tools-app)
- **Primary Language**: Python (66.6%) - Backend
- **Markup**: HTML (16.2%)
- **Styling**: CSS (9.1%)
- **Build/Deploy**: Shell (5.4%)
- **Client-side**: JavaScript (2.7%)
- **Description**: Legal tool (licenses, public domain dedication, etc.) management application for Creative Commons

### Creative Commons Legacy (creativecommons.org)
- **Primary Language**: HTML (99.9%) - Static/legacy content
- **Other**: (0.1%)
- **Description**: Legacy legal code translations and general support issues

## Key Insights

1. **SVG Working Group** is documentation-heavy with Bikeshed specifications
2. **XKCD Project** emphasizes frontend styling and interactivity
3. **CC Legal Tools** is a full-stack application with Python backend
4. **Creative Commons Legacy** is a static HTML-based repository for historical content
