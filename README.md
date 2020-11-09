# Portfolio Performance using Style Analysis

A python notebook [style_analysis.ipynb](https://github.com/andrebodo/style-analysis/blob/main/style_analysis.ipynb) to analyze portfolio performance using William Sharpe's style analysis. A performance tearsheet is also provided.

## Input File Requirement
The notebook expects a csv file with two labelled columns ('date' and 'return'). Dates align with calendar EOM dates and returns are monthly. 

## Parameters
Some manual inputs to be aware of:

- Indicies: Choose which indicies you want to include. Some description is given for this in the notebook.
- CUSTOM_T_CRIT: T-critical stat used to determine which coefficients of regression are relevant
- ALPHA: Alpha level used to determine T-CRIT if None is specified for CUSTOM_T_CRIT

## Style Analysis
The significant style factors are presented based on significant regression coefficients between portfolio returns and index returns. 
Sequential least squares programming is used since there are no popular libraries supporting constrained multiple regressions. The following are the constraints used:

1. No intercept
2. All coefficients are >= 0
3. The sum of all coefficients = 1

Indicies corresponding to significant coefficients are considered representative of the style of the portfolio. A benchmark ('bogey') can be created to compare the portfolio performance to the style-based bogey. The bogey is constructued using the signficant style index returns, and weighting them based on the coefficients of regression.

## Performance Analysis
Several charts are presented to graphically depict the performance figures of the portfolio. Additionally, statistics are provided at the very end of the notebook.

## Author's Note
Some attempt is made at flexible re-useable coding. The focus was to provide a method for analysis, rather than reuseable code.