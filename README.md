
# Rossmann Store 



Rossmann operates over 3,000 drug stores in 7 European countries. 
Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. 
Store sales are influenced by many factors, 
including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, 
the accuracy of results can be quite varied.






![Logo](https://www.arkadpecs.hu/fileadmin/user_upload/GLOBAL/brand_stores/logos/rossmann.jpg)


## Data Description

| Variable                       | Descriptions                                                      |
| -------------------------------- | ------------------------------------------------------------ |
| Id                               | An id that represents a (store, date) duple within the test set|
| Store                            | A unique id for each store                                   |
| Sales                            | The turnover for any given day                          |
| Customers                        | The number of customers on a given day                       |
| Open                             | An indicator for whether the store was open: 0 = closed, 1 = open |
| Stateholiday                     | Indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. A = public holiday, b = easter holiday, c = christmas, 0 = none |
| Schoolholiday                    | Indicates if the (store, date) was affected by the closure of public schools |
| Storetype                        | Differentiates between 4 different store models: a, b, c, d  |
| Assortment                       | Describes an assortment level: a = basic, b = extra, c = extended |
| Competitiondistance              |Distance in meters to the nearest competitor store           |
| Competitionopensince[month/year] | Gives the approximate year and month of the time the nearest competitor was opened |
| Promo                            | Indicates whether a store is running a promo on that day        |
| Promo2                           | Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating |
| Promo2since[year/week]           | Describes the year and calendar week when the store started participating in promo2 |
| Promointerval                    | Describes the consecutive intervals promo2 is started, naming the months the promotion is started anew. E.G. "Feb,may,aug,nov" means each round starts in february, may, august, november of any given year for that store |


## Documentation

[Kaggle](https://www.kaggle.com/c/rossmann-store-sales)


## Authors

- [@ikauann](https://www.linkedin.com/in/kauan-souza-913518213/)


