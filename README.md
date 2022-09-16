![](RackMultipart20220705-1-ruigrg_html_70e3b217e6f91606.png)

# ATLAS Service Template Specification

# Name: Crop Status Monitoring

# Author(s): AgroApps (AGA)

_The &quot;__Crop Status Monitoring&quot; ATLAS Service Template_

This service will deliver a number of indicators for crop status monitoring.

## INTRODUCTION

The **Crop Status Monitoring (CSM) Service Template**, is a crop monitoring module that provides crop monitoring and farming service products, through the use of validated algorithms. The aim of the **CSM Service Template** is to provide farmers with information on their crops&#39; health status, through a biophysical proxy. Another aim is to provide estimations of the expected yield and crop residues. The CSM service template can help farmers identify anomalies in plant performance during the growing season.

The **CSM Service Template** will provide crop growth, yield and crop residues information in parcel and sub parcel level and will enable farmers to keep an eye on their crops&#39; status **from emergence through harvest**. Local deviations of the calculated parameters could imply the occurrence of abiotic and/or biotic stress in crops. Indirectly, crop growth monitoring helps in delineating different management zones at sub-parcel level, that are otherwise invisible to the naked eye, for variable rate application of crop protection products (CPPs) or fertilizers.

The provided **CSM Service Template** addresses to different user segments:

- **farmers** ; they can address crop stress early on and avoid yield damage that would arise if the situation was addressed later on;
- **agricultural insurance companies** ; provides them with continuous information of their portfolio exposure in order to have an estimation of the maximum reimbursement cost, in the case of an event, and assist them in better pre- and after disaster-related decision-making;
- **companies** , small and large scale **Agri-businesses** ; for improving the contract farming scheme and enabling sustainability advisers to continuously monitor the overall quality assurance of farmers&#39; (suppliers&#39;) agricultural practices, in order to improve the environmental performance of products, throughout their life-cycle;
- **policy makers** ; to assist policy makers in determining the performance of crops and crops&#39; varieties under different environments and base decisions on allocating and expanding crops and better planning crop suitability for future climate-resilience.

## Service Template API Overview

This section provides a summary of the Crop Status Monitoring API endpoints:

**Indices List**

- **Description**: Returns a list of all the available service indices.
- **Input**: No path and/or query parameters or request body required.
- **Output**: An enumeration of strings, denoting index names or the description of the encountered error (in case something goes wrong) in JSON format.

**Indices Search**

- **Description**: Returns a list of the dates (within a user specified range) for which the requested field growth indices have been calculated, or all requested dates and available indices, in case the service cannot provide such information.
- **Input**:
	1. Path parameter: 
		- the field URN.
	2. Request body, containing: 
		- the indices of interest, 
		- the start date of the interval of interest and
		- the end date of interest (if omitted, current date is assigned to it).
- **Output**: A list of the dates for which the requested field growth indices have been calculated along with the Download URL or the description of the encountered error (in case something goes wrong) in JSON format.



##


