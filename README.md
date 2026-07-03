# Empowering Urban Planners through Generative AI for Geospatial Analytics: A Case Study of Cognitive Complexity
This repository contains the detailed information of the practical exercises refered in the Case Study section included in the "Empowering Urban Planners through
Generative AI for Geospatial Analytics: A Case Study of Cognitive Complexity" paper. 

Through a sequence of logically structured prompts, we will illustrate three real-world analytical exercises: (1) the visualization of traffic incident concentrations, (2) the estimation of cycling incidents, and (3) the quantitative modeling of a cyclist risk index based on urban infrastructure. This division is fundamental to guiding professionals from basic to specialized analyses. Working in phases helps them understand the processes and adjust the complexity of the analyses, prevents cognitive overload for the LLM, and ensures the stability and transparency of the process.

## Exercise 1. Visualization of traffic incident concentration

This initial exercise serves as the foundational phase of the spatial analysis workflow, focusing exclusively on data preparation and baseline mapping. 
This exercise is designed to stablish essential data structures by applying initial tasks of data cleaning and exploratory spatial visualization.

Through the following natural language prompt, the AI is instructed to act as a spatial analysis expert using Python. 
The LLM is directed to read GeoJSON files containing traffic incident data, to standardize the Coordinate Reference System, to identify high-concurrency hotspots and to generate a map.

## Exercise 2. Estimation of cycling incidents 

This second exercise elevates the analytical complexity of the workflow by transitioning from baseline visualization to relational spatial coincidence analysis. Building upon the standardized parameters established in the first phase, this exercise utilizes sequential prompting to direct the LLM through a more sophisticated data processing pipeline, specifically targeting the spatial interaction between existing urban cycling infrastructure and traffic incidents. The operation is methodically divided into step-by-step processes to ensure the stability of the model's outputs.

## Exercise 3. Quantifying Cyclist Safety via Risk Index Modeling

This final exercise serves as the culmination of the spatial analysis methodology, advancing the geoprocessing workflow from descriptive spatial coincidence to predictive quantitative modeling and spatial enrichment. To systematically manage the ingestion of external datasets and the programmatic execution of custom mathematical algorithms, the operation is structured into progressive analytical stages. The primary objective is to compute the spatial frequency of cycling incidents alongside trip-generating locations (Points of Interest) that intersect with specific road network segments and existing cycling infrastructure. By synthesizing these enriched topological variables, the workflow ultimately generates a dynamic and highly localized custom risk assessment model.


