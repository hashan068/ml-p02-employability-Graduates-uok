# ml-p02-employability-for-Graduates
# Graduate Student Employability Analysis : Leveraging Machine Learning Clustering to Identify Patterns and Recommendations

// ## Analysis of Employability for Graduates of University of Kelaiya

### 1	Introduction
#### 1.1	Importance of Analyzing Graduate Employability
For Students: It helps them understand their career prospects after graduation. This information can be used to make informed decisions about their studies, such as choosing a program aligned with job market demands or developing relevant skills through internships or extracurricular activities.
For Universities: It helps universities assess the effectiveness of their programs in preparing students for the workforce. This information can be used to improve curriculum, career services, and overall student preparation.
For Employers: It helps employers understand the skills and qualifications of graduates from different universities. This information can be used to develop targeted recruitment strategies.
For Policymakers: It helps policymakers understand the skills needed in the workforce and identify any skills gaps. This information can be used to develop policies that support higher education and workforce development.

#### 1.2	Objectives of Analyzing Graduate Employability
Measure employment rates: What percentage of graduates find employment within a specific timeframe after graduation?
Identify in-demand skills: What skills are most sought-after by employers for graduates in specific fields?
Compare universities: How does the employability of graduates from the University of Kelaniya compared to other universities?
Identify areas for improvement: Are there any programs or faculties with lower than expected employment rates? If so, what are the reasons?

#### 1.3	Scope and Methodology
##### 1.3.1	Scope
The scope of this study encompasses the exploration of graduate employability of the Graduates of the University of Kelaniya through a process of Data collection, data preprocessing, and clustering techniques to identify specific employability statistics of the graduates. It involves the analysis of various factors that contribute to graduate employability, such as academic qualifications, skills, internships, previous employment, and the 5 capital of the Graduate Employability which are the Human capital, social capital, Cultural capital, psychological capital, and Identity capital. The study aims to identify patterns and clusters within the dataset that can provide insights into different profiles of employable graduates. Additionally, the scope includes evaluating the effectiveness of ML clustering in understanding and predicting graduate employability trends.
##### 1.3.2	Methodology
Data Collection / Data Source:
Graduates from various academic department and faculties of the university of Kelaniya are subjected to a survey which includes all the necessary data for the scope of the project.
Data Preprocessing: 
Pre-processed the data to handle missing values, outliers, and inconsistencies. Also feature engineering was used to find the capital score values of each human capital, social capital, cultural capital, psychological capital, agentic capital and identity capital to extract meaningful features from the raw data.
Exploratory Data Analysis: 
The survey data reveals valuable insights into the demographic composition of the respondents. Gender-wise distributions, ethnicity distributions, academic department, degree specific, and G.C.E A/L examination region/district related data was plotted to identify the dataset more thoroughly. 
ML Clustering: 
Clustering algorithms such as K-means, to partition the dataset into distinct groups (cluster) based on similarities in the selected features. Principle component Analysis is used to reduce the dimensionality of the features and hence obtain a 2d and 3d clustering visualizations based on the data.


### 2	Five Forms of Capital and Graduate Employability
2.1	Human Capital
Human capital refers to the knowledge, skills, and abilities that individuals possess, which can be used to enhance their productivity and earning potential . In the context of graduate employability, human capital is crucial as it encompasses the education, training, and experiences that graduates have acquired during their studies and previous work experiences. Employers often seek graduates with strong technical skills, problem-solving abilities, and critical thinking skills, which are all aspects of human capital .
2.2	Social Capital
Social capital refers to the networks, relationships, and connections that individuals have, which can be leveraged to access resources and opportunities . For graduates, social capital can be developed through networking, internships, and involvement in extracurricular activities. These connections can provide access to job opportunities, mentorship, and valuable industry insights, all of which can enhance graduate employability .
2.3	Cultural Capital
Cultural capital refers to the cultural knowledge, skills, and dispositions that individuals possess, which can be used to navigate and succeed in various social and professional contexts . For graduates, cultural capital can include their understanding of workplace norms, communication styles, and professional etiquette. Employers often value graduates who can demonstrate cultural awareness and the ability to adapt to different organizational cultures .
2.4	Identity Capital
Identity capital refers to the personal characteristics, values, and beliefs that individuals possess, which can shape their sense of self and influence their career choices and trajectories . For graduates, identity capital can include their self-awareness, resilience, and adaptability, all of which can contribute to their employability. Employers often seek graduates who can demonstrate a strong sense of identity and the ability to navigate the complexities of the job market .
2.5	Psychological Capital
Psychological capital refers to the positive psychological resources that individuals possess, such as self-efficacy, hope, optimism, and resilience . For graduates, psychological capital can be crucial in navigating the job search process, managing stress, and adapting to new work environments. Employers often value graduates who can demonstrate a positive and proactive mindset, which can contribute to their overall employability .In conclusion, the five forms of capital – human, social, cultural, identity, and psychological – are all important in shaping graduate employability. By developing and leveraging these forms of capital, graduates can enhance their chances of securing meaningful employment and achieving long-term career success.

 
 
### 3	Data Collection and Analysis
3.1	Data Source
Data Source primarily includes categorical data, with 78 columns and 203 rows. This includes more specific columns such as Gender, Faculty, academic department, degree program, ethnicity, and other features related to the five graduate employability capitals of human capital, social capital, cultural capital, psychological capital, agentic capital and identity capital related columns. Data Source included mixed language data entries which were in Sinhala and English. Missing values were present in the dataset as per respondents' entries. There were some irrelevant columns such as Timestamp, Student No., and record ID etc. These irrelevant data columns were later ignored and dropped during the data pre-processing stage of the analysis.

 3.2	Data Preprocessing
The data preprocessing steps included:
3.2.1	Handling Missing Values:
Imputing with Most Common Value:
For a column 'Col' with missing values, the most common value 'most_common_val' was calculated as:
most_common_val = df['Col'].mode()[0]
Then, missing values were replaced with the most common value:
Imputing with Placeholder for Employment Columns:
For employment-related columns like 'Job_Satisfaction', missing values were replaced with a placeholder 'Irrelevant' for individuals who were not employed:
3.2.2	Encoding Categorical Variables:
Label Encoding:
For ordinal categorical variables like 'Rating' with values ['Poor', 'Average', 'Good', 'Excellent'], label encoding was applied using sklearn's LabelEncoder:
This would assign numerical labels like 0 for 'Poor', 1 for 'Average', 2 for 'Good', and 3 for 'Excellent'.
One-Hot Encoding:
For nominal categorical variables like 'Department', one-hot encoding was applied. 
This would create new binary columns for each unique value in 'Department', e.g., 'Department_Sales', 'Department_Marketing', etc., with 1 indicating the presence of that value and 0 otherwise.
By handling missing values and encoding categorical variables appropriately, the data was prepared for further analysis and modeling.
3.2.3	Feature engineering: 
New features were created by combining related columns and aggregating scores for different skill categories (e.g., Computer Literacy Score, Communication Skills Score).
Communication Skills Score: There are 8 columns related to communication skills, with the same value range of 1 to 5.
The maximum possible total score would be 8 * 5 = 40.
The Communication Skills Score is calculated as:
Communication_Skills_Score = (col1 + col2 + ... + col8) / 40 * 100
 
### 4	Exploratory Data Analysis 
4.1	Visualizations and descriptive statistics
Demographic Profiles
The survey data reveals valuable insights into the demographic composition of the respondents. 
Gender-wise distribution of the respondents
 
Ethnicity distribution of the respondents


Geographical Analysis
The survey data covers respondents from various geographical regions and examination districts. 
 
 
These regional variations could be attributed to discuss potential factors contributing to the observed regional differences in employability.

Academic Performance Analysis
Academic performance is a crucial factor influencing employability.
Distribution of Academic merits based on the respondents.
 
The employment percentages across different academic merit categories reveal a clear pattern.
 
Figure 1 Overall Distribution of Academic Merits by the Graduates
 
Degree Program and Department Analysis
The survey respondents represent a diverse range of degree programs and academic departments. 
Distribution of the Degree program preference according to the respondents.
 


Distribution of the Academic department according to the respondents.
 
LinkedIn Profile
In today's professional landscape, having an online presence is increasingly important. 
 
Internship Experience.
Practical experience through internships is often considered valuable for enhancing employability.
 
 
### 5	Clustering Approach
#### 5.1	K-means clustering.
1. Identifying Groups with Similar Employability Outcomes:
K-means clustering excels at grouping data points with similar characteristics. In this case, it can group undergraduates based on their demographics and graduate capital (skills, networks, etc.). These groups might represent students with High vs. Low employability chances.
2. Understanding Relationships Between Factors:
By analyzing the characteristics of each cluster, you can see how demographics and graduate capital interact to influence employability. For example, a cluster with high social capital (strong networks) but low human capital (technical skills) might have moderate employability, suggesting networks can compensate to some extent.
3. Simplifying Complex Data:
K-means reduces complex data into a smaller number of clusters, making it easier to identify trends and patterns. This can be helpful for universities or policymakers to understand the overall employability landscape for their students and develop targeted support programs.

##### 5.2	Determining the optimal number of clusters
5.2.1	Silhouette analysis.
•	Evaluate the silhouette score using the silhouette_score() function.
•	Silhouette scores are used to study the distance between clusters.
•	compare the silhouette score of each value of k, from 2 through 15
 
•	Silhouette scores near 1 indicate that samples are far away from neighbouring clusters. 
•	Scores close to 0 indicate that samples are on or very close to the decision boundary between two neighbouring clusters.
•	The plot indicates that the silhouette score is closest to 1 when the data is partitioned into five clusters.
•	Therefore, based on the silhouette analysis, it can be concluded that the optimal number of clusters for this dataset is five.
 
6	Clustering Results and Interpretation

6.1.1	Visualizing clusters
This scatter plot depicts the results of the K-means clustering algorithm applied to the data after dimensionality reduction using Principal Component Analysis (PCA). Each data point is represented by a marker, color-coded according to its assigned cluster. The red markers indicate the centroids of each cluster. However, due to overlapping data points, the clusters may not be clearly distinguishable in this two-dimensional representation. 
  
The use of three dimensions in this visualization provides a more comprehensive representation of the data compared to a two-dimensional plot. By employing Principal Component Analysis (PCA) to reduce the dimensionality of the data, we capture the most significant patterns and variations while retaining as much information as possible.
 
This visualization illustrates the results of applying K-means clustering with Principal Component Analysis (PCA) to the data. Each data point is represented as a marker in a three-dimensional space, with its position determined by its principal components. The colour of each point corresponds to its assigned cluster, as determined by the K-means algorithm. Additionally, black markers represent the centroids of each cluster. This visualization provides a clear understanding of how the data points are grouped into distinct clusters in a reduced-dimensional space.
 
6.2	Cluster Profiling
The analysis conducted on the dataset reveals insightful information regarding employment trends among individuals.
Firstly, the overall employment percentage across all individuals in the dataset is determined to be 71.43%. This figure signifies the proportion of individuals currently employed out of the total population under consideration.
Furthermore, upon delving deeper into the data, it becomes evident that employment percentages vary across different clusters within the dataset. Each cluster represents a distinct subgroup of individuals characterized by unique attributes or characteristics.
 
Upon examine the employment distribution within each cluster, it is observed that:
1.	Cluster 0 exhibits the highest employment rate among its members, with 85.11% of individuals currently employed.
2.	Cluster 1 follows closely behind, with 71.43% of individuals employed.
3.	Cluster 2 demonstrates a robust employment percentage of 83.72% among its members.
4.	Cluster 3 portrays a lower employment rate, with only 44.44% of individuals currently employed.
5.	Cluster 4 displays a moderate employment percentage, with 68.25% of individuals holding current employment positions.
 
6.2.1	Graduate Capital within Clusters

Cluster	Computer_Literacy_Score	Communication_Skills_Score	Attitude_Score	Social_Capital_Score	Cultural_Capital_Score	Identity_Capital_Score	Psychological_Capital_Score	Agentic_Capital_Score
0	31.35	22.39	23.78	21.54	16.52	19.06	22.06	20.12
1	47.14	47.14	75.36	82.50	91.90	61.43	94.76	95.51
2	43.41	40.00	41.74	35.87	36.59	37.21	49.92	46.18
3	31.67	27.43	22.50	26.11	32.87	32.22	35.00	28.41
4	39.74	30.79	28.81	29.48	24.81	28.95	29.84	24.49
 
visualization of the relationship between average scores across different capitals and employment percentage across various clusters, facilitating the analysis of cluster characteristics in terms of both skill scores and employment outcomes.
Each row in the heatmap represents a specific cluster, while each column corresponds to a particular type of capital. The color intensity within each cell indicates the average score for the respective capital type within the corresponding cluster. Additionally, numerical annotations provide precise values for better interpretation. 

 
The clusters are ordered based on their employed percentage, with those exhibiting higher employment percentages positioned towards the top of the heatmap. This ordering enables easy comparison between clusters in terms of both capital scores and employment percentages.
 
Cluster 1 (High Employability, High Skill Scores):
Leadership Development Programs: Individuals in Cluster 1 exhibit strong skill sets across various domains. Implement leadership development programs to nurture their leadership abilities and prepare them for managerial roles.
Advanced Skill Training: Offer advanced training workshops or courses to further enhance their existing skills and stay ahead of industry trends.
Mentorship Opportunities: Provide mentorship opportunities with experienced professionals to guide and support individuals in their career growth and development.
Cluster 2 (High Employability, Moderate Skill Scores):
Targeted Skill Enhancement: Identify areas of improvement based on skill gaps and offer targeted skill enhancement programs to strengthen weaker areas, such as Psychological Capital and Agentic Capital.
Professional Certification Programs: Encourage participation in professional certification programs relevant to their field of expertise to enhance credibility and career prospects.
Soft Skills Workshops: Conduct workshops focused on soft skills development, such as leadership, teamwork, and communication, to complement technical skills and improve overall effectiveness in the workplace.
Clusters 0 and 4 (Moderate Employability, Mixed Skill Scores):
Strengths Assessment: Conduct comprehensive assessments to identify individual strengths beyond skill levels, including personal attributes, values, and motivations.
Career Path Exploration: Provide career counseling services to help individuals explore various career paths aligned with their strengths and interests.
Networking Opportunities: Facilitate networking events or platforms to connect individuals with industry professionals and potential employers, enhancing their visibility and career opportunities.
Cluster 3 (Low Employability, Mixed Skill Scores):
Intensive Skill Development Programs: Develop intensive skill development programs tailored to address specific skill gaps identified within the cluster, focusing on both technical and soft skills.
Career Transition Support: Offer career transition support services, including resume building workshops, interview preparation sessions, and job search assistance, to facilitate re-entry into the workforce.
Industry Partnerships: Establish partnerships with local businesses and organizations to create internship or apprenticeship opportunities, providing hands-on experience and enhancing employability prospects.
 
6.2.2	Gender Representation within Clusters
 

Cluster 3 has a notably higher proportion of females (86.11%) compared to males (13.89%), but a lower employment rate, with only 44.44% of individuals currently employed. This suggests that a highly imbalanced gender distribution may be associated with lower employment rates.  
GCE (A/L) Examination District within Clusters
 
The provided data illustrates the distribution of GCE (A/L) Examination District and employability percentages within different clusters. Each cluster represents a distinct group of individuals with varying characteristics, including their educational background and employment status.
Cluster 0: 
The majority of individuals are from Colombo (38.30%) and Rathnapura (12.77%) districts, with a relatively high employability percentage of 85.11%. This cluster includes individuals with diverse backgrounds, potentially reflecting a mix of urban and suburban populations with relatively higher employability rates.
Cluster 1: 
The distribution of GCE (A/L) Examination District is more evenly spread across different districts, with significant representation from Colombo (35.71%) and Gampaha (21.43%) districts. The employability percentage in this cluster is 71.43%, indicating a relatively high employability rate among individuals from diverse districts.
Cluster 2: 
Colombo (27.91%) and Gampaha (11.63%) districts have higher representation in this cluster, along with notable proportions from Kegalle and Rathnapura districts. The employability percentage is 83.72%, suggesting a strong correlation between district distribution and employability rates within this cluster.
Cluster 3: 
Gampaha district has the highest representation (25.00%) in this cluster, followed by Kandy, Matale, and Nuwara Eliya districts. The employability percentage is 44.44%, indicating a lower overall employability rate compared to other clusters, despite significant representation from certain districts.
Cluster 4: 
Colombo (22.22%) and Kandy (14.29%) districts have notable representation in this cluster, along with significant proportions from Kalutara and Kurunegala districts. The employability percentage is 68.25%, reflecting moderate employability rates among individuals from diverse districts within this cluster.


 
7	Insights
Regional Employability Patterns:
Employability rates vary across different GCE (A/L) Examination Districts, suggesting the influence of factors such as educational opportunities, industry presence, and economic conditions. Clusters with higher representation from specific districts may exhibit distinct employability patterns.
Human Capital and Employability Correlation:
There is a positive correlation between human capital attributes (skills) and employment percentage, indicating the importance of investing in the development of various capital types to improve employment outcomes.
Higher capital scores (skills) generally lead to better employment prospects.
External Factors and Employability:
While higher capital scores are beneficial, other external factors may also influence employment outcomes, as seen in Cluster 1, which has high employability despite moderate skill scores.
Variations Across Clusters:
Employment rates differ significantly across the identified clusters, with Cluster 0 having the highest employment (85.11%) and Cluster 3 having the lowest (44.44%).
Clusters exhibit varying patterns in human capital attributes (skills), academic performance, demographics, and other factors that may influence employability.
Need for Tailored Support:
Clusters with lower capital scores and employment percentages may require tailored interventions and support mechanisms to enhance their employability and socio-economic well-being.
Gender Imbalance and Employability:
Cluster 3 has a skewed gender ratio (higher females) and lower employability, suggesting a potential link between gender distribution and employment outcomes.
Interpreting Cluster Characteristics:
Clusters can be interpreted and compared based on factors such as employability rates, human capital attributes (skills), academic performance, demographics (gender, ethnicity), degree programs, and academic departments.
Identifying the factors that contribute to the variations in employability across clusters can help design targeted interventions and support strategies.
 
8	Recommendations
Based on the analysis and insights provided in the document, the following recommendations are listed:
Cluster 1 (High Employability, High Skill Scores):
Implement leadership development programs to nurture their leadership abilities and prepare them for managerial roles.
Offer advanced training workshops or courses to further enhance their existing skills and stay ahead of industry trends.
Provide mentorship opportunities with experienced professionals to guide and support individuals in their career growth and development.
Cluster 2 (High Employability, Moderate Skill Scores):
Identify areas of improvement based on skill gaps and offer targeted skill enhancement programs to strengthen weaker areas, such as Psychological Capital and Agentic Capital.
Encourage participation in professional certification programs relevant to their field of expertise to enhance credibility and career prospects.
Conduct workshops focused on soft skills development, such as leadership, teamwork, and communication, to complement technical skills and improve overall effectiveness in the workplace.
Clusters 0 and 4 (Moderate Employability, Mixed Skill Scores):
Conduct comprehensive assessments to identify individual strengths beyond skill levels, including personal attributes, values, and motivations.
Provide career counseling services to help individuals explore various career paths aligned with their strengths and interests.
Facilitate networking events or platforms to connect individuals with industry professionals and potential employers, enhancing their visibility and career opportunities.
Cluster 3 (Low Employability, Mixed Skill Scores):
Develop intensive skill development programs tailored to address specific skill gaps identified within the cluster, focusing on both technical and soft skills.
Offer career transition support services, including resume building workshops, interview preparation sessions, and job search assistance, to facilitate re-entry into the workforce.
Establish partnerships with local businesses and organizations to create internship or apprenticeship opportunities, providing hands-on experience and enhancing employability prospects.
Targeted Interventions: 
If a strong positive correlation is observed, stakeholders may consider implementing targeted interventions to address gender-based disparities in employment outcomes and promote equitable access to employment opportunities across clusters.
Further Research: 
Conduct further research to explore the underlying factors contributing to the observed relationship and identify specific mechanisms through which gender composition influences employment outcomes within clusters.








 
9	Conclusion
In conclusion, this study employed machine learning clustering techniques to analyze graduate employability data from the University of Kelaniya. The analysis revealed several valuable insights into the factors influencing employment outcomes among graduates. The K-means clustering algorithm identified five distinct clusters within the dataset, each exhibiting varying patterns in terms of employment rates, human capital attributes (skills), academic performance, demographics, and other relevant factors. The analysis highlighted a positive correlation between higher skill scores across different capitals (e.g., human capital, social capital, psychological capital) and increased employability prospects. However, the findings also indicated that while strong capital scores are advantageous, other external factors may influence employment outcomes, as exemplified by Cluster 1, which demonstrated high employability despite moderate skill scores. Moreover, the study uncovered potential links between gender imbalance and employment rates, with Cluster 3 exhibiting a skewed gender ratio towards females and lower overall employability. This finding suggests the need for targeted interventions to address gender-based disparities and promote equitable access to employment opportunities. By understanding the unique characteristics and patterns within each cluster, stakeholders such as universities, policymakers, and employers can devise tailored strategies and initiatives to enhance graduate employability. These may include curriculum updates, skills development programs, career counseling services, industry partnerships, and advocacy for supportive policies. Overall, this study demonstrates the value of data-driven approaches in understanding complex factors influencing graduate employability and informing evidence-based decision-making to improve employment outcomes for graduates.
 
10	References

1.	Pham, T., Tomlinson, M. and Thompson, C. (2019). Forms of capital and agency as mediations in negotiating employability of international graduate migrants. Globalisation, Societies and Education, 17(3), pp.394–405. doi:https://doi.org/10.1080/14767724.2019.1583091.

11	Appendices 

Google Colab notebook that contains code for performing cluster analysis.
https://colab.research.google.com/drive/1LHP9tmrqxN4fH4IW0nB8ZqArXLUBwwx-?usp=sharing
