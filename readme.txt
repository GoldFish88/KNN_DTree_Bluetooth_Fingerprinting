=== Bluetooth Fingerprinting with EDA ===
Dataset: Bluetooth Low Energy (BLE) RSSI Dataset
Source: UCI Machine Learning Repository
Author: Kristian James Guinto (s3826723)

=== Description ===

This notebook contains data prepartion, EDA and modelling using KNN and Decision Tree to perfrom Bluetooth fingerprinting using the BLE RSSI Dataset. 

To use this, just run the notebook.

The notebook are divided into parts identified by markdown labels:

* Data Prepation
* Data Exploration
     * Propagation of Signal in Space
     * RSSI Readings on Grid Locations
     * Exploration in Time
     * Exploration of relationship of different variables
* Modelling
     * Feature Extraction
     * Grid Search
     * K-Folds Cross Validation
          * Using Raw RSSI
          * Using Moving Average RSSI
     * Effect of increasing the window size

=== Custom Plot Functions ===

Most of the plots were customized to fit the needs and these were converted into functions for ease of use. 

* plot_Signal2Space (beacon)
     - This function computes the mean of valid RSSI readings from a specific beacon and plots plots these values on their corresponding location. This function expects a string parameter representing the beacon of interest, e.g. 'b3002', 'b3001'. 

* plot_Signals(location)
     - This function first selects only the columns with values greater than -200 for a given location label. Next, it converts -200 to null values then plots each column on the x-axis forming a dot plot of the valid readings for the beacons. This function expects a string parameter representing the locaiton of interest, e.g. 'J04', 'L05'.

* plot_RSSIinTime(beacon, x_start, x_end = 0)
     - This function plots the RSSI and its corresponding distance to beacon from x_start to x_end. This function expects 3 parameters, a string to represent the beacon, and integers for x_start and x_end. The start and end parameters are used to select only a slice of the entire data. The x_end has a default value of 0, but this value will be converted to the length of the data available to plot the entire data.