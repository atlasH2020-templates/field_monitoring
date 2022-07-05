![](RackMultipart20220705-1-ruigrg_html_70e3b217e6f91606.png)

# ATLAS Service Template Specification

# Name: Crop Status Monitoring

# Author(s): AgroApps (AGA)

_The &quot;__Crop Status Monitoring&quot; ATLAS Service Template_

This service will deliver a number of EO derived indicators for crop status monitoring consisting of:

- Vegetation Indices

NDVI

- Biophysical Parameters for annual crops

Biomass

LAI

- Chl Content
- Canopy Water Content

and a number of farm services, such as:

- Yield Estimation
- Crop Residues

The system for the calculation and application of the VIs will be optimized with respect to crop types. To ensure high temporal coverage of the data, the system will utilize data from optical satellite sensors, namely the Sentinel-2.

The provider of the Crop Status Monitoring Service is **AgroApps P.C. (AGA)**. The service is provided through a centralized integration RESTful API.

## INTRODUCTION

The **Crop Status Monitoring (CSM) Service**, is an earth observation crop monitoring module that exploits multispectral satellite data, and through the use of validated algorithms, provides crop monitoring and farming services products to the external client. The aim of the **CSM service** is to provide farmers with information on their crops&#39; health status, through a biophysical proxy, namely the NDVI and biophysical parameters (Leaf Area Index – LAI, Chlorophyll content – Chl, above ground crop biomass production, NDWI – canopy water status). Another aim is to provide estimations of the expected yield and crop residues. The CSM service multi-device application component ( **web-based or mobile** ) can help farmers identify anomalies in plant performance during the growing season, by comparing consecutive satellite images of high resolution (10 m or 20 m) depicting the status of their parcels.

The **CSM Service** will provide crop growth, yield and crop residues information in parcel and sub parcel level and will enable farmers to keep an eye on their crops&#39; status **from emergence through harvest**. Local deviations of the calculated parameters could imply the occurrence of abiotic and/or biotic stress in crops. Indirectly, crop growth monitoring helps in delineating different management zones at sub-parcel level, that are otherwise invisible to the naked eye, for variable rate application of crop protection products (CPPs) or fertilizers. The crop monitoring data are crop specific for **wheat** , **maize** , **soybean** , **cotton** and **sunflower**.

## Crop Status Monitoring (CSM) / Products: Vegetation Indices – Biophysical Parameters – Web Mapping

The service provides:

1. maps of vegetation indices (NDVI, NDWI) in sub-parcel level (pixel 10 and 20 m spatial resolution);
2. maps of biophysical parameters in sub-parcel level (pixel 10 or 20 m spatial resolution);
3. yield and crop residues maps (pixel 10 m spatial resolution);

The provided **C**** SM service** addresses to different user segments:

- **farmers** ; they can address crop stress early on and avoid yield damage that would arise if the situation was addressed later on;
- **agricultural insurance companies** ; provides them with continuous information of their portfolio exposure in order to have an estimation of the maximum reimbursement cost, in the case of an event, and assist them in better pre- and after disaster-related decision-making;
- **companies** , small and large scale **Agri-businesses** ; for improving the contract farming scheme and enabling sustainability advisers to continuously monitor the overall quality assurance of farmers&#39; (suppliers&#39;) agricultural practices, in order to improve the environmental performance of products, throughout their life-cycle;
- **policy makers** ; to assist policy makers in determining the performance of crops and crops&#39; varieties under different environments and base decisions on allocating and expanding crops and better planning crop suitability for future climate-resilience.

## Service Template API Overview

This section provides a very high-level summary of the Crop Status Monitoring API:

Crop Monitoring Endpoints

- Monitor parcel
- Get parcel monitoring info

Farm Services Endpoints

- Yield and crop residues
- Get yield and crop residues info

## Requirements

Implementations of Crop Status Monitoring service require a number of parameters that are not included in the API. These are crop-related user input:

**Crop data**.

- The external user must **upload shp file of farm area** or **provide coordinates of the farm** in the reference World Geodetic System (WGS84);
- The external user must specify **crop type (wheat, maize, soybean, cotton and sunflower)**;
- The external user must specify **sowing date** ;

## **Monitor parcel/NDVI and Biophysical Parameters**

Crop growth monitoring is the process of monitoring the crop status from emergence to harvest. Among the vegetation indices, NDVI is the one most often used for monitoring the environmental conditions (e.g. grassland status, land degradation, desertification, and drought) all over the world. In the CMS Service, NDVI is calculated and produced, along with the crop specific biophysical parameters LAI, chlorophyll concentration and above ground biomass. Biophysical parameters are crop specific for **wheat** , **maize** , **soybean** , **cotton** and **sunflower**. Monitoring of crop growth assists in early detection of stress factors due to water and nutrient deficiencies, as well as biotic stresses due to insect attacks and disease infestations.

From the wide spectrum of biophysical parameters available worldwide, LAI describes the area of leaves that cover a specific area of ground (unitless or m2/m2). Biomass corresponds to the produced mass of the dry aboveground biomass per unit of area that is produced by the crop. Chlorophyll content is the concentration of chlorophyll a and b per cm2 of leaf area. Crop biomass accumulation is calculated using Sentinel-2 imagery and is expressed in t/ha. Leaf Area Index (m2/m2) and chlorophyll content (g/m2) are calculated on Sentinel-2 imagery and are presented per-parcel and sub-parcel level. The parameters are updated regularly, based on the temporal resolution and the condition (e.g. cloudiness) of the satellite imagery. All the above mentioned products of Crop Status Monitoring service are presented on maps through the multi-device application component (web-based or mobile).

The CSM Service calculates chlorophyll content, LAI and Biomass using crop-specific, empirical models based on vegetation indices. The models were calibrated and validated against available in-situ data for wheat, maize, soybean, sunflower and cotton in order to identify optimal combinations of VIs-crops that provided the best fit between calculated and measured data.

## **Get parcel monitoring info**

_The service will provide:_

1. **maps of NDVI and biophysical parameters** over a registered parcel updated every time a satellite image is available. Every product is accompanied with a legend showing the values of NDVI, LAI, chlorophyll content and above ground biomass.
2. **the products are accompanied with graphs** depicting the variation throughout the growing season.

## _Table of Variables_

| _ **Type of Data** _ | _ **Parameter** _ | _ **Spatial Resolution** _ | _ **Temporal Resolution** _ | _ **Source** _ | _ **Range** _ |
| --- | --- | --- | --- | --- | --- |
| _EO data_ | _NDVI_ | _10 m_ |
- _Less than 5 days depending on cloudiness_
 | _AgroApps API_ | _[-1, 1]_ |
| _EO data_ | LAI | _10 or 20 m_ | _AgroApps API_ | _Crop specific_ |
| _EO data_ | Chlorophyll content | _10 or 20 m_ | _AgroApps API_ | _Crop specific_ |
| _EO data_ | Biomass | _10 or 20 m_ | _AgroApps API_ | _Crop specific_ |

##

## **Yield and crop residues**

Accurate and real-time estimation of crop yield on regional, national and international scale is becoming increasingly important in both developed and developing countries. In particular, crop yield estimation may play a fundamental role in supporting policy formulation (e.g. EU Common Agriculture policy) and decision-making in agriculture (e.g. management of food shortage). Yield forecasting can be performed with statistical and deterministic models that require a significant number of input variables. The estimation of crop yield before harvest presents benefits for farmers. Farmers can calculate their expected income and decide if they are going to sell or stock their crop yield.

A simple method for estimating crop yield is by multiplying biomass with harvest index. Biomass is a term for all organic material that stems from plants (including algae, trees and crops). Biomass is produced by green plants converting sunlight into plant material through photosynthesis. Harvest index describes plant capacity to allocate biomass (assimilates) into the formed reproductive parts. However, under non-optimal growing conditions, estimates of crop growth and yield using crop growth models often are inaccurate. NDVI has been considered to be a useful way for crop yield assessment models using various approaches from simple integration to more complicated transformation.

The Crop Status Monitoring provides crop yield estimation and crop residues biomass estimation in parcel and sub parcel level. Crop-specific Yield (expressed in Mg/ha or tn/ha) is estimated using Sentinel-2 imagery for the calculation of above ground crop biomass and the crop related harvest index (HI). The crop residues are calculated from the final yield and the harvest index. As long as there are values of biomass per pixel, yield is calculated and visualized per pixel in maps after sowing. The values of the yield and crop residues one month before the estimated harvest, are the values of importance. Therefore, the visualization of the yield one month before harvest will be the final yield and the estimation will stop at this point.

## **Get yield and crop residues info**

_The service will provide:_

1. **Yield and Crop Residues maps** over a registered parcel updated every time a satellite image is available. Every product is accompanied with a legend showing the values of yield and crop residues.
2. **the products are accompanied with graphs** depicting the variation throughout the growing season.

## _Table of Variables_

| _ **Type of Data** _ | _ **Parameter** _ | _ **Spatial Resolution** _ | _ **Temporal Resolution** _ | _ **Source** _ | _ **Range** _ |
| --- | --- | --- | --- | --- | --- |
| _EO data_ | Yield Estimation | _10 m_ | _Less than 5 days depending on cloudiness_ | _AgroApps API_ | _Crop specific_ |
| _EO data_ | _Crop Residues Estimation_ | _10 m_ | _AgroApps API_ | _Crop specific_ |

Technical References