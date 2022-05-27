# walmart_sales
Sales predictions based on external factors (temperatures, holidays, etc.)
# Identify Key Factors Affecting Weekly Sales
## Use analytic graphics to find which factors most affect sales outcomes. Then use predictive modeling to make future weekly sales predictions.

**Author**: Rija Voloder

### Business problem:

This project attempted to aid a company (Walmart) in identifying trends in weekly sales. The goal was to find any major factors that could be affecting weekly sales and to create a model that would allow for good predictions for future sales. 


### Data:
The project found a very strong correlation between dates and weekly sales. 


## Methods:
- The data was first analyzed for missing data. The data appeared to be clean and ready for use with no imputations necessary.
- A variety of visualizations were then performed on the data to derive some more specific insights on various factors affecting item sales. 
- The data was then split into training and target data using a train_test_split.
- Column selectors were used to select for numeric and categorical columns.
- A standard scaler and OneHotEncoder were instantiated and placed into two tuples along with the numerical selector and categorical selector.
- Four models were then built to predict data. 
- The first, a linear regression model, performed poorly on the data (evaluated based on r2 scores). The scores lied between 0.1 and 0.2.
- The second, a simple decision tree model, performed much better but was slightly overfit on the data with the train score being 1.0 and the test around 0.91. 
- The third model was a bagging regressor model which decreased the variance and improved performance on the testing data to around 0.936.
- The fourth model performed the best with a testing score around 0.940.
- Based on these bas results, I chose to hypertune the third and fourth models to see if I could get any improvement in performance. 
- After tuning the bagging model with n_estimators, performance increaased to a 0.940. 
- After tuning the random forest model with n_estimators, min_samples_split, and max_depth (using a GridSearchCV) the performance stayed about the same.
- Because both models were performing very similarly, I attempt to use the time (or duration of performance of the models) to choose a model. But this was also around the same performance.
- I then compared the Mean Absolute Error and the Mean Squared Error of the models and those were also around the same, one model performing slightly better in one category and the other performing slightly better in the other value.
- To finally choose a model, I decided to stay with the simple baseline Random Forest Model which was performing at a slightly better r value (0.9402 to 0.9400).

## Results:
The analysis conducted provided quite a few key observations from the data. It was identified that the biggest outlier in weekly sales (i.e. the highest weekly sales) usually occurred during holidays. In particular, we found that the weeks between Thanksgiving and Christmas were the best performing in sales and that the 3 to 4 weeks after Christmas were the worst performing throughout the year. In comparing the unemployment rate to each store, we found that there appeared to be a postive correlation between unemployment and store sales. The areas in which unemployment was the lowest were also the stores with the worse performing sales whereas those areas with higher unemployment performed very well. This confirms and shows that Walmart's target customer bas still lies within the poorer neighborhoods and that they have not been able to expand their reach to wealthier customers.  

The Random Forest model was chosen as the approprate model for predicting sales predictions. The r2 value of both the training and testing data were around 0.9922 and 0.9402 respectively, showing little variance and fairly low bias, a solid model overall. The mse and mae values were also very close for the training and testing data, showing good model consistency in predicting outcomes. 
### The images below show evidence of the above results:


#### Holidays and Weekly Sales



#### Item Category Sales

The categories with the highest performing items are "Household", "Fruits and Vegetables", and "Snack Foods".

<img width="403" alt="Item Type" src="https://user-images.githubusercontent.com/101893905/165899981-f0211047-dece-4d1f-8b9e-9369dff53f09.png">

## Recommendations:

From the analysis provided above and within the file, I would recommend that the company figure out exactly which items are the highest performers. It would then be a good idea to evaluate which components seem to be making those items outperform others. Is it something the company can control (their display, item visibility, etc.) or something that is linked more to the individual product (brand recognition, advertising, etc.). They can then act accordingly. It would also be wise to figure out why certain location types or store types seem to be performing better and try to implement some of those aspects in other stores or for other items (design, location selection, etc.). Any of these factors could lead to improved sales numbers in the future. 

The model is also able to provide predictions based on the current data and can be improved as more data is added. 


## Limitations & Next Steps:

The biggest limitation in this project is the lack of individual product name or description that would have allowed us to make further insights into causation of high or low performance. Missing data was also another challenge but was dealt with appropriately.

In the next steps, the individual items with high sales should be looked at and analyzed more deeply to find links and reasons for their high performance, concepts that can be carried over to other stores and items. The model should also be used to predict the sales of future items added to the store and to compare whether making certain changes do indeed created better performance and higher sales predictions for other "low performers".

### For further information


For any additional questions, please contact **rijavoloder@gmail.com**
**
