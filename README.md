## UNETs implementation for paddy fields segmentation in Santa Fe (Argentina)

This project corresponds to the final assignment for the Geo Data Scientist course provided by the [Geodojo institute](https://www.geodojo.ai/geo-data-scientist) during 2025.

**Author:** Franco David Barrionuevo (@francobarrionuevoenv21)

### About the project

The project consists of training a Convolutional Neural Network to detect active/in-production paddy fields in a region in northern Santa Fe, Argentina. This area was originally characterized by wetlands, but in recent decades these natural ecosystems have been converted into paddy fields.

The approach will involve training a basic [U-Net neural network](https://www.geeksforgeeks.org/machine-learning/u-net-architecture-explained/) along with two variations. These variations will use different backbones and pretrained weights.

<p align="center">
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/585cfa62-7902-4bbe-9649-2984913d32cc"/> <br> 
<b>Description</b>: UAV fly over the study area; <b>Credits</b>: Natalia Morandeira (@nmorandeira) </p>

### Data

The data used in this project consists of [Landsat 8 (L8) composite scenes (corrected to surface reflectance)](https://developers.google.com/earth-engine/datasets/catalog/LANDSAT_LC08_C02_T1_L2?hl=es-419) for the period November–February. This corresponds to the stage in which the paddy fields of the study area—a wetland region in northern Santa Fe (Argentina)—reach full development before harvesting. During this period, the crop is easier to identify in optical imagery and typically shows a strong NDVI peak associated with maximum biomass.

The L8 images were obtained from the Google Earth Engine platform. To reduce file size, only the R, G, B and NIR bands were included. In total, 12 images were retrieved, one for each year between 2014 and 2024. For example, to obtain the scene for 2019, the composite was generated using the period from November 2018 to February 2019, and so on.

### Description

- **L8_data_chipping_v3.ipynb**: In this notebook, the processing of the L8 scenes is performed to prepare them as input for the CNN models. First, the NDVI index is computed. Then, the image and mask chips are generated. The ground truth for each year corresponds to a vector layer with clusters of paddy fields differentiated by active year, which was generated and validated as previous work.

- **UNETs_training_paddyfieldsV2.ipynb**: In this notebook, three U-Nets variations to detect active/in-production paddy fields in the study area will be trained. For this purpose will be used the L8 data chips and its masks prepared before.

**Keywords:** Deep learning, UNET, segmentation, paddy fields, remote sensing, GIS

**Author's contact:** [francod.barrionuevo@gmail.com](mailto:francod.barrionuevo@gmail.com)

