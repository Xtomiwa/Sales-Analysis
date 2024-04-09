# Company_Sales_Analysis

### Project Overview 

The aim of this project is to conduct an in-depth analysis of a company's sales dataset to gain valuable insights into the company's performance and profitability. By exploring various aspects such as item types, shipping durations, regional contributions, and profit margins, the project seeks to provide actionable recommendations for improving business operations and driving revenue growth. Through thorough analysis and visualization of the sales data, the project aims to empower decision-makers with valuable insights to make informed strategic decisions, optimize resource allocation, and enhance overall business performance.

### Data Source

Sales Data: The primary dataset utilized for this analysis is the "5000 Sales Record.csv", containing a list of 5000 sales records from an undisclosed company.

- [Link to data source](https://data.world/rc122681/sales-analysis/workspace/file?filename=5000+Sales+Records.csv)

  ### Tools
  Python(Jupyter)

 ### Data Cleaning

In the intital data preparion phase, I performed the following task:
1. Data loading and inspection.
2. Handling missing values.
3. Data Cleaning and Formatting.

 ### Exploratory Data analysis
 EDA involved in the sales data to answer key questions, such as 
 
  - Identifying the item type that generated the most profit and creating a measure to calculate profit.
  - Utilizing a visualization tool to determine the item type that yielded the highest profit
  - Analyzing the number of days it took to ship each item.
  - Using visualization tools to identify the regions contributing the most profit, facilitating targeted production strategies.  
  - Calculating the percentage profit margin for each item type to assess profitability.
  - Summing the profit by order priority to understand profit distribution across different priority levels.
  - Analyzing the profit trend of the company from 2010 till date

### Data Analysis 
Some Interesting code I worked with 😃

``` Jupyter(Python)
# To group the regions by profit, starting with the highest and ending with the lowest.
region_with_the_most_profit = df.groupby('Region')[['Profit']].sum().sort_values(by = 'Profit', ascending = False).reset_index(drop = False )
region_with_the_most_profit

# To visulaize the region that made the most profit
plt.figure(figsize=(20, 10))
ax = sns.barplot(x='Region', y='Profit', data=region_with_the_most_profit, order=region_with_the_most_profit['Region'].value_counts().index)
plt.title('Region With The Most Profit')

# Format the profit labels with commas
ax.yaxis.set_major_formatter(ticker.FuncFormatter(lambda x, _: locale.format_string('%d', x, grouping=True)))

# Annotate each bar with its value
for p in ax.patches:
    ax.annotate(locale.format_string('%d', p.get_height(), grouping=True), (p.get_x() + p.get_width() / 2., p.get_height()), ha='center', va='center', xytext=(0, 10), textcoords='offset points')

plt.show()
```

### Results 
![Most Profitable Item](https://github.com/Xtomiwa/Sales_Analysis/assets/112486285/3292c4dd-d063-41a7-b101-cedf1652861c)

- The bar chart above and the data show the item types that yielded the highest profit from 2010 till 2017. Cosmetics generated the highest profit, followed by Household items, Office Supplies, and Baby Food. This analysis highlights the product categories contributing significantly to the company's profitability over the specified period. Understanding the profitability of these item types is crucial for informed decision-making and strategic planning to optimize product offerings and maximize revenue
  
 ![Most Profitable Region](https://github.com/Xtomiwa/Sales_Analysis/assets/112486285/f7c732c0-b455-4f1a-b85e-7535e9084570)
- The bar chart above and the data reveal the regions that contributed the most profit from 2010 to 2017. Sub-Saharan Africa emerged as the top profit-generating region, followed by Europe, Asia, and the Middle East and North Africa. This analysis underscores the significant financial impact of these regions on the company's profitability during the specified period. Understanding the profitability of these regions is essential for strategic decision-making and resource allocation to capitalize on lucrative markets and drive sustainable growth.

![Profit Margin by Item Type](https://github.com/Xtomiwa/Sales_Analysis/assets/112486285/a575b4f1-3e47-41a9-9a5d-3375513dfa69)
- The bar chart above and the data reveal the profit margins for different item types. Clothes have the highest profit margin, followed by Cosmetics, Vegetables, and Baby Food. This analysis underscores the varying profitability levels across product categories and emphasizes the importance of understanding profit margins for informed decision-making and strategic planning. Leveraging these insights to optimize product offerings can enhance operational efficiency and foster competitive advantage in the market, ultimately driving sustained business growth and profitability.

![Profit Trend Over Time](https://github.com/Xtomiwa/Sales_Analysis/assets/112486285/3e2b95f0-605e-484f-a8ca-412f57c94a22)
- The analysis shows the profit trend from 2010 to 2017, revealing fluctuations in profitability over the specified period. Profit peaked in 2012, with a steady increase from 2010 to 2012. However, there was a slight decline in profit in 2013, followed by fluctuations in subsequent years. Notably, there was a significant drop in profit in 2017 compared to previous years. This trend underscores the dynamic nature of profitability within the company over the years. It emphasizes the necessity of closely monitoring profit trends to adapt to changing market conditions effectively. Understanding these fluctuations enables agile decision-making and facilitates strategic planning to navigate challenges and capitalize on opportunities for sustained business success.

### Insights
- The analysis reveals a clear hierarchy in profit generation among various item types from 2010 to 2017. Cosmetics emerge as the top-performing category, followed by household items, office supplies, and baby food. This hierarchy signifies consumer preferences and market dynamics, shedding light on potential growth areas and competitive advantages within the company's product portfolio. By leveraging these insights, businesses can tailor their product development, marketing strategies, and resource allocation to capitalize on high-profit item types, driving sustained profitability and market relevance. This underscores the significance of continuous monitoring and adaptation to evolving market trends for strategic decision-making and long-term success.

-  With an average shipping time of 25.0458 days, it appears that the shipping process takes a considerable amount of time on average. This may indicate potential inefficiencies or bottlenecks in the shipping process that could lead to customer dissatisfaction and increased operational costs. By comparing this average to industry standards or benchmarks, such as average shipping times for similar products or competitors, further insights can be gained into the company's shipping performance.

-  The analysis of profit generated by different regions unveils significant disparities in financial contributions from 2010 to 2017. Sub-Saharan Africa emerges as the highest profit-generating region, followed by Europe, Asia, and the Middle East and North Africa.This ranking underscores the diverse economic landscapes across regions and emphasizes the importance of market segmentation and targeted strategies for maximizing profitability. Understanding the underlying factors driving profitability in each region is essential for strategic decision-making and resource allocation to capitalize on emerging opportunities and mitigate risks. By leveraging these insights, businesses can tailor their market entry, expansion, and operational strategies to optimize returns and foster sustainable growth in diverse geographical markets. This highlights the critical role of data-driven analysis in informing informed decision-making and facilitating strategic agility in a dynamic global business environment.

-  The analysis of profit margins by item type reveals varying levels of profitability across different product categories. Clothes exhibit the highest profit margin, indicating potentially higher pricing or lower production costs compared to other items. Cosmetics and Vegetables also demonstrate strong profit margins, suggesting significant consumer demand or efficient production processes. Conversely, Meat and Office Supplies have comparatively lower profit margins, possibly indicating higher production costs or lower selling prices. Understanding these profit margin dynamics can inform pricing strategies, product development efforts, and resource allocation to optimize profitability and enhance overall business performance.

- The profit trend from 2010 to 2017 exhibits fluctuations, with profit peaking in 2012 and 2015 before experiencing a decline in 2017. These fluctuations may be influenced by several factors, including shifts in consumer preferences and purchasing behavior, intensified market competition, changes in economic conditions such as fluctuations in GDP or inflation rates, and alterations in industry regulations. Additionally, internal factors such as changes in pricing strategies, marketing efforts, and operational efficiency may also contribute to the observed trends. Understanding the multifaceted nature of these factors is crucial for devising adaptive business strategies that can effectively navigate market dynamics and sustain profitability over time.


