# Digital Autonomy Assessment Tool

A browser-based assessment tool that implements the Digital Autonomy Assessment Framework (DAAF). Helps organisations evaluate the digital autonomy of their application landscape. Developed at Utrecht University as part of the UU Digital Autonomy project.

## About

The Digital Autonomy Assessment Framework (DAAF) is a structured approach to assessing applications across three levels:

1. **Risk exposure**: how significant are the dependencies and associated risks?
2. **Mitigation capacity**: what measures are in place to manage those risks?
3. **Strategic importance**: how critical is the application to the organisation?

This tool implements the framework as an interactive, browser-based assessment. Based on 22 indicators across 8 dimensions, it calculates an autonomy score (1-10) per application. Results are presented in a summary table and an autonomy quadrant that provides immediate insight into which applications require attention.

> **Note:** The tool interface is currently in Dutch. An English version is planned for a future release.

## Features

- Fully client-side: runs entirely in the browser, no server required
- Data is stored locally in the browser (localStorage)
- Quick scan (9 indicators) and full assessment (22 indicators)
- Assess and compare multiple applications side by side
- Import/export via JSON and CSV
- Guided scoring with rubrics per indicator

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

All data stays in your browser. Nothing is sent to a server. You can export assessments as JSON (for backup or transfer) or CSV (for further analysis).

## Dimensions

| Code | Dimension | Level |
|------|-----------|-------|
| A | Geopolitical risk | Risk exposure |
| B | Vendor dependency | Risk exposure |
| C | Technical resilience | Mitigation capacity |
| D | Organisational resilience | Mitigation capacity |
| E | Contractual resilience | Mitigation capacity |
| F | Organisational importance | Strategic importance |
| G | Data importance | Strategic importance |
| H | Compliance importance | Strategic importance |

## Scoring methodology

The autonomy score is calculated using the formula:

```
Score = Mitigation / (Risk exposure x Strategic importance)
```

The result is normalised to a 1-10 scale using a logarithmic function, where 1 indicates low autonomy (urgent) and 10 indicates high autonomy (optimal).

## Technical details

- Single HTML file, no external dependencies
- Plain JavaScript, no frameworks or external libraries
- Responsive design

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

## Contact

- Tim van Neerbos, Lead Enterprise Architect, Utrecht University
- Email: tim@vneerbos.nl
