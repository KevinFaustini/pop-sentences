#How does the features of a sentence influences its popularity ?

## Introduction

If you say something, odds are you want to be heard. This is even more true if you want to share ideas or opinions. If you believe in something and you want to be sure what you say reaches as many people as it can, then you may want to pay attention to what you say, or rather, how you say it. Should you use a long sentence ? With long words ? Should you use a lot of punctuation ? How could you maximize the reach of your ideas by only tweaking the intrinsic structure of what you say ?

## Data

Obviously we used the [Quotebank](https://github.com/epfl-dlab/Quotebank) dataset, but more specifically we focused on the year 2017 because we needed both recent and old data so we thought 2017 was a good compromise.
We also used a bit of data from Google Trend, especially to get speaker's popularity.

## Should you consider your options together or separatly ?

First thing we did, before even considering modeling, was observing, comparing and trying to find dependance relationships between our variables.
We measured the number of times a quotation appears in our dataset, the number of words in the quotation, its average word length, the longest word length ,the number of punctuation signs and the number of repeated words. We also used a log scale on some of these parameters which were skewed.

![heatmap](/graphs/heatmap1.png)

The only stand-out fact we see is that the hight the number of words in a sentence, the higher the humber of repeated words. This makes sense, especially considering we didn't remove stopwords. So basically, there is no clear dependence between our variables. However it could be interesting to look at our variables separatly ! 

![hist](/graphs/hist1.png)
![hist2](/graphs/hist_numWords.png)

Well, let's try modelling !

## Surely the least squares are gonna tell us something interesting!

We want to find how impactful are there features on ones quote popularity, and as such, we runned a few ordinary least squares models on our data. First we runned it as it is but we didn't really get good results : about 0.86 for the MSE. So we thought, perhaps if we only focus on popular quotes we could get something... Well, we used the quotes which are cited more than 100 times and we get some significantly better results : the MSE of our model droppesd to 0.382! This is good but still not enough...

## So... let's try more ! 

Since we couldn't find anything impactful, we tried engineering our features : add interaction terms, log transforms... Despite trying to add complexity, our results stay more or less the same. First we tried adding each possible second order interaction term, to see if this would improve our results, But no, our MSE doesn't really improve : 0.380 so an improvement of 0.002. Meh, not very useful ain't it...

## Still nothing, then let's try on more powerful models !


## Well, it seems that even powerful models can't explain our theories... so maybe we're not looking at the right things ?

## Still nothing ! Okay we need to go extreme mode then.


You can use the [editor on GitHub](https://github.com/KevinFaustini/pop-sentences/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.


