# Understanding-Seaborn-Library
## Introduction
Seaborn is a Python data visualization library based on Matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics. Seaborn makes it easy to create complex visualizations with just a few lines of code, offering several built-in themes and color palettes to make the plots more visually appealing.

1. **Why Use Seaborn?**
      •	Ease of Use: Simplifies complex plotting with concise syntax.
   
      •	Statistical Visualization: Provides tools for statistical data visualization.
   
      •	Integration: Built on top of Matplotlib, integrates well with Pandas DataFrames.
   
      •	Customization: Offers advanced features and customization options for plots.
   
3. **Uses of Seaborn :**
   
      •	Exploratory Data Analysis (EDA): Visualizing distributions and relationships.
   
      •	Statistical Analysis: Plotting statistical models.
   
      •	Data Insights: Identifying patterns and trends in data.

4. **Seaborn Basics :**
   
      Importing Seaborn

        import seaborn as sns
        import matplotlib.pyplot as plt

      Built-in Datasets
   
      Seaborn has several built-in datasets that you can use for practice and examples.

        tips = sns.load_dataset("tips")

5. **Seaborn Plots :**
   
      **Relational Plots**
   
      Relational plots are used to visualize relationships between two or more variables.

      Scatter Plot

        sns.scatterplot(x='total_bill', y='tip', data=tips)
        plt.show()

      Line Plot

        sns.lineplot(x='size', y='total_bill', data=tips)
        plt.show()

      **Categorical Plots**

      Categorical plots are used to visualize data in categories.

      Bar Plot

        sns.barplot(x='day', y='total_bill', data=tips)
        plt.show()

      Count Plot

        sns.countplot(x='day', data=tips)
        plt.show()

      Box Plot

        sns.boxplot(x='day', y='total_bill', data=tips)
        plt.show()

      Violin Plot

        sns.violinplot(x='day', y='total_bill', data=tips)
        plt.show()

      **Distribution Plots**

      Distribution plots are used to visualize the distribution of a dataset.

      Histogram

        sns.histplot(tips['total_bill'], bins=20, kde=True)
        plt.show()

      Kernel Density Estimate (KDE)

        sns.kdeplot(tips['total_bill'], shade=True)
        plt.show()

      **Joint Plot**

      Joint plots combine scatter plots and histograms.

        sns.jointplot(x='total_bill', y='tip', data=tips, kind='scatter')
        plt.show()

      **Matrix Plots**

      Matrix plots are used to visualize data matrices.

      Heatmap

        flights = sns.load_dataset("flights")
        flights_pivot = flights.pivot("month", "year", "passengers")
        sns.heatmap(flights_pivot, annot=True, fmt="d", cmap="YlGnBu")
        plt.show()

      Clustermap

        sns.clustermap(flights_pivot, cmap="coolwarm", standard_scale=1)
        plt.show()

6. **Customizing Plots :**
   
      Seaborn offers several options for customizing plots.

      Setting Styles

        sns.set_style("whitegrid")

      Custom Color Palettes

        sns.set_palette("pastel")

      Adding Titles and Labels

        sns.scatterplot(x='total_bill', y='tip', data=tips)
        plt.title('Total Bill vs Tip')
        plt.xlabel('Total Bill')
        plt.ylabel('Tip')
        plt.show()

      Adjusting Figure Size

        plt.figure(figsize=(10, 6))
        sns.scatterplot(x='total_bill', y='tip', data=tips)
        plt.show()

      Saving Plots

        sns_plot = sns.scatterplot(x='total_bill', y='tip', data=tips)
        figure = sns_plot.get_figure()
        figure.savefig("output.png")

7. **Statistical Estimation :**
   
      Seaborn can estimate and plot the data with confidence intervals.

      Estimating with Bar Plot

        sns.barplot(x='day', y='total_bill', data=tips, ci="sd")
        plt.show()

      Linear Regression Model

        sns.lmplot(x='total_bill', y='tip', data=tips)
        plt.show()

8. **Pair Plots :**

      Pair plots are useful for exploring relationships between multiple variables.

        sns.pairplot(tips)
        plt.show()

9. **Facet Grids :**
    
      Facet grids allow you to create multiple plots based on subsets of your data.

        g = sns.FacetGrid(tips, col="time")
        g.map(sns.histplot, "total_bill")
        plt.show()

      Advanced Facet Grids

        g = sns.FacetGrid(tips, col="sex", hue="smoker")
        g.map(plt.scatter, "total_bill", "tip", alpha=.7)
        g.add_legend()
        plt.show()
        


