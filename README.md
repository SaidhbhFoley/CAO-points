# CAO Points and PyPlot 
## CAO Points
### CAO Points Overview
The CAO Project Jupyter Notebook contains an overview of how to load CAO points information from the CAO website and appropriate plots and other visualisations of the data.
The notebook contains a brief overview of the background on the CAO, including a breakdown of the points that can be achieved based on the grades achieved in the Leaving Certificate.
### Importing the Required Libraries
Several different packages were used throughout this notebook, including Regular Expressions, HTTP Requests, Datetime, Pandas, urllib requests, Seaborn (this was downloaded but not used in the analysis), NumPy, and Matplotlib.pyplot.
### Obtaining the Data
The first step in this project was to obtain the data from the CAO website for the years 2021 to 2017 inclusive. As each years data was offered in different formats it required different mechanisms for downloading. The data from 2021 was obtained using HTTP requests, 2020 was obtained through URL requests, the next 3 years were all available on the CAO website in a pdf format. This meant manually obtaining and cleaning the data. Reproducible steps are given for each year to allow others to obtain the data following the same steps I sued.
### CLeaning the Data
The data obtained from the CAO required cleaning after it was obtained. I choose to remove the #, * symbols. The # symbol represented Test/Interview/Portfolio/Audition and the * symbol represented that not all on this points score were offered places. AQA was also removed from the data this stands for All Qualified Applicants. There were several instances of +matric in the data so this was also removed.
The logic for removing # symbol was I was focused on points only and did not have the time to examine the points and then the relationship between the points and #.
### The Data
This notebook is then broken up into each year. 
#### 2021
The first year examined is 2021 using the dataframe df2021 containing the Code, Title, R1 Points and R2 Points. The dataframe is then examined using the commands df.describe and df.info. As these indicated that the data were objects and not floats the data from R1 Points was converted to float. The dataframe was then examined to ascertain how prevailant NaN was in the data. It was found that 72% of R2 Points were NaN, therefore R2 Points were excluded from further analysis as the data were too patchy to conclusively state any inferences. Once it was decided that the R2 Points were to be excluded a new dataframe was created, df2021_r1, containing Code, Title and R1 Points. Upon examining this dataframe using ,max() it was shown the highest course points was 1028, as the highest points that can be achieved in the Leaving Certificate is 625 all courses above 625 were removed. The logic for the removal of these courses is that the points could not be differentiated from the points and the points obtained from either Test/Interview/Portfolio/Audition. 
#### 2020
The next year examined is 2020 using the dataframe df2020. The dataframe is then examined using the commands df.describe and df.info. As these indicated that the data were objects and not floats the data from R1 Points was converted to float. The dataframe was then examined to ascertain how prevailant NaN was in the data. It was found that 77% of R2 Points were NaN, therefore R2 Points were excluded from further analysis as the data were too patchy to conclusively state any inferences. Once it was decided that the R2 Points were to be excluded a new dataframe was created, df2020_r1, containing Code, Title and R1 Points. Upon examining this dataframe using ,max() it was shown the highest course points was 1088, as the highest points that can be achieved in the Leaving Certificate is 625 all courses above 625 were removed. The logic for the removal of these courses is that the points could not be differentiated from the points and the points obtained from either Test/Interview/Portfolio/Audition. 
#### Examining 2021 and 2020
As previoulsy stated in the Introduction as the data are not synonomous across all years examined in this notebook the years 2021 and 2020 are grouped together, as they both have R1 Points.
The dataframes from both years, df2021_r1 and df2020_r1, were merged creating the new dataframe df2020_2021_r1. I first plotted this entire dataframe however it was too busy and data could not be extrapolated in a quick manner visually. Therefore I chose to focus on the courses with the highest and lowest points. I did this using .nlargest and .nsmallest.
From the bar charts it is clear that for the 10 highest courses on offer the points for each course increased in points from 2020 to 2021. The 10 lowest courses on offer overall decreased in points from 2020 to 2021 with the exception of two courses which increased slightly in points required.
### 2019
After comapring the years 2020 and 2021 the next section of the data to be examined is the year 2019.
In this section the dataframe df2019 used to examine the data. The dataframe is examined using the commands df.describe and df.info. As these indicated that the data were objects and not floats the data from R1 Points was converted to float. The dataframe was examined to ascertain how prevailant NaN was in the data. It was found that <2% of Mid Points were NaN, therefore these were removed as they made up only a small fraction of the data overall. EOS points were not focused on in this analysis as EOS indicates the points required the year previous. Therefore Mid was chosen for analysis, this is the median points required for entry into a given course. Once it was decided that the EOS Points were to be excluded a new dataframe was created, df2019_r1, containing Code, Title and Mid Points. Upon examining this dataframe using ,max() it was shown the highest course points was 1073, as the highest points that can be achieved in the Leaving Certificate is 625 all courses above 625 were removed. The logic for the removal of these courses is that the points could not be differentiated from the points and the points obtained from either Test/Interview/Portfolio/Audition. 
### 2018
In this section the data from 2018 was examined using the dataframe df2018. The dataframe is examined using the commands df.describe and df.info. The dataframe was examined to ascertain how prevailant NaN was in the data. It was found that <3% of Mid Points were NaN, therefore these were removed as they made up only a small fraction of the data overall. EOS points were not focused on in this analysis as EOS indicates the points required the year previous. Therefore Mid was chosen for analysis, this is the median points required for entry into a given course. Once it was decided that the EOS Points were to be excluded a new dataframe was created, df2018_r1, containing Code, Title and Mid Points. Upon examining this dataframe using ,max() it was shown the highest course points was 1045, as the highest points that can be achieved in the Leaving Certificate is 625 all courses above 625 were removed. The logic for the removal of these courses is that the points could not be differentiated from the points and the points obtained from either Test/Interview/Portfolio/Audition. 
### 2017
In this section the data from 2017 was examined using the dataframe df2017. The dataframe is examined using the commands df.describe and df.info. The dataframe was examined to ascertain how prevailant NaN was in the data. It was found that <2% of Mid Points were NaN, therefore these were removed as they made up only a small fraction of the data overall. EOS points were not focused on in this analysis as EOS indicates the points required the year previous. Therefore Mid was chosen for analysis, this is the median points required for entry into a given course. Once it was decided that the EOS Points were to be excluded a new dataframe was created, df2018_r1, containing Code, Title and Mid Points. Upon examining this dataframe using ,max() it was shown the highest course points was 1068, as the highest points that can be achieved in the Leaving Certificate is 625 all courses above 625 were removed. The logic for the removal of these courses is that the points could not be differentiated from the points and the points obtained from either Test/Interview/Portfolio/Audition. 
#### Examining 2019, 2018 and 2017 Data
As previoulsy stated the data are not synonomous across all years examined in this notebook the years 2019, 2018 and 2017 are grouped together, as they all contain Mid Points.
In order to merge three dataframes first I created a new dataframe containing 2017 and 2018, which I then merged with the data from 2019 creating df2017_2018_2019_r1. It was dicovered when I attempted to merge the dataframes for each year togther that the years 2017 and 2018 contained spaces in the Code, therefore these were stripped from the data in order to merge the years.
Again I focused on the courses with the highest and lowest points, based off of 2019's data. I did this using .nlargest and .nsmallest.
From the bar charts it is clear that for the 10 highest courses on offer the points for each course increased in points from 2018 to 2019. The 10 lowest courses on offer overall decreased in points from 2017 to 2019 with the exception of four lowest courses which only showed either a slight decrease of remained the same as the points required for 2017. 
### The Top Five Universities 
I choose to examine the point requirements for the top five universities in Ireland:
    1. Trinity College Dublin
    2. University College Dublin
    3. National Univeristy of Ireland Galway
    4. Univeristy College Cork
    5. Dublin City University
I looked at the 10 most in demand courses for these universities from 2021 to 2017, to examine if there was trend in the popularity of courses offered by these universities over the years. As I was not extrapolating data from the points but observing the most in demand courses I did not group the years as previously done but instead focused on all years in this section. 
For Trinity College Dublin only 2 courses appeared in the top 10 courses each year but 6 courses appeared in 4 out of 5 years.
For UCD 7 courses appeared in the top 10 courses each year and only 1 course appeared in 4 out of 5 years.
For NUIG only 3 courses appeared in the top 10 courses each year with 2 courses appearing in 4 out of 5 years.
FOR UCC 6 courses appeared in the top 10 courses each year and only 1 course appeared in 4 out of 5 years.
For DCU 5 courses appeared in the top 10 courses each year with 2 courses appearing in 4 out of 5 years.
### Conclusion
The data indicates a general increase in the points required for the courses with the highest points requirements. For the top univeristies in Ireland there is a trend showing the most in demand courses appear in the highest points for all five years examined. Had the data been synonomous a clearer picture may have emerged of an overall increase in the points required to gain entry to the top courses. As I was only able to exmaine 2021 and 2020 and then separetky exmaine 2019, 2018 and 2017's data there is no way to definitively state that the points increased from 2017 to 2021. With only two years of synonomous data I also could not accurately predict if the points for the highest courses would indeed increase for 2022, this would have been nice addition to the analysis of this data.

## PyPlot
### PyPlot Overview
In the Jupyter Notebook for PyPlot I will give an overview of the matplotlib.pyplot Python package and an in depth explanation of three interesting plots from matplotlib.pyplot.
### PyPlot Introduction
The matplotlib.plot is a state-based interface to matplotlib. It provides an implicit was of plotting and is mainly intended for interactive plots and simple cases of plotting.
There are many different plots available with matplotlib, such as:
    1. Line Plot
    2. Histogram
    3. Scatter Plot
    4. 3D Plot
    5. Polar Plot
    6. Contour Plot
PyPlot is an API for Python's matplotlib that effectively makes matplotlib a viable open source alternative to MATLAB.
PyPlot provides matplotlib with two key features:
    - A MATLAB-style interface, allowing those familiar with MATLAB to adopt Python more easily
    - Staefullness, which means PyPlot stores the state of an object when it is first plotted.

The plots I will look into in this notebook are:
    - Histograms
    - Scatter plots
    - Pie Charts

### Histograms
A histogram is a graphical representation that organizes a group of data points into user-specified ranges. Similar in appearance to a bar graph, the histogram condenses a data series into an easily interpreted visual by taking many data points and grouping them into logical ranges or bins.

Bins are also sometimes called "intervals", "classes", or "buckets". Choice of bin size has an inverse relationship with the number of bins. The larger the bin sizes, the fewer bins there will be to cover the whole range of data. With a smaller bin size, the more bins there will need to be. If you have too many bins, then the data distribution will look rough, and it will be difficult to discern the signal from the noise. On the other hand, with too few bins, the histogram will lack the details needed to discern any useful pattern from the data.

Histograms are commonly used in statistics to demonstrate how many of a certain type of variable occurs within a specific range. They are good for showing general distributional features of dataset variables.

A density curve, or kernel density estimate (KDE), is an alternative to the histogram that gives each data point a continuous contribution to the distribution. In a KDE, each data point adds a small lump of volume around its true value, which is stacked up across data points to generate the final curve. The shape of the lump of volume is the ‘kernel’, and there are limitless choices available. Because of the vast amount of options when choosing a kernel and its parameters, density curves are typically the domain of programmatic visualization tools. These can be added to Histograms for extra visualisation.

A good histogram can be a very quick way of accurately conveying the general shape and distribution of a data variable.

#### Histograms vs. Bar Charts

Both histograms and bar charts provide a visual display using columns, and people often use the terms interchangeably. More technically, a histogram represents the frequency distribution of variables in a data set. On the other hand, a bar graph typically represents a graphical comparison of discrete or categorical variables5.

Histograms visualise quantitative data or numerical data, whereas bar charts display categorical variables.

### Scatterplot

A scatterplot uses dots to represent values for two different numeric variables. The position of each dot on the horizontal and vertical axis indicates values for an individual data point. Scatter plots are used to observe relationships between variables.

Scatter plots’ primary uses are to observe and show relationships between two numeric variables. The dots in a scatter plot not only report the values of individual data points, but also patterns when the data are taken as a whole.

A scatter plot can also be useful for identifying other patterns in data. We can divide data points into groups based on how closely sets of points cluster together. Scatter plots can also show if there are any unexpected gaps in the data and if there are any outlier points.

Scatter plots show if there is any correlation between the variables. There are three types of correlation:

Positive Correlation: as one variable increases so does the other.
Negative Correlation: as one variable increases, the other decreases.
No Correlation: there is no apparent relationship between the variables.

### Pie Chart

A pie chart shows how a total amount is divided between levels of a categorical variable as a circle divided into radial slices. Each categorical value corresponds with a single slice of the circle, and the size of each slice (both in area and arc length) indicates what proportion of the whole each category level takes.

Pie charts have a fairly narrow use-case that is encapsulated particularly well by its definition. In order to use a pie chart, you must have some kind of whole amount that is divided into a number of distinct parts. Your primary objective in a pie chart should be to compare each group’s contribution to the whole, as opposed to comparing groups to each other. If the above points are not satisfied, the pie chart is not appropriate, and a different plot type should be used instead.

#### Pie Chart vs Bar Chart

Pie charts show how much each category represents as a proportion of the whole, by using a circular format with different-sized “slices” for different percentages of the whole. Bar graphs use a series of rectangular bars to show absolute values or proportions for each of the categories.

Pie charts and bar charts look strikingly different from one another, but from the perspective of somebody looking for the best way to display data, the key differences are the fact that pie charts can only show proportions and that bar graphs can display changes in quantities over time.

Below I will use data from worldometers on CO2 emissions14. I will use both a Pie Chart and a Bar Chart.

### Conclusion

In this notebook I have illustrate the ease of use PyPlot offers and some of the many plots it is possible to create.