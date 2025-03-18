# global-IT-and-business-consulting-firm
a global IT and business consulting firm renowned for its expertise in IT solutions and highly experienced consultants. To stay competitive in the rapidly evolving technology landscape, thre organization regularly analyzes data to identify emerging and future skill requirements.

## Roles and responsibilities:
Contribute to this initiative by collecting data from diverse sources and identifying trends for this year's report on in-demand skills. One key source for analysis will be the latest Developer Survey, a comprehensive dataset offering insights into the global developer community.
iInitial task is to gather data on the most sought-after programming skills from various sources, including:

#### Job postings:

  - Training portals
  
  - Developer surveys, such as the latest Stack Overflow Developer Survey
  
  - Analyze it to identify key insights and trends. 

#### Trends: 

  - Which programming languages are most in demand?
  
  - Which database technologies are currently most sought after?
  
  - Which Integrated Development Environments (IDEs) are the most popular?
  

#### Working process:

  - Scraping internet websites, accessing APIs, and working with datasets like the latest Stack Overflow Developer Survey in various formats such as .csv files, Excel sheets, and databases.
  
  - Apply data-wrangling techniques to prepare the data for analysis.
  
  - Employ statistical techniques to analyze the data, identifying key trends and insights. 
  
  - Synthesize findings using IBM Cognos Analytics to create a dashboard that visualizes the results. 
  
  - Share insights through a presentation, showcasing your storytelling and data analysis skills.

# DATA PREPARE
## Accessing APIs

#### Install the required libraries
```
!pip install requests
!pip install pillow
```

#### Requests in Python
```
# import libraries
import requests
import os 
from PIL import Image
from IPython.display import IFrame

# get data from website ibm.com
url='https://www.ibm.com/'
r=requests.get(url)

