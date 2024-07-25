# PythonPandasGameSale
This is a Portfolio project 

Author: Dominik Scibor

Website:

LinkedIn: www.linkedin.com/in/dominik-andrzej-scibor-5b48b267



A portfolio project using dataset from kaggle

https://www.kaggle.com/datasets/amoghrrao2/video-games-list/data

Pc Game analysis
We will take a look at:
1) Which Publisher has released most titles
2) Which developer has create most titles
3) What year had most titles released
4) What genre is most popular 
5) Why year 2007 has most sales? 


# First look at our data
![image](https://github.com/user-attachments/assets/d4abfb8e-1841-41a7-9bd7-c2ac439081b3)

 Time for cleaning:
 ![image](https://github.com/user-attachments/assets/cf1ecb96-f9ee-4d82-82d0-00b669c0a68d)

Quick look at statistics of our data:

![image](https://github.com/user-attachments/assets/3c6ba864-0832-4d06-9e30-90c7e8a08eb7)

We want to check publishers and see which one has most released titles.
``` python
top10 = (data['publishers'].value_counts()).iloc[:10]
top10.plot(kind='bar')
```
![image](https://github.com/user-attachments/assets/778fd4c7-9b5a-40ff-a04b-14f31f9cff0f)
# As we can see Electronic Arts has most titles released, following by Ubisoft and Activision.

## Now we want to take a look at developers:

``` python
top10 = (data['developers'].value_counts()).iloc[:10]
top10.plot(kind='bar')
```
![image](https://github.com/user-attachments/assets/c4f5fc99-e56e-48d5-8708-b55b434df664)

EA Canada has most games created.

## What year has the most releases?
``` python
print("Entries for each year :")
data["released"].value_counts().to_frame().iloc[:10]
```
As we can see, in 2007 we had 272 releases on PC
##Last statistic we want to see is about genres
``` python
top10 = (data['genres'].value_counts()).iloc[:10]
top10.plot(kind='bar')
```
![image](https://github.com/user-attachments/assets/0819f147-a547-4683-b161-e0dc5bd9f160)

# "Shooter" is the most popular genre on PC

Now we want to wrap it up and analyse why year 2007 had most releases
First I want to have data with only shooter games
``` python
data_copy = data.copy()
data_copy = data[data['genres'] == 'Shooter']
data_copy

```
How does it look if we see popular shooter developers?

![image](https://github.com/user-attachments/assets/6ed1632d-710b-42e6-a7d1-b7c11c184ce5)

As we can see, "EA Canada" is not listed in the top 10 developers within "Shooter" genre despite being the most popular developer overall.

Let's answer the last question, why did 2007 have so many titles released?
``` python
top10 = (data_copy['released'].value_counts()).iloc[:10]
top10.plot(kind='barh')
```
![image](https://github.com/user-attachments/assets/bd339712-7ea8-4e91-8e1c-f64fe212ef00)

 The year 2007 had the most titles released, and the reason for that is that shooter games had the most released that year.




