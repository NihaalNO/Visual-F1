# Visual-F1

**A telemetry data-visualization hub organized by Driver → Track → Year**

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Motivation](#motivation)
3. [Key Features](#key-features)
4. [Project File Structure (assumptions)](#project-file-structure-assumptions)
5. [Data & Formats](#data--formats)
6. [Getting Started / Installation](#getting-started--installation)
7. [Usage / Examples](#usage--examples)
8. [Reference & Inspirations](#reference--inspirations)
9. [Future Vision (ML & Predictions)](#future-vision-ml--predictions)
10. [Contributing](#contributing)
11. [License & Acknowledgements](#license--acknowledgements)
12. [Contact](#contact)

---

## Project Overview

**Visual-F1** is a telemetry data-visualization project structured around drivers, tracks, and seasons. The repository collects, organizes and visualizes telemetry and lap data for Formula 1 circuits (tracks), beginning from the 2018 season onward. Visualizations are stored per track and per year and are intended to support analysis, storytelling, and downstream machine learning tasks (e.g., predicting lap times, pit strategy outcomes, or tire degradation).


## Motivation

- To build a centralized, well-organized archive of Formula 1 telemetry visualizations, currently focused on Sir Lewis Hamilton.
- To provide clear, shareable visual analysis for comparisons across seasons, tyres, and setup changes.
- To prepare clean, labeled outputs that can feed model development for race/prediction experiments.


## Key Features

- Per-track, per-year telemetry visualizations starting from **2016**.
- Currently focused on a single driver (Sir Lewis Hamilton) for deep-dive comparisons and temporal analysis.
- Jupyter notebooks for plotting speed, throttle, steering, gear, brake, sector times, and more.
- Exportable CSV/feature files suitable for machine learning pipelines.


## Project File Structure (assumptions)

> The project follows a **Driver → Track → Year-specific notebook** hierarchy.

Each driver has a folder, inside which each track has its own folder. Visualizations are stored as notebooks named using the pattern `{track_name}-{year}.ipynb`.

Example layout:
```
Visual-F1/
├── Driver/
│   ├── Lewis_Hamilton/
│   │   ├── Spanish_GP/
│   │   │   ├── output_images/
│   │   │   │   ├── 2018.png
│   │   │   │   ├── 2019.png
│   │   │   │   ├── 2025.png
│   │   │   ├── spanish_gp-2018.ipynb
│   │   │   ├── spanish_gp-2019.ipynb
│   │   │   ├── spanish_gp-2025.ipynb
│   │   ├── British_GP/
│   │   │   ├── output_images/
│   │   │   │   ├── 2018.png
│   │   │   │   ├── 2017.png
│   │   │   ├── british_gp-2018.ipynb
│   │   │   ├── british_gp-2020.ipynb
```
## Reference & Inspirations

- **FastF1** — Python package for accessing and working with F1 telemetry and session data (used as the primary inspiration for data handling and caching patterns).
- **Developer Inspiration**: **mar-antaya** — credited as an inspiration for workflow ideas and some plotting approaches.


## Future Vision (ML & Predictions)

The visualized and processed outputs from **Visual-F1** are intentionally organized so they can be used as training inputs for machine learning models. Some concrete ML possibilities include:

- **Lap time prediction**: Predict lap times using telemetry, sector performance, and tyre data.
- **Pit strategy simulation**: Estimate race outcome probabilities under different pit strategies.
- **Tyre degradation modelling**: Model performance drop-offs across stints and compounds.
- **Driver performance profiling**: Learn driver-specific racing patterns from telemetry.

### Future Enhancements

- Addition of other elite drivers such as **Max Verstappen** and **Fernando Alonso**, following the same Driver → Track → Year structure.
- Cross-driver comparative visualizations.
- Unified feature datasets for multi-driver ML model training.

To support ML workflows, Visual-F1 will continue to provide reproducible, columnar feature exports and well-documented metadata for each session.


## Contributing

1. Fork the repo and create a feature branch.
2. Add or update visualization notebooks under the appropriate `Driver/{Driver_Name}/{Track_Name}/` folder.
3. Ensure output images are exported into the corresponding `output_images/` folder using the `year.png` naming format.
4. Open a pull request with a clear description of changes.


## License & Acknowledgements

- License: Apache 2.0
- Acknowledgements: Thanks to the FastF1 community and to mar-antaya for inspiration.


## Contact

If you want changes, additional formats, or help setting up ML pipelines from Visual-F1 outputs, open an issue or drop a message to the project owner.

---

*Created for data-visualization research and ML-ready outputs. Currently focused on Sir Lewis Hamilton, with planned expansion to multiple drivers — starting season: 2016.*

