# Anomaly Detection in Petroleum Pipelines 🛢️

## Problem 🎯
Detect the **position** of anomalies in petrol pipelines using data generated from a maintenance device called "Pig" that travels inside the pipeline.
- Detecting **Wielding**
- Visualising **Metal loss** and or dents

<img src='Images/process.gif'/>

### About Data 📋
- Data is in **binary** format saved in - 'captured_data.bin' file, captured from 84 sensors for 50_000 milliseconds
- Pigs directly captured/stored data in `binary(.bin)` format

### Data Analysis Insights with Understanding 📈
- Data varies with time i.e., **Time Series data**
- We can also see a **repeated pattern** of **flux** at times in all sensors.
   
### Techniques 🛠️
- **Normalised** data for comparison purposes.
- **Aggregated(sum)** all sensors to amplify anamoly.
- The **z-score** method is effective here in comparison to the *Inter-Quartile Range* method as per the observations.
- Edge detection using **Sobel**, OpenCV.

### Different Approaches Used 🔄
- [x] Approach 1: Using Various Statistical methods like InterQuartile Range, Z-score, etc.     
- [x] Approach 2: By Filtering anomalies with Sobel Derivatives, Image Processing in OpenCV.

[Approach 1](Notebooks/anamoly-detection.ipynb) | [Approach 2](Notebooks/anamoly-detection-using-image.ipynb)


## Output 📄

|Pipe | Number|Outlier Position|
|-----|-------|----------------|
|0 | 0 | 624 |
|1 | 0 | 678 |
|2 | 1 | 5070 |
|3 | 1 | 5117 |
|4 | 1 | 8252 |
|5 | 1 | 8286 |
|6 | 2 | 11397 |
|7 | 2 | 14990 |
|8 | 3 | 15001 |
|. | . | ... |
|. | . | ... |
|. | . | ... |

## Conclusion 📝
We can detect the position of welded iron and also visualise the metal loss.

> ### Little Business Understanding
> - Many pipes are welded together to form a pipeline.
> - Pigging is a concept in pipeline maintenance that involves the use of devices known as pigs, which clean pipelines and are capable of checking pipeline conditions from inside.
> - Pigs inspect pipelines by receiving magnetic flux from the walls of the pipe.
> - Applications of Pigging include oil & gas, lube oil, chemical plants and hygienic applications such as pharmaceutical or food, etc.

> <div style="display:flex"><img src='Images/petrol-pipe.jpg' width=200 height=200/>
> <img src='Images/pig.jpg' width=200 height=200/></div>

> - Each "Pig"(here) has 84 sensors in circumference that capture data every millisecond while travelling in pipes. So this becomes a `time series problem` where each traversal time for each independent pipe is 5_000 milliseconds.
