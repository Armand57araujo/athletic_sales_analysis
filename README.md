# athletic_sales_analysis

## Technology Used 

| Technology Used | Resource URL | 
| ------------- |:-------------:| 
| Python | [https://www.w3schools.com/python/python_reference.asp](https://www.w3schools.com/python/python_reference.asp) | 
| Git | [https://git-scm.com/](https://git-scm.com/) | 
| Pandas | [https://www.w3schools.com/python/pandas/default.asp](https://www.w3schools.com/python/pandas/default.asp)

## Description 
In this project I analyzed sales data to gain insight into which cities in the U.S. sold the most athletic wear over a two year period. Next I determined which retailers had the greatest total sales for athletic wear, and of those retailers which sold the most women's athletic footwear. Lastly, I ascertained what day and week had the highest sales for women's athletic footwear.

## Code Example 

<----  #1  ----->


     womens_footwear_sold = womens_athletic_footwear_sales.pivot_table(
     index=['retailer', 'region', 'state', 'city'],
     values='units_sold',
     aggfunc='sum',
     margins=False
     )

      womens_footwear_sold.rename(columns={'units_sold': 'Womens_Footwear_Units_Sold'}, inplace=True)


      womens_footwear_sold = womens_footwear_sold.sort_values(by=['Womens_Footwear_Units_Sold'], ascending=False)


      womens_footwear_sold.head(5)


<------ #2 ------>


     pivot_table_sales = womens_athletic_footwear_sales.pivot_table(
     index='invoice_date', 
     values='total_sales', 
     aggfunc='sum'  # Aggregating to sum total sales for each date
     )

      pivot_table_sales.rename(columns={'total_sales': 'Total Sales'}, inplace=True)


     pivot_table_sales.head(10)

<----- #3 ------->

     pivot_table_sales = womens_athletic_footwear_sales.pivot_table(
    index='invoice_date', 
    values='total_sales', 
    aggfunc='sum'
)


      pivot_table_sales.rename(columns={'total_sales': 'Total Sales'}, inplace=True)


     daily_sales = pivot_table_sales.resample('D').sum()

     daily_sales_sorted = daily_sales.sort_values(by='Total Sales', ascending=False)

     daily_sales_sorted.head(10)

     df['line_cost'] = df['unit_cost'] * df['qty'] + df['shipping_price']
     df.head()

     df['profit'] = df['total_price'] - df['line_cost']

     df.head()  



## Challenges
This project wasn't too bad once I had a better grasp of .groupby and pivot_table(). It was challenging keeping the syntax straight just simpally because it was new. But overall the thought process was very straightforward and logical. 



## Learning Points 
I have a new new best friend. Google: Best bud, w3 Schools: Lovely lady friend, ChatGPT: My BOY, GeeksForGeeks: Bombshell, and last but certainly not least, the staff of AskBCS.... there are no words... Friends... For Life....


## Author Info
Armand Araujo
Age: 29
Location: Las Vegas, NV

 
* [LinkedIn](https://www.linkedin.com/in/armand-araujo-a82ba2291/) 
* [Github](https://github.com/Armand57araujo) 


## Credits 

W3 Schools, GeeksforGeeks, chatgpt, MDN