# Digital Autonomy Assessment Tool

A browser-based assessment tool that implements the Digital Autonomy Assessment Framework (DAAF). Helps organisations evaluate the digital autonomy of their application landscape. Developed at Utrecht University as part of the Digital Autonomy programme.

## About

The Digital Autonomy Assessment Framework (DAAF) is a structured approach to assessing applications across three levels:

1. **Risk exposure**: how significant are the dependencies and associated risks?
2. **Mitigation capacity**: what measures are in place to manage those risks?
3. **Strategic importance**: how critical is the application to the organisation?

This tool implements the framework as an interactive, browser-based assessment. Based on 22 indicators across 8 dimensions, it calculates an autonomy score (1-10) per application. Results are presented in a summary table and an autonomy quadrant that provides immediate insight into which applications require attention.

> **Note:** The tool interface is currently in Dutch. An English version is planned for a future release.

## Features

- Fully client-side: runs entirely in the browser, no server required
- Works fully offline and makes no external requests: fonts are bundled, so no data (such as IP addresses) is sent to third parties
- Data is stored locally in the browser (localStorage)
- Quick scan (9 indicators) and full assessment (22 indicators)
- Assess and compare multiple applications side by side
- Adjustable indicator weights per application
- Import/export via JSON and CSV (summary and detailed, the detailed export includes the per-indicator remarks)
- Guided scoring with rubrics and glossary tooltips per indicator
- Quick delete with undo, and bulk delete
- Export reminder to help prevent data loss
- Changelog viewer for version history

## Usage

Open the tool via GitHub Pages:
**https://utrechtuniversity.github.io/digital-autonomy-assessment-tool/**

Or download `index.html` and open it locally in your browser.

### Getting started

1. Click "Nieuwe applicatie" (New application) and enter a name
2. Choose Quick scan or Full assessment
3. Score each indicator using the provided rubrics
4. View the results in the overview table and autonomy quadrant

### Data privacy

All data stays in your browser. Nothing is sent to a server, and the page makes no external requests at all (fonts are bundled in the file). You can export assessments as JSON (for backup or transfer) or CSV (for further analysis).

## Dimensions

| Code | Dimension | Level |
|------|-----------|-------|
| A | Geopolitical risk | Risk exposure |
| B | Vendor dependency | Risk exposure |
| C | Technical resilience | Mitigation capacity |
| D | Organisational resilience | Mitigation capacity |
| E | Contractual resilience | Mitigation capacity |
| F | Organisational importance | Strategic importance |
| G | Data sensitivity | Strategic importance |
| H | Academic impact | Strategic importance |

## Scoring methodology

The autonomy score is calculated using the formula:

```
Score = Mitigation / (Risk exposure x Strategic importance)
```

The result is normalised to a 1-10 scale using a logarithmic function, where 1 indicates low autonomy (urgent) and 10 indicates high autonomy (optimal).

## Technical details

- Single HTML file, no external dependencies or network requests
- Fonts (Merriweather, OFL; Open Sans, Apache 2.0) are embedded as woff2
- Plain JavaScript, no frameworks or external libraries
- Responsive design

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

## Contact

- Tim van Neerbos, Lead Enterprise Architect, Utrecht University
- Email: tim@vneerbos.nl
