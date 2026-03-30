# Project Spec: IHE GitHub Transition & Governance Framework

## 1. Project Vision
**Goal**: Transition the IHE GitHub organization from a centralized, manual workflow to a decentralized, "domain-led" model.
**Objective**: Enable technical "Domain Leads" to author and publish computable standards (AsciiDoc, FHIR IG) autonomously, while reducing the administrative burden on non-technical Organization Owners.

## 2. Technical Context
*   **Organization**: [IHE on GitHub](https://github.com/IHE)
*   **Plan**: GitHub Free (No access to "Sub-organizations" or advanced "Custom Roles").
*   **Primary Technologies**:
    *   **FHIR IG Publisher** (Existing stack).
    *   **AsciiDoc / Asciidoctor** (Target stack for technical frameworks).
    *   **GitHub Pages** (Hosting for computable standards).
    *   **GitHub Actions** (CI/CD for auto-rendering documents).

## 3. Governance Architecture (The "Two-Playbook" Model)
To solve the lack of nested namespaces, the project uses a **Delegated Authority** model:

### A. Org Admin Role (The Stewards)
*   **Personnel**: Non-technical IHE staff.
*   **Responsibilities**:
    *   Creating new repositories from **Templates**.
    *   Assigning **Domain Teams** as "Admin" to those repos.
    *   Handling the **Email Request** flow (Trigger: Domain lead sends email with Repo Name, Tech Stack, and Lead Username).
*   **Constraint**: Must be a "zero-code" workflow using only the GitHub UI.

### B. Domain Admin Role (The Implementers)
*   **Personnel**: Technical leads (e.g., ITI, PCC domains).
*   **Permissions**: **Team Maintainer** status.
*   **Responsibilities**:
    *   Managing their own contributors (adding/removing team members from their assigned team).
    *   Configuring Repo Settings (Branch protection, Secrets).
    *   Managing Subdomains (e.g., `iti.ihe.net`) via GitHub Pages settings.

## 4. Infrastructure Requirements (The "Menu" of Templates)
The agent should help build the following repository templates:

1.  **`IHE/template-asciidoc`**:
    *   Standard directory structure for IHE Technical Frameworks.
    *   `.github/workflows/publish.yml`: Auto-renders `.adoc` to HTML/PDF and deploys to `gh-pages` branch.
2.  **`IHE/template-fhir-ig`**:
    *   Based on existing FHIR IG Publisher standards.
3.  **`IHE/template-base`**:
    *   Generic boilerplate (License, Contributing.md, README) for new domains.

## 5. User Stories for Playbook Development
*   **Story 1**: A Domain Lead emails an Org Admin requesting a new AsciiDoc-based repo titled `iti-pds-fhir`.
*   **Story 2**: The Org Admin uses the `template-asciidoc` to create the repo and assigns the `ITI-Domain` team as Admin.
*   **Story 3**: The Domain Lead (as Team Maintainer) adds three new contributors to the `ITI-Domain` team without involving the Org Admin.
*   **Story 4**: The Domain Lead sets up `iti.ihe.net` to point to the new repo's documentation.

## 6. Implementation Task List
1.  **Team Setup**: Create GitHub Teams for each domain; appoint Maintainers.
2.  **Permissions**: Set Org-level repository creation to "Owners Only."
3.  **CI/CD**: Develop the Asciidoctor GitHub Action for the template.
4.  **Documentation**: Build the `IHE/playbooks` repo to host the guides at `playbooks.ihe.net`.
5.  **Domain Verification**: Ensure `ihe.net` is verified at the Org level to secure subdomains.

## 7. Future-Proofing (The "Exit Strategy")
*   Provide a "Just-in-case" section in playbooks for **Billing** and **Audit Logs**.
*   Ensure all CI/CD logic is "embedded" in templates so it persists after the project lead (6-month term) disengages.
