# Solar Power dataset
Working with the [Solar Power Generation Data](https://www.kaggle.com/anikannal/solar-power-generation-data)

This project is in its early stages. See the [jupyter notebook](./solar_power_data_exp_and_model_training.ipynb) for implementation details.

> This data has been gathered at two solar power plants in India over a 34 day period. It has two pairs of files - each pair has one power generation dataset and one sensor readings dataset. The power generation datasets are gathered at the inverter level - each inverter has multiple lines of solar panels attached to it. The sensor data is gathered at a plant level - single array of sensors optimally placed at the plant.
> 
> There are a few areas of concern at the solar power plant -
> 
> 1. Can we predict the power generation for next couple of days? - this allows for better grid management
> 2. Can we identify the need for panel cleaning/maintenance?
> 3. Can we identify faulty or suboptimally performing equipment?

## Overview

Power generation data is split by plant and inverter ID. Thus far, I've focused on plant-level comparisons. Later, I will explore inverter differences.

## Data Exploration


### Looking at raw data

Initial observations:
- What's up with cumulative yield?
- Weather at the two plants is fairly similar
    - Plant #2 is ~2.5 degree warmer
    - Very similar irradiation
- Power more different
    - Plant #2 generates little DC power, and ~15% less AC power
- Correlations:
    - total yield: higher for plant 2
    - DC power: higher for plant 1
    - DC power, AC power, module temperature, irradiation, ambient temperature strongly corellated
      (ambient slightly less than others)
    - ambient temperature peaks a few hours after noon
    - other data peaks close to noon
    - irradiation and AC/DC power generation nearly symmetric over noon
    - **Plant 2 power seems to saturate at certain values: AC ~14k and DC ~2k**
### TODO
- check for missing times during night
- investigate missing power-weather pairs
- investigate Plant 2 power saturation
- plot averages by day
- plot comparison for different inverters
- histogram to identify performance outliers
- split_scatter?
- possible features to add:
    - AC:DC ratio
    - bool: module temp > ??
    - bool: yield < ??
    - median yield by Plant, inverter
    - median temperature and irradiation by plant + time
    - bool: before/after noon
    - variance of grouped data



<!-- ## Data preparation


## Model selection

Observations:

## Generalization 

## Summary and Outlook -->
