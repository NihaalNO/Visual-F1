# Visual-F1

<div align="center">

**A Comprehensive F1 Telemetry Visualization**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![FastF1](https://img.shields.io/badge/FastF1-3.0+-red.svg)](https://github.com/theOehrly/Fast-F1)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

[Report Bug](https://github.com/yourusername/Ham-Hub/issues) · [Request Feature](https://github.com/yourusername/Ham-Hub/issues) · [Documentation](https://github.com/yourusername/Ham-Hub/wiki)

</div>

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Motivation](#motivation)
3. [Key Features](#key-features)
4. [Project File Structure](#project-file-structure-assumptions)
5. [Data & Formats](#data--formats)
6. [Getting Started / Installation](#getting-started--installation)
7. [Usage / Examples](#usage--examples)
8. [Reference & Inspirations](#reference--inspirations)
9. [Future Vision (ML & Predictions)](#future-vision-ml--predictions)
10. [Contributing](Contributing.md)
11. [License & Acknowledgements](#license--acknowledgements)
12. [Contact](#contact)

---

## Project Overview

**Visual-F1** is a telemetry data-visualization project structured around drivers, tracks, and seasons. The repository collects, organizes and visualizes telemetry and lap data for Formula 1 circuits (tracks), beginning from the 2018 season onward. Visualizations are stored per track and per year and are intended to support analysis, storytelling, and downstream machine learning tasks (e.g., predicting lap times, pit strategy outcomes, or tire degradation).

---

## Motivation

Formula 1 generates vast amounts of telemetry data during each race weekend, yet this data remains underutilized for public analysis and predictive modeling. **Visual-F1** addresses this gap by:

- **Building a Centralized Archive**: Creating a well-organized, comprehensive collection of Lewis Hamilton's telemetry visualizations across his illustrious career.
- **Enabling Temporal Analysis**: Facilitating year-over-year comparisons to track performance evolution, car development, and track-specific improvements.
- **Supporting Data-Driven Insights**: Providing clear, shareable visual analysis for understanding racing strategies, optimal racing lines, and performance characteristics.
- **Preparing ML-Ready Datasets**: Structuring outputs to feed machine learning pipelines for race predictions, strategy optimization, and performance forecasting.

By focusing on a single driver of Hamilton's caliber, the project enables deep-dive analysis that reveals patterns, consistency, and evolution across regulation changes, team transitions, and circuit characteristics.

---

## Key Features

### Comprehensive Telemetry Visualizations
- **Speed Traces**: Color-coded track maps showing speed variations throughout the lap
- **Throttle & Brake Applications**: Detailed analysis of driver inputs and braking zones
- **Gear Changes**: Visualization of gear selection patterns around the circuit
- **Racing Lines**: Comparative analysis of optimal racing lines across different years
- **Sector Performance**: Breakdown of lap times by sector with historical comparisons

### Historical Coverage
- **Temporal Depth**: Data visualization spanning from **2018** to **2025** (current season)
- **Complete Track Coverage**: All circuits where Lewis Hamilton has competed during this period
- **Regulation Era Comparison**: Analysis across multiple F1 regulation changes (2017 aero, 2019 updates, 2022 ground effect)

### Data Organization
- **Track-Based Structure**: Each circuit has its dedicated folder with year-by-year notebooks
- **Reproducible Analysis**: Jupyter notebooks ensure transparency and reproducibility
- **Export Capabilities**: Visualizations saved as high-quality PNG images
- **ML-Ready Outputs**: Structured data exports suitable for machine learning workflows

### Driver-Centric Focus
Currently focused exclusively on **Sir Lewis Hamilton**, enabling:
- Career trajectory analysis
- Performance consistency studies
- Circuit-specific mastery evaluation
- Team transition impact assessment (Mercedes to Ferrari)

---

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
---
## Data & Formats

### Data Source
**Ham-Hub** leverages the **[FastF1](https://github.com/theOehrly/Fast-F1)** Python package to access official Formula 1 timing and telemetry data. FastF1 provides:
- Real-time and historical session data
- Lap-by-lap telemetry (speed, throttle, brake, gear, DRS, etc.)
- Session information (weather, track status, race control messages)
- Driver and team metadata

### Telemetry Parameters
Each visualization incorporates multiple telemetry channels:

| Parameter | Description | Unit |
|-----------|-------------|------|
| **Speed** | Car velocity | km/h |
| **Throttle** | Accelerator pedal position | % (0-100) |
| **Brake** | Brake pressure/activation | Binary or % |
| **Gear** | Current gear selection | 1-8 |
| **RPM** | Engine revolutions per minute | rpm |
| **DRS** | Drag Reduction System status | Binary |
| **X, Y** | Track position coordinates | Meters |
| **Distance** | Distance along track | Meters |

### Output Formats
- **Visualizations**: High-resolution PNG images (1200x675px minimum)
- **Notebooks**: Jupyter `.ipynb` files with embedded analysis and markdown documentation

### Data Completeness
- **2018-2025**: Full race telemetry for all driver's race participations
- **Session Types**: Race sessions (qualifying and practice data available for select events)
- **Missing Data**: Some sessions may have incomplete telemetry due to technical issues or data unavailability

---

## Getting Started / Installation

### Prerequisites
- **Python 3.8+** (3.10 or 3.12 recommended)
- **pip** package manager
- **Jupyter Notebook** or **JupyterLab**
- Stable internet connection (for initial FastF1 data downloads)

### Installation Steps

1. **Clone the Repository**
```bash
   git clone https://github.com/NihaalNO/Visual-F1.git
   cd Visual-F1
```

2. **Create Virtual Environment** (recommended)
```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
```

3. **Install Dependencies**
```bash
   pip install -r requirements.txt
```

4. **Set Up FastF1 Cache** (optional but recommended)
```python
   # In your notebook or Python script
   import fastf1
```

### Required Packages
```
fastf1>=3.0.0
matplotlib>=3.5.0
numpy>=1.21.0
pandas>=1.3.0
jupyter>=1.0.0
```
---
## Usage / Examples

### Basic Usage

1. **Navigate to a Circuit Folder**
```bash
   cd circuits/Spanish_GP/
```

2. **Open the Desired Year's Notebook**
```bash
   jupyter notebook spanish_gp_2025.ipynb
```

3. **Run All Cells** to generate visualizations

### Customization Options

You can modify the notebooks to:
- Change color schemes (colormap parameter)
- Compare multiple laps (fastest vs. different tire compounds)
- Overlay throttle/brake data
- Analyze specific sectors or corners
- Export data for further analysis

### Output Location
All generated visualizations are automatically saved to the `output_images/` folder within each circuit directory.

---

## Reference & Inspirations

### Primary Data Source
**[FastF1](https://github.com/theOehrly/Fast-F1)** - A comprehensive Python package for accessing Formula 1 timing and telemetry data. FastF1 provides the foundational data infrastructure that makes Ham-Hub possible.

- **Creator**: theOehrly
- **Documentation**: [docs.fastf1.dev](https://docs.fastf1.dev/)
- **GitHub**: [github.com/theOehrly/Fast-F1](https://github.com/theOehrly/Fast-F1)

### Developer Inspiration
**mar-antaya**: [[Github](https://github.com/mar-antaya)] - Acknowledged as a key inspiration for:
- Workflow design patterns
- Visualization approaches
- Data organization strategies
- Plotting techniques and aesthetics

### Additional Resources
- **F1 Official Timing**: Data sourced through FastF1's API integration
- **Matplotlib**: Advanced plotting and customization
- **Jupyter Notebooks**: Interactive analysis and documentation

---

## Future Vision (ML & Predictions)

One of the core objectives of **Ham-Hub** is to create a **machine learning-ready dataset** that can power predictive models for Formula 1 racing. The structured, labeled outputs from this project are intentionally designed to support various ML applications.

### Planned Machine Learning Applications

#### 1. **Lap Time Prediction**
- **Input Features**: Telemetry data (speed, throttle, brake), track conditions, tire age, fuel load
- **Target Variable**: Predicted lap time
- **Use Case**: Forecast qualifying performance and race pace based on practice session data
- **ML Approaches**: Regression models (Random Forest, XGBoost, Neural Networks)

#### 2. **Pit Strategy Optimization**
- **Input Features**: Tire degradation curves, gap to competitors, track position, weather forecast
- **Target Variable**: Optimal pit window, predicted race outcome
- **Use Case**: Simulate race scenarios under different pit strategies
- **ML Approaches**: Reinforcement Learning, Monte Carlo simulation

#### 3. **Tire Degradation Modeling**
- **Input Features**: Lap number, compound type, track temperature, driving style metrics
- **Target Variable**: Tire performance drop-off per lap
- **Use Case**: Predict when tire performance will fall below optimal threshold
- **ML Approaches**: Time-series forecasting (LSTM, Prophet)

#### 4. **Driver Performance Profiling**
- **Input Features**: Braking points, corner entry/exit speeds, throttle application patterns
- **Target Variable**: Driver-specific racing line efficiency
- **Use Case**: Identify Hamilton's unique driving characteristics and consistency patterns
- **ML Approaches**: Clustering (K-means), Principal Component Analysis

#### 5. **Race Outcome Prediction**
- **Input Features**: Grid position, historical performance at circuit, car performance metrics, weather
- **Target Variable**: Finishing position probability distribution
- **Use Case**: Pre-race predictions and in-race strategy adjustments
- **ML Approaches**: Classification models (Logistic Regression, Gradient Boosting)

#### 6. **Overtaking Probability Analysis**
- **Input Features**: Speed differential, DRS availability, tire compound delta, track section
- **Target Variable**: Likelihood of successful overtake
- **Use Case**: Inform strategic decisions on when to push for overtakes
- **ML Approaches**: Binary classification, ensemble methods

---

## License & Acknowledgements

### License
This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### Acknowledgements

- **Sir Lewis Hamilton**: The focus of this analytical project and an inspiration to millions worldwide
- **FastF1 Development Team** ([theOehrly](https://github.com/theOehrly)): For creating and maintaining the incredible FastF1 package
- **mar-antaya** ([mar-antaya](https://github.com/mar-antaya)): For workflow inspiration and visualization techniques
- **Formula 1**: For the exciting sport that generates this fascinating data
- **F1 Data Community**: Researchers, analysts, and enthusiasts who push the boundaries of motorsport analytics

### Data Attribution
All Formula 1 timing and telemetry data is accessed via the **FastF1** package, which sources official F1 timing data. This project is not affiliated with, endorsed by, or connected to Formula One Management, Formula One World Championship Limited, or any F1 teams.

### Fair Use Statement
This project is created for **educational and research purposes**, focusing on data visualization and machine learning applications. All visualizations are transformative works based on publicly available telemetry data.

---

## Contact

### Project Maintainer
- **GitHub**: [Your GitHub Profile](https://github.com/NihaalNO)
- **Email**: odathernihaal@gmail.com

### Getting Help
- **Issues**: Open an issue for bugs or feature requests
- **Discussions**: Use GitHub Discussions for questions and ideas
- **Pull Requests**: Submit PRs for contributions (see [CONTRIBUTING.md](CONTRIBUTING.md))

### Stay Updated
- ⭐ Star the repository to stay notified of updates
- 👀 Watch for new releases and features
- 🍴 Fork to create your own driver-focused analysis

---
<div align="center">

**Built with ❤️ for Formula 1 analytics**

---

*This project is continuously evolving. Check back regularly for new circuits, years, and ML capabilities.*

**Last Updated**: January 2025  
**Current Coverage**: 2018-2025 | Focus: Lewis Hamilton | Tracks: Spanish GP (complete) Great Britain (complete), expanding to full calendar

</div>
