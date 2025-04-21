# 6140finalproject
# Identifying Social Media Hotspots Using Topological Data Analysis

This project explores how **Topological Data Analysis (TDA)** can be used to identify geographic **hotspots of social media engagement** from geotagged tweet data. We compare traditional clustering (DBSCAN) with a novel approach based on **SoftMapper**, which leverages persistent homology and fuzzy clustering to reveal deeper spatial patterns.

## 🌍 Overview

Social media has become a rich source of real-time urban and cultural information. In this project, we analyze the spatial distribution of tweets using:
- **DBSCAN**: a traditional density-based clustering algorithm.
- **SoftMapper**: a topological data analysis technique that uses persistent homology and fuzzy clustering to capture shape and connectivity in data.

Our goal is to discover and visualize **hotspots**—areas with high social media activity—while handling noisy and unevenly distributed data.

## 🔍 Methods

### DBSCAN (Density-Based Spatial Clustering)
- Uses **Haversine distance** to calculate proximity on a spherical surface.
- Parameters:
  - `eps = 10 km` (in radians)
  - `min_samples = 10`
- Classifies points as:
  - **Core points**, **Border points**, or **Noise**
- Captures dense, arbitrarily-shaped clusters but may over-fragment in high-density areas.

### SoftMapper (Topological Data Analysis)
- Computes a **persistence-based lens function**
- Discretizes the space into overlapping intervals
- Uses **Fuzzy C-Means** clustering to allow soft membership
- Constructs a **Mapper graph** representing connectivity between clusters
- Offers richer, more stable representations of sparse or complex regions

## 📊 Dataset

**[Multilingual Geo-Tagged Social Media Posts (by 123 World Regions)](https://www.kaggle.com/datasets/yachaytech/multilingual-geotagged-social-media-posts)**  
- 615,000 entries
- Global coverage across 123 regions
- Each entry includes a `(latitude, longitude)` coordinate
- Originally designed for text-based geolocation tasks; we instead analyze spatial patterns

## 📈 Results Summary

- **DBSCAN** detects over 5000 clusters; good for dense urban regions but limited in sparsity
- **SoftMapper** reveals transitions between regions, captures topological structure, and is better at identifying meaningful global patterns
- Visualizations show clear differences in how each method interprets space


