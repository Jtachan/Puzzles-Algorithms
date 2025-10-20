# Design Document Template

Here you can find the structured files to be used as a template for a Design Document at any of your projects.

A **Design Document** (DD) is a planification for a project;
a document file where is consolidated all the structure of each part of the project before the project is developed.
In other words, within a DD is explained the idea and planification about a specific project before its implementation starts.
It should be completely uncorrelated from any user's documentation and any code within it should be snippets or pseudocode.

See the section ["DESIGN.md"](#designmd) for a more in-detailed explanation of the parts a DD could contain.

## Structure

Considering the case the DD is contained within the project folder, it is encourage to fit to the following structure:
```
<project>/
| -> Readme.md
|    ...
| -> docs/
     | -> design-doc/
          | -> DESIGN.md
          | -> VERSION.json
          | -> CHANGELOG.txt
```

Each DD is composed by three files:

- **DESIGN.md**: Markdown file containing the complete design document.
- **VERSION.json**: Information about the latest release (commited changes).
- **CHANGELOG.txt**: In-detailed file with explanations about all changes of the latest and previous versions.

> Note: The folder `docs/` is optional, but many repositories and projects (like [`mkdocs`](https://www.mkdocs.org/)) use it as the normalized documents folder.

### DESIGN.md

This file relates to the final released DD.
Each DD can have multiple iterations when the requirements change in a smaller period of time than the one required delivering the final project.

There is no strong reason for all DDs to have the same sections, as each document must adapt to the project it is created for.
However, the following information should be contained in the document:

- **Overview and Context**: A high-level summary of the problem, strategy to tackle it and why this project is necessary.
- **Requirements**: A list of all the specific issues for the project to tackle (if required).
- **Solution**: The strategy for designing the project, divided in the sections that would be required. This also considers:
    - Other existing solutions to the problem and the discussion of why they are not valid for this project.
    - All mathematical formulas that might be included within the project.
    - Any flow-chart diagram is required for clarification.

### VERSION.json

JSON file containing the version of the latest released document, as well as additional basic information about it.

_Example VERSION.json_
```json
{
  "version": "1.3.0",
  "releaseDate": "2025.10.08",
}
```

- `"version"`: Corresponding to the Semantic Versioning of the latest released changes into the document.
- `"releaseDate"`: ISO date specified as 'year.month.day' of the last release.

Other keywords could be integrated if they seem helpful.

### CHANGELOG.txt

Version control of all changes applied into the document.
It is encouraged that the document is a precise and with as many extended explanations as necessary.

The goal of this document is to:

- Avoid new implementations that were deprecated for a good reason.
- Normalize the contribution of everyone that modified the DD.
- State the reason for newly introduced or modified features.

To achieve the previous goal, each changelog should compile to the next set of rules:

- **Continuous append**: Every new release must always be appended into the document, maintaining all the information about any previous release.
- **Data sorting**: Each new release must be appended to the top of the document. In other words, all releases within the changelog must be sorted from newer to older.
- **Semantic Versioning**: A release is defined as vX.Y.Z following the Semantic Versioning rules. No other labels over the version are allowed here.
- **ISO release date**: Every release date must be organized as YYYY.mm.dd (or year.month.day) pointing to the day the release was integrated.
- **Sections**: Use the sections "ADDED", "CHANGED", "FIXED" and "DEPRECATED", always keeping the same order among releases. If one section is empty (for example, nothing was deprecated), it can be skipped at the final changelog document.

_Example CHANGELOG.txt_
```
Changelog
=========

Release v1.3.0 - 2025.10.08
---------------------------
ADDED:
    - Metrics about the speed reading a file in MB/s

CHANGED:
    - The metrics about writing a file from B/s to MB/s
      Reason: It was discussed and decided to unify all byte-speed operation metrics to MB/s

DEPRECATED:
    - Compression metrics
      Reason: It did not provide sufficient additional and helpful information for working and maintaining the project 

Release v1.2.4 - 2025.09.20
---------------------------
...
```
