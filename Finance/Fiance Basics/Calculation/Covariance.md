### Covariance (协方差)

**Covariance** measures the degree to which two variables change together. In finance, it’s commonly used to assess the relationship between the returns of two assets.

#### Covariance Formula

For two sets of values,$X = \{x_1, x_2, x_3, \ldots, x_n\}$ and $Y = \{y_1, y_2, y_3, \ldots, y_n\}$, with means $\bar{x}$ and $\bar{y}$​:
$$\text{Cov}(X, Y) = \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})$$
Where:

- $x_i$and $y_i$​ are each individual value in sets $X$ and $Y$,
    
- $\bar{x}$ and $\bar{y}$​ are the means of $X$ and $Y$,
    
- $n$ is the total number of pairs.
    

The covariance will be positive if the variables tend to increase or decrease together, and negative if one tends to increase when the other decreases.

#### Example

Suppose we have the returns for two stocks, Stock A and Stock B, over four days:

- Stock A: \[2%, 3%, 5%, 6%]
    
- Stock B: \[1%, 4%, 4%, 5%]
    

Steps to calculate covariance:

1. Find the means of each stock: $\bar{x} = 4$ for Stock A and $\bar{y} = 3.5$ for Stock B.
    
2. Compute each difference from the mean for each pair and find the average product: $$\text{Cov}(X, Y) = \frac{1}{4} \left[(2 - 4)(1 - 3.5) + (3 - 4)(4 - 3.5) + (5 - 4)(4 - 3.5) + (6 - 4)(5 - 3.5)\right] = 1.75$$