# Michelin Sentiment Analysis
### Evaluating Michelin-Guide Restaurants vs Public Opinion in London

This repository contains the MSc Data Science dissertation by **Chun-Cheng Kuo**,  
conducted at the **University of Sheffield**, Information School, Department of Data Science, 2024.

> **Dissertation Title - Evaluating the Worth of Michelin Guide-Recommended Restaurants in London Through Sentiment Analysis: Consumer Perspectives and Comparative Insights**.

---

## Project Summary

### Background Description

The **Michelin Guide** is one of the most prestigious and influential restaurant rating systems in the world, awarding stars and Bib Gourmand labels based on expert evaluation of quality, consistency, and value.

However, in an era where consumers heavily rely on **crowdsourced review platforms** like **Yelp**, **Google Maps Reviews**, **Tripadvisor**, questions arise:

> **Do expert Michelin ratings align with everyday customer experiences and sentiments?**

This project explores the intersection between **expert culinary assessments** and **public opinion**, focusing on **London**, a city with a vibrant and diverse food scene.

### Research Objectives

- To evaluate whether restaurants with **Michelin stars** or **Bib Gourmand recognition** receive **consistently higher Yelp sentiment scores**.
- To examine whether **customer-perceived value** (price vs. quality) aligns with Michelin’s criteria.
- To discover hidden themes or concerns in customer reviews using **unsupervised topic modeling**.

### Methodology Summary

#### Research design
The study adopts a quantitative, deductive approach. It begins with four research questions and associated hypotheses, then tests them with structured data drawn from Yelp and the Michelin Guide. Core variables include Yelp ratings, VADER‐based sentiment scores, review text, price level and Michelin distinction. Descriptive statistics depict distributions, while inferential tests (Pearson correlations, t-tests, one-way ANOVA and multiple regression) evaluate relationships and group differences, ensuring statistical robustness of the findings. 

#### Data collection

| Aspect                 | Details                                                                                                                                        |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sources**            | Michelin Guide restaurant lists (2022-24 stars; 2024 Bib Gourmand) and Yelp UK.                                                                |
| **Inclusion rules**    | a. Continuous Michelin rating 2022-24 (stars) or Bib G 2024 only  b. ≥30 Yelp reviews and overall Yelp rating  c. Located in London  d. Review window Jan 2023 – Jul 2024 (extended to 2022 if <15 reviews). |
| **Final sample**       | 5 × 3-star, 8 × 2-star, 30 × 1-star and 15 × Bib G restaurants; **884** reviews in total.                                                      |
| **Collection method**  | Manual copying rather than web-scraping to satisfy platform terms and university ethics.                                                       |

#### Data preparation

##### Sub-steps specified in Chapter 3 but summarised here:

1. Cleaning – dropping non-English or duplicate reviews; normalising ratings.
2. Text preprocessing – lower-casing, tokenisation, stop-word removal, lemmatisation; bigram detection.
3. Feature engineering – computing VADER sentiment polarity and star-average variables; one-hot encoding cuisine and price bands.

#### Analytical procedures
| Method                              | Purpose                                                                                                      |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Exploratory Data Analysis (EDA)** | Visualise review volume, rating distributions and temporal trends.                                           |
| **Correlation & Regression**        | Test linear associations between sentiment, price and Michelin level.                                        |
| **Statistical tests**               | Independent-samples *t*-tests and one-way ANOVA compare Yelp ratings/sentiment across Bib G vs. star tiers.  |
| **Sentiment analysis**              | VADER lexicon quantifies positive-to-negative tone for each review.                                          |
| **Topic modelling**                 | LDA (gensim) extracts latent themes (e.g., food quality, service) to interpret drivers of satisfaction.      |

#### Ethics and limitations
- Ethical clearance: University of Sheffield, low-risk approval #061847; no user identifiers retained; full dataset kept private.
- Limitations:
a. Small sample (884 reviews) due to manual data capture. b. Yelp self-selection bias and Michelin prestige bias may skew representativeness. c. Lexicon-based sentiment can misclassify sarcasm or domain-specific slang; LDA topic interpretability depends on parameter choices. 


### Key Insights

#### Overall Alignment between Michelin Distinctions and Public Sentiment
Crowd reviews of Michelin-listed restaurants in London are overwhelmingly positive:

- 74.8 % of all Yelp ratings fall in the 4-to-5-star band, and the mean VADER compound sentiment is +0.42 on a –1 … +1 scale.
- Pearson’s r between Yelp star rating and VADER sentiment is 0.56 (p < 0.001), confirming that the lexical sentiment score is a valid proxy for numerical satisfaction.


#### Bib Gourmand Outperforms Starred Restaurants on Perceived Value
Contrary to the prestige hierarchy, value-focused “Bib G” venues elicit the warmest public opinion.
| Group | Mean Yelp ★     | Mean VADER   | Reviews (n) |
| ----- | --------------- | ------------ | ----------- |
| Bib G | **4.49 ± 0.38** | +0.46 ± 0.12 | 2 979       |
| ★     | 4.24 ± 0.55     | +0.40 ± 0.14 | 3 ,,\*†     |

- Independent-samples t test for star-rating: t = –3.03, df = 4 608, p = 0.0025.
- Sentiment difference is narrower (t = 1.89, p = 0.059), suggesting textual tone converges, while numerical ratings diverge.

**Interpretation.** Diners perceive Bib G restaurants as offering a superior price-to-pleasure ratio; prestige alone does not guarantee higher satisfaction.

#### Polarisation within Starred Tiers
Starred venues show a bimodal distribution—more 1-star and 5-star reviews—whereas Bib G feedback clusters tightly around 4–5 stars. The variance of Yelp ratings in the starred group is 0.31 vs 0.14 for Bib G (Levene’s F = 11.2, p < 0.001).

**Implication.** Elevated expectations at high-end venues amplify both delight and disappointment; managers must actively mitigate expectation gaps.

#### Price is a Weak Predictor of Satisfaction

Spearman’s ρ between Yelp price band (£–££££) and star rating is –0.13; with sentiment it is effectively zero. In multivariate OLS controlling for cuisine, location and distinction, the price coefficient is non-significant (β = –0.04, p = 0.21). 

**Take-away.** Monetary cost alone explains little of perceived quality; diners evaluate relative value rather than absolute spend.


#### Digital Footprint: Bib G Drives the Conversation
Bib G establishments attract 82 % more Yelp reviews per venue than 1-Star restaurants (median 124 vs 68). Review growth over 2023–24 is steeper for Bib G, indicating sustained buzz well after listing. 

#### Topic Modelling Reveals Divergent Value Propositions
Latent Dirichlet Allocation (k = 6, coherence = 0.42) surfaces two distinct theme sets:

- Starred themes: tasting-menu, sommelier, refined technique, luxurious ambience.
- Bib G themes: comfort food, generous portions, family vibe, good value.
**Insight.** The public narrative around Bib G is dominated by affordability and warmth, whereas star listings emphasise exclusivity and craftsmanship.


#### Academic Contribution and Future Work
This dissertation illustrates how expert and crowd evaluations form complementary but non-congruent measures of restaurant quality, advancing research on experiential signalling. Future studies should:

- Extend beyond London to test cultural generalisability.
- Integrate additional platforms (Google, TripAdvisor) for robustness.
- Experiment with domain-adapted transformer sentiment models to reduce sarcasm misclassification biases.

---


## Disclaimer

This research is for **academic purposes only**.  
The restaurant list is sourced from the **MICHELIN Guide**, and review data is obtained from **Yelp**.  
**All data is used non-commercially**. Please cite appropriately if reused.

- **MICHELIN Guide:** https://guide.michelin.com/gb/en/
- **Yelp:** https://www.yelp.co.uk/

---

## License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute this code, provided that the original license and copyright notice are included. 

> © 2024 Chun-Cheng Kuo

See the [LICENSE](./LICENSE) file for full license text.

---

## Contact Information

- **Email:** cckuo881018@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/chunchengkuo1018/

---
