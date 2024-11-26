# the-MET-Museum-art-trends-analysis

# MET Art Trends Analysis  

## **Project Overview**  
This project addresses the question:  
**"How do different art departments at the Metropolitan Museum of Art compare in terms of their most prominent object types, shared artistic mediums, and artifact counts, and how do the departments with the largest collections align with public interest, as reflected by Wikipedia pageviews?"**  

### **Goals**  
The primary objective is to analyze the artwork collection of The Metropolitan Museum of Art (The Met) to uncover key patterns that differentiate departments based on:  
- Prominent object types  
- Artistic mediums  
- Artifact counts  

Additionally, the project integrates **Wikipedia pageviews for 2024** to align public interest trends with specific art departments and their artifacts.  

### **Key Questions**  
1. What are the top 10 art departments with the most artifacts?  
2. What are the top labels (art object types) associated with each department?  
3. Which departments are the most similar in terms of the art mediums they feature?  
4. How do Wikipedia page visits for the top 10 art departments reflect public interest in specific artworks or cultural topics?  

### **Supplementary Questions**  
- What are the most represented periods and cultures in each department?  
- What is the most common object type in each department?  
- Who are the artists with the highest number of works in each department?  

---

## **Analysis of Dataset**  

### **Datasets**  
#### 1. **The Met Dataset**  
A public domain dataset containing metadata for over **200,000 objects**, including images and metadata. Key tables include:  
- **Objects Table**: Contains details such as title, artist, culture, department, period, medium, and creation date.  
  - **Size**: 83.35 MB  
  - **Rows**: 200,074  
  - **Primary Key**: `object_id`  
- **Vision API Data Table**: Includes labels detected through computer vision analysis (e.g., dominant colors, landmarks).  
  - **Size**: 275.53 MB  
  - **Foreign Key**: `object_id` (links to the objects table).  
- **Images Table**: Contains URLs for digital access to images (not used in this project).  

#### 2. **Wikipedia Dataset**  
Pageview tables for **2015-2024**, detailing user interaction with Wikipedia pages.  
- **Key Columns**:  
  - `datehour`: When the page was accessed  
  - `wiki`: Language of the Wikipedia page  
  - `title`: Page title  
  - `views`: Number of views  
- **Size of 2024 Data**: 1.92 TB  

For this project, the **2024 pageviews table** is used to analyze public interest in the MET art departments by matching department names in the title column.  

### **Dataset Limitations**  
1. **Incomplete Metadata in The Met Dataset**:  
   - Certain fields like `dynasty`, `artist_display_name`, or `period` are missing or inconsistently labeled.  
2. **Naming Convention Misalignment**:  
   - Wikipedia uses underscores (`_`) in titles, while The Met dataset uses spaces, making direct joins challenging.  
3. **Size of Wikipedia Dataset**:  
   - Large file sizes necessitate careful query optimization to extract relevant data.  

---

## **Technologies Used**  
- **BigQuery**: For querying large datasets.  
- **SQL**: To perform analysis and create insights.  
- **Data Visualization**: Tools like Matplotlib for presenting trends and findings.  

---

## **How to Run the Project**  
1. **Set Up BigQuery**:  
   - Ensure access to The Met and Wikipedia datasets on Google BigQuery.  
2. **Clone the Repository**:  
   ```bash
   git clone https://github.com/yourusername/met-art-trends-analysis.git
   cd met-art-trends-analysis
   ```  
3. **Run Queries**:  
   - Use the provided SQL scripts in the repository to execute queries in BigQuery.  
4. **Analyze Results**:  
   - Export query outputs for further analysis or visualization.  

---

## **Insights and Results**  
- Identified the top 10 art departments by artifact count.  
- Mapped relationships between object types, periods, and cultures for each department.  
- Analyzed Wikipedia pageviews to highlight public interest trends related to The Met’s departments.  

---

## **Future Work**  
- Enhance data cleaning to address metadata inconsistencies.  
- Develop methods to automate Wikipedia and MET dataset integration.  
- Incorporate machine learning to predict future art trends and user engagement.  

---

## **Acknowledgments**  
- **MET Museum**: For the comprehensive art collection dataset.  
- **Wikipedia Pageviews Dataset**: For insights into public interest trends.  

---

## **Contributions**  
Contributions and feedback are welcome! Feel free to submit a pull request or open an issue for discussion.  

**License**: MIT License  
