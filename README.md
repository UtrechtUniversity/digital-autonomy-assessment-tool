# Digital Autonomy Assessment Tool

A browser-based assessment tool that implements the Digital Autonomy Assessment Framework (DAAF). Helps organisations evaluate the digital autonomy of their application landscape. Developed at Utrecht University as part of the [Digital Autonomy programme](https://www.uu.nl/en/organisation/digital-autonomy).

> **License in short:** free to use by educational, research, non-profit and government organisations. Commercial organisations may use it to assess their own IT landscape, under the conditions in the [LICENSE](LICENSE): credit the original author, do not sell it, and do not rebrand it or turn it into another framework. See [License](#license) below.

## About

The Digital Autonomy Assessment Framework (DAAF) is a structured approach to assessing applications across three levels:

1. **Risk exposure**: how significant are the dependencies and associated risks?
2. **Mitigation capacity**: what measures are in place to manage those risks?
3. **Strategic importance**: how critical is the application to the organisation?

This tool implements the framework as an interactive, browser-based assessment. Based on 22 indicators across 8 dimensions, it calculates an autonomy score (1-10) per application. A dashboard with an autonomy quadrant gives immediate insight into which applications require attention.

> **Note:** The tool is available in seven languages (Dutch, English, German, French, Spanish, Italian and Danish), with Dutch as the default. Dutch and English are verified; the other languages are best effort and not yet fully reviewed by native speakers (contributions welcome). The user guide and changelog are available in Dutch and English (other languages show English).

## Features

- Fully client-side: runs entirely in the browser, no server required
- Works fully offline and makes no external requests: fonts are bundled, so no data (such as IP addresses) is sent to third parties
- Data is stored locally in the browser (localStorage)
- Quick scan (9 indicators) and full assessment (22 indicators)
- Dashboard with autonomy quadrant, filters, supplier and organisational-unit overviews
- Radar chart per application
- One profile for your organisation: sector texts (dimension H and G2), dimension H on or off, and organisation-wide weights, with per-application deviations
- Import/export via JSON and CSV (summary and detailed, the detailed export includes the per-indicator remarks)
- Multilingual: Dutch, English, German, French, Spanish, Italian and Danish (switch language from the toolbar)
- Guided scoring with rubrics and glossary tooltips per indicator
- Delete with undo, bulk delete and a trash
- Export reminder to help prevent data loss
- Changelog viewer for version history

## Usage

Open the tool via GitHub Pages:
**https://utrechtuniversity.github.io/digital-autonomy-assessment-tool/**

Or download `index.html` and open it locally in your browser. Note that the browser stores data per location: assessments made on GitHub Pages are not visible in a locally opened file, and vice versa. Use JSON export and import to move data.

### Getting started

1. Click "+ Add Application" and enter a name
2. Choose Quick scan or Full assessment
3. Score each indicator using the provided rubrics
4. View the results in the dashboard and autonomy quadrant

Want to explore first? Choose Import, then "Load sample data".

### Assessing together

The DAAF is usually completed together with colleagues, without anyone having to log in. A common way of working:

1. **Agreements beforehand**: one coordinator creates the organisation's profile (sector texts, dimension H and weights) and shares it. Also agree on the names of organisational units and suppliers.
2. **Completing**: colleagues import that profile via Import > Import profile (it then becomes their active profile), assess their applications and export them as JSON.
3. **Collecting**: the coordinator imports all JSON files at once. The import preview shows what will happen per assessment (new, identical, updated version) and asks how unknown organisational units and suppliers should be mapped, so the overview stays clean.
4. **Complete overview**: the coordinator's dashboard shows the complete picture (quadrant, suppliers, organisational units, data quality) and can be presented to different stakeholders, for example filtered by organisational unit or supplier, printed, or exported as CSV.

The dashboard also works for an individual user, but then you only see your own assessments.

### Data privacy

All data stays in your browser. Nothing is sent to a server, and the page makes no external requests at all (fonts are bundled in the file). You can export assessments as JSON (for backup or transfer) or CSV (for further analysis).

## Profiles

A profile sets how your organisation uses the DAAF. It holds three things, each on its own tab:

- **Sector texts**: the DAAF was developed for higher education, so dimension H (Academic impact) and indicator G2 (Research data and knowledge security) are sector-specific. You can adapt their texts to your sector yourself, or copy the texts of a sector template in one go and adapt them from there.
- **Dimension H**: switch it off if it does not fit your organisation. Strategic importance then becomes the average of dimensions F and G.
- **Weights**: one weighting for your whole organisation. Per application you can still deviate.

The default profile is the DAAF as developed for higher education and is fixed, so scores stay comparable. You create your own profile from a sector template: higher education (the default), primary and secondary education, municipalities, central government, provinces, water authorities or executive agencies (such as tax or benefits agencies), or a generic template. Use "View texts" to see a template's sector texts before you choose. The template is only the starting point. **The templates outside higher education are a first version.** Feedback and input from these sectors are very welcome, so we can improve them together. Templates are currently in Dutch. The other indicators, the scale and the calculation stay the same for everyone.

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
| H | Academic impact (sector-specific) | Strategic importance |

## Scoring methodology

The autonomy score is calculated using the formula:

```
Score = Mitigation / (Risk exposure x Strategic importance)
```

The result is normalised to a 1-10 scale using a logarithmic function, where 1 indicates low autonomy (urgent) and 10 indicates high autonomy (optimal). If dimension H is switched off in a profile, strategic importance is the average of dimensions F and G.

## Compatibility

- Stored data from earlier versions is loaded automatically; nothing needs to be converted. When upgrading from 0.8.x, a backup of the stored data is made automatically in the browser.
- JSON files exported with earlier versions can be imported. The export format remains `DAAF-export-v1`; new fields are optional additions that older versions simply ignore.

## Technical details

- Single HTML file, no external dependencies or network requests
- Fonts (Merriweather, OFL; Open Sans, Apache 2.0) are embedded as woff2
- Plain JavaScript, no frameworks or external libraries
- Responsive design

## Acknowledgements

The multilingual translations were created with the help of **Thomas Steenbergen** (OSPO Advisor at [SIVON](https://www.sivon.nl)), who also contributed to the sector template for primary and secondary education. Dutch and English are verified; the German, French, Spanish, Italian and Danish translations are best effort. Contributions are welcome.

Thanks to **Lucas Hofmann** (University of Würzburg) for reviewing and improving the German translation.

Thanks to **Dr. Jonas Heller** (Maastricht University) for suggesting the move to self-hosted (bundled) web fonts, removing the dependency on Google's font servers.

## License

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/), with the additional permission below. The full text is in the [LICENSE](LICENSE) file.

### Additional permission (CC+)

In addition to the rights granted under CC BY-NC-SA 4.0, Utrecht University grants every organisation, including commercial organisations, permission to use the DAAF and this tool free of charge to assess its own applications and IT landscape, and to share the results within the organisation and with its own auditors and supervisory bodies. This includes consultants acting on behalf of such an organisation.

This additional permission applies only if:

- the DAAF is credited to its original author (Tim van Neerbos, Utrecht University) with a link to this repository;
- the DAAF is not presented as the method, model or product of anyone else, and no other names, logos or branding are added to it;
- the DAAF is not sold, licensed or offered as (part of) a paid product, and is not turned into, or merged into, another framework or model.

For any other commercial use, please contact the author first.

## Contact

- Tim van Neerbos, Lead Enterprise Architect, Utrecht University
- Email: t.m.vanneerbos@uu.nl
