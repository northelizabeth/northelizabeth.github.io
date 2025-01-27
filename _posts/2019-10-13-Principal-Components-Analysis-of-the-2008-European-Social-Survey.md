---
layout: post
title: Princinpal Compenents Analysis of the 2008 European Social Survey
categories: [Statistics, PCA]
---
The European Social Survey is an instrument developed to annually assess social, political and moral attitudes across all 27, formerly 28, European nations. For this survey a cross sectional probability sample from 2008 was administered to all people aged 15 or over residing in private households. In the current sample, we are interested in only nine variables, three which assess attitudes toward immigration, and six which assess trust of governmental infrastructure. Because more than one question was asked to assess immigration attitudes and governmental trust, it is likely they will all hang together empirically. Here I will perform an orthogonal principal component analysis to answer the questions: Did the 2008 Eurpean Social Survey indeed measure attitudes toward immigration and trust of governental infrastructure?
```md
![](/images/pca1.png)
```
About the data:
The dataset intends to measure trust in the formerly 28 european countries. There are 9 questions that measure the level of trust on a scale from 1 to 10. Table 1 gives descriptive statistics of these. The variance information shows that while the top four variables have a higher value, the mean of most variables is around 5. Figure 1 also gives some correlation information about variables. There is a clear division into two parts, where two sets of four variables each are highly correlated with each other. What is surprising is that one TOG variable is not correlated with the other TOG variables, but is instead correlated with the ATI variables. PCA should be used to further investigate whether this variable is indeed measuring trust of governmental infrastructure, or instead if it is reflecting attitudes towards immigration. Assumption It is assumed all the data provided by the ESS are correct, that we are using non-standardized data, and PCA should be done given that the correlation matrix shows correlations between the variables. Method Application (Mean-Corrected Data) PCA is a variable reduction method which is used to identify if a smaller number of components can account for the variance within a set. In this case since all variables are metric (based on an interval scale from 1 to 10), mean-corrected data is more informative and can be analysed firstly. The standardized data can be also analyzed briefly in the next part.

Two groups of correlated variables are found based on the output of PCA. Nine variables are summarized into two principal components. The Kaiser criterion provides that one should retain any component with an eigenvalue above one, because that value will have contributed greater than its share of a single variable within the distribution. However, because non-standardized data are analyzed here, the Kaiser criterion as well as the proportion of variance accounted for rule are used. Looking at the proportions which are found by computing the eigenvalue for the component of interest divided by the total eigenvalues of the correlation matrix, we can see that variables one and two account for the most significant variance within the set, furthermore because none of the remaining values account for even 5% of the remaining variance, the first two components have been chosen as the principal components.

![](/images/pca2.png)

The output of PCA also gives the result of eigenvectors, which can be regarded as weights to calculate PC scores. 
```md
| Princinpal Components        |           |
|:-------------:|:-------------:|
| PC1     | 0.473399b+0.475382c+0.421763d+0.407364e+0.135135f+0.256875g +0.178642h+0.239684i+0.180187j | 
| PC2     | -0.300551b -0.368046c -0.098461d-0.067808e+0.179370f+0.361351g +0.362399h+0.534678i+0.424213j  |   
```
As the data is unstandardized data, the eigenvectors can not be used to label two principal components. In other words, structural loadings should be calculated and used to interpret two components. They can be quantified by using the Pearson correlation coefficients (See Table 3). The cutting value is set to 0.5. Hence, it can be found that PC1 is strongly correlated with all variables. It can be labelled with “General political trust”. As for PC2, it has a strong relationship with trstun(g), imbgeco(h), imueclt(i) and imwbcnt(j), which can be labelled with “Immigrant politics” or “Trust in foreign politics” based on the content of variables.

Figure 3 shows the biplot of PCA based on the mean-corrected data. It can be found that Denmark(DK), Finland(FI) and Norway(NO) which are located in the northern part of Europe trust politics highly. Compared to those countries, Bulgaria(BG) and Poland(PL) have a higher level of trust in foreign politics or immigrant politics. Russia(RU), Greece(GR) and Turkey(TR) have a lower level of all kinds of trust in politics.

![](/images/pca3.png)

Alternative Method (Standardized Data) Although the mean-corrected data is more informative, the standardized data is still analyzed here. Those results can be compared. Table 4 gives the result of eigenvalues. As the analysis is based on the standardized data, the rule of eigenvalue greater than 1 can be used to decide the number of principal components. Hence, there are two components and they can explain 85% variance.

The new output also gives the result of eigenvectors, which can be regarded as weights to calculate PC scores as well. PC1=0.336253b+0.313852c+0.371606d+0.376340e+0.261239f+0.351150g +0.333402h+0.323866i+0.317978j PC2=-0.400702b -0.418629c -0.294507d-0.272881e+0.127504f+0.195817g +0.364280h+0.382292i+0.411752j For the labelling part, Pearson correlation coefficients between two principal components and nine variables are also calculates here and Table 5 gives details about this. It can be found that there is no big difference for the first principal component compared to the result of mean-corrected data. It still can be labelled with “General trust in politics”. For the second principal component, the label name should be revised since it has a positive correlation with the last variable and negative correlation with the top two variables. It may be labelled with “political distrust” based on the contents of variables.

There is no huge difference between the biplots based on different datasets. As the label of the second principal component has been changed, the interpretation of biplot should also be changed slightly. For example, Bulgaria(BG) and Poland(PL) have a higher level of political distrust.

![](/images/pca4.png)

Conclusion The whole dataset includes 28 observations (countries) and 9 variables. Principal component analysis is conducted and the result shows that two principal components can be retained. The mean-corrected is analysed firstly since the scare of variables is the same and the standardized data is also analyzed, which can be compared. Based on the mean-corrected data, the first principal component is labelled with “General political trust” and the second principal is labelled with “Immigrant politics” or “Trust in foreign politics”. For the standardized data, they are labelled with “General political trust” and “Political distrust” respectively. It can be concluded that northern countries in Europe have a level in the political trust and some countries (such as Bulgaria(BG) and Poland(PL)) has a lower level in local political trust.
