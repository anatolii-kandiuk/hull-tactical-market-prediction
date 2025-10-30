# **Hull Tactical - Market Prediction**

Description

Wisdom from most personal finance experts would suggest that it's irresponsible to try and time the market. The Efficient Market Hypothesis (EMH) would agree: everything knowable is already priced in, so don’t bother trying.

But in the age of machine learning, is it irresponsible to not try and time the market? Is the EMH an extreme oversimplification at best and possibly just…false?

This competition is about more than predictive modeling. Predicting market returns challenges the assumptions of market efficiency. Your work could help reshape how investors and academics understand financial markets. Participants could uncover signals others overlook, develop innovative strategies, and contribute to a deeper understanding of market behavior—potentially rewriting a fundamental principle of modern finance. Most investors don’t beat the S&P 500. That failure has been used for decades to prop up EMH: If even the professionals can’t win, it must be impossible. This observation has long been cited as evidence for the Efficient Market Hypothesis the idea that prices already reflect all available information and no persistent edge is possible. This story is tidy, but reality is less so. Markets are noisy, messy, and full of behavioral quirks that don’t vanish just because academic orthodoxy said they should.

Data science has changed the game. With enough features, machine learning, and creativity, it’s possible to uncover repeatable edges that theory says shouldn’t exist. The real challenge isn’t whether they exist—it’s whether you can find them and combine them in a way that is robust enough to overcome frictions and implementation issues.

Our current approach blends a handful of quantitative models to adjust market exposure at the close of each trading day. It points in the right direction, but with a blurry compass. Our model is clearly a sub-optimal way to model a complex, non-linear, adaptive system. This competition asks you to do better: to build a model that predicts excess returns and includes a betting strategy designed to outperform the S&P 500 while staying within a 120% volatility constraint. We’ll provide daily data that combines public market information with our proprietary dataset, giving you the raw material to uncover patterns most miss.

Unlike many Kaggle challenges, this isn’t just a theoretical exercise. The models you build here could be valuable in live investment strategies. And if you succeed, you’ll be doing more than improving a prediction engine—you’ll be helping to demonstrate that financial markets are not fully efficient, challenging one of the cornerstones of modern finance, and paving the way for better, more accessible tools for investors.

Files

train.csv Historic market data. The coverage stretches back decades; expect to see extensive missing values early on.

    date_id - An identifier for a single trading day.
    M* - Market Dynamics/Technical features.
    E* - Macro Economic features.
    I* - Interest Rate features.
    P* - Price/Valuation features.
    V* - Volatility features.
    S* - Sentiment features.
    MOM* - Momentum features.
    D* - Dummy/Binary features.
    forward_returns - The returns from buying the S&P 500 and selling it a day later. Train set only.
    risk_free_rate - The federal funds rate. Train set only.
    market_forward_excess_returns - Forward returns relative to expectations. Computed by subtracting the rolling five-year mean forward returns and winsorizing the result using a median absolute deviation (MAD) with a criterion of 4. Train set only.

test.csv A mock test set representing the structure of the unseen test set. The test set used for the public leaderboard set is a copy of the last 180 date IDs in the train set. As a result, the public leaderboard scores are not meaningful. The unseen copy of this file served by the evaluation API may be updated during the model training phase.

    date_id
    [feature_name] - The feature columns are the same as in train.csv.
    is_scored - Whether this row is included in the evaluation metric calculation. During the model training phase this will be true for the first 180 rows only. Test set only.
    lagged_forward_returns - The returns from buying the S&P 500 and selling it a day later, provided with a lag of one day.
    lagged_risk_free_rate - The federal funds rate, provided with a lag of one day.
    lagged_market_forward_excess_returns - Forward returns relative to expectations. Computed by subtracting the rolling five-year mean forward returns and winsorizing the result using a median absolute deviation (MAD) with a criterion of 4, provided with a lag of one day.
