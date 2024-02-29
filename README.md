# Exoplanet Classifier

This project explores the use of machine learning techniques to classify the planet type for exoplanets based on their recorded features. The ability to accurately identify what type an exoplanet is with machine learning models would provide an immediate deeper understanding into the composition of a newly discovered planet, depicting whether it is mainly gas-based or of a terrestrial type similar to Earth. Discovering this planet type for newly found exoplanets would enable researchers within Astronomy to determine the relevance of that particular planet within current ongoing research.

## Dataset

This project makes use of a dataset by NASA consisting of 5250 exoplanets. For each planet, the dataset includes:

    - Distance from Earth
    - Stellar magnitude (brightness of the planet)
    - Planet type
    - Year of discovery
    - Mass
    - Radius
    - Orbital radius
    - Orbital period
    - Eccentricity
    - Method of detection with which the planet was found

The planet type classifies each of the planets into one of:

    - Gas giants
    - Neptune-like
    - Super-Earths
    - Terrestrial

Of the `5250` planets in the dataset, there are `1825` Neptune-like, `1630` gas giants, `1595` super-Earths, `195` terrestrial planets and `5` unknown.

## Preprocessing

Initially, the mass and radius of each planet is recorded as a factor of either Earth’s or Jupiter’s mass or radius respectively. To ensure the units of measurement is consistent for all entries, these columns are converted such that all planet masses and radii are listed as multiples of the Earth’s mass and radius. This is done by using Jupiter’s mass being `317.83` times that of Earth, and Jupiter’s radius being larger by a factor of `11.209`

The names and discovery years of the planets are removed as a potential point of bias. K-Nearest Neighbour (KNN) imputation using K=5 is used to fill any empty entries in a planet’s data. This allows all planets where the type is known to be preserved in the dataset and assist in training the model.

The five planets where the classification is not yet known are removed.

## How it works and how to run

Since this is a problem of classification, a random forest classifier is used. 80% of the dataset is used to train the model and it is tested on the remaining 20%.

The program is most effectively run through Jupyter Notebooks. Here the machine learning models and the input parameters used to train the models can be modified.

The numerous branches of this repo correspond to using different selections of input parameters when training the machine learning models.
