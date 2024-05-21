# typing-workflow
A workflow made in Orange 3.22, that uses LR (Linear Regression) to predict my WPM (Words Per Minute).

The dataset consists of 100 consecutive TypeRacer games (done in two days), and its numerical features are as follows:
* Race ID (more races can lead to gradual decline or sudden rise in WPM)
* Words (unlike TypeRacer, I also counted words less than 5 characters)
* Characters (including spaces)
* Mistakes
* Accuracy
* Time
* Points (alternate measuring of performance done by TypeRacer)
  
As expected, its only class is the WPM, and it is continuous (not discrete).

Linear Regression turned out to work the best for this kind of problem, and adding more features led to a steady decrease in RMSE (Root Mean Square Error).

![image](https://github.com/ViveTheModder/typing-workflow/assets/93151014/4e55a697-7b54-4edd-bcb4-300bc6fb7650)

Normalizing the data did not do much, which is why I did not include it in the workflow.

Neither did expanding the dataset. I started out with 25 races, then 50, then 100. It led to slight increases in RMSE, if anything.


Given the range of WPM being 50 (from 92 to 142), an RMSE of 3.706 would mean a deviation in prediction by 1.853, roughly 2 WPM.

So, typically speaking, my predictions would be wrong by 2 WPM (either 2 more or 2 less than intended). 

At most, it would be wrong by 11 WPM.

![image](https://github.com/ViveTheModder/typing-workflow/assets/93151014/5d2206f9-aaea-4239-a004-8e7482fede04)

Here is a preview of the actual & predicted WPM, alongside the aforementioned features.
