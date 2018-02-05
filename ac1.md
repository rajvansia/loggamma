rvrv3

Raj Vansia 
# Exploratory Analysis AC1
I wanted to see which question had the most missing data. This can help with enhancing the survey to get a better response rate. I wanted to determine if there is a reason why so many people did not answer a particular question. According to the data I found the most unanswered question was “How much total rainfall did your city/region receive in 2016? (in inches)”, with 22 unanswered responses The least unanswered question was “What was the maximum temperature in your area yesterday?” , with only 2 unanswered. I hypothesizes that the rain fall question was not answered the most because it took the most effort to look up.  Below is a bar graph of the total counts of unandswered questions. 

![Imgur](https://i.imgur.com/ZD9uixa.png)

---------------------------------------

# Processing the Data 
To calculate the unanswered questions I needed to convert data with NAs to an empty string. This was done using the is.na function. 
```
ac1[is.na(ac1)]<-""
```
Then the count was taken for each empty value for every question. 

```
sum(ac1_$Rain == "")
```
I found this amusing that the biggest outlier of the data likes death metal as their music genre. I guess they like to create chaos!
```
1/21/2018 17:28:31	2.718281828	9999999999999999999999999		Death Metal	-100000	Facebook	99999999999
```

