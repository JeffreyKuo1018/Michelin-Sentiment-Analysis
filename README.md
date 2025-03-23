# Michelin Sentiment Analysis

This repository contains the MSc Data Science dissertation by **Chun-Cheng Kuo**,  
conducted at the **University of Sheffield**, Information School, Department of Data Science, 2024.

> **Dissertation Title: Evaluating the Worth of Michelin Guide-Recommended Restaurants in London Through Sentiment Analysis: Consumer Perspectives and Comparative Insights**.

---

## Project Description

The **Michelin Guide** is one of the most prestigious and influential restaurant rating systems in the world, awarding stars and Bib Gourmand labels based on expert evaluation of quality, consistency, and value.  
However, in an era where consumers heavily rely on **crowdsourced review platforms** like **Yelp**, questions arise:

> **Do expert Michelin ratings align with everyday customer experiences and sentiments?**

This project explores the intersection between **expert culinary assessments** and **public opinion**, focusing on **London**, a city with a vibrant and diverse food scene.

### Research Objectives

- To evaluate whether restaurants with **Michelin stars** or **Bib Gourmand recognition** receive **consistently higher Yelp sentiment scores**.
- To examine whether **customer-perceived value** (price vs. quality) aligns with Michelin’s criteria.
- To discover hidden themes or concerns in customer reviews using **unsupervised topic modeling**.

### Methodology Summary

- **Sentiment Analysis**:  
  Using the **VADER (Valence Aware Dictionary and sEntiment Reasoner)** algorithm to assign sentiment polarity scores to Yelp reviews.

- **Topic Modeling**:  
  Leveraging **Latent Dirichlet Allocation (LDA)** to extract dominant topics across reviews of each restaurant group.

- **Statistical Analysis**:  
  Applying **t-tests**, **ANOVA**, and **correlation tests** to validate whether observed differences in sentiment are statistically significant.

- **Data Curation**:  
  Yelp reviews and metadata were scraped and cleaned. Michelin restaurant listings were matched and categorized using the official **Michelin Guide**.

### Key Insights

- **Bib Gourmand restaurants**, which emphasize value-for-money, tend to receive **more positive average sentiment** than Michelin-starred restaurants, suggesting that **consumer satisfaction is influenced by expectations and price sensitivity**.
- Some Michelin-starred venues show mixed sentiment, often reflecting high expectations, long wait times, or inconsistencies in service.
- Topic modeling reveals that **service, pricing, atmosphere**, and **value** are frequently mentioned dimensions in customer reviews.

This research demonstrates how **Natural Language Processing (NLP)** can complement traditional expert-driven evaluations and provide a more nuanced view of customer experience.

---

## Disclaimer

This research is for **academic purposes only**.  
The restaurant list is sourced from the **MICHELIN Guide**, and review data is obtained from **Yelp**. **All data is used non-commercially**. Please cite appropriately if reused.

---

## License

This project is licensed under the **MIT License**.  
You are free to use, modify, and distribute this code, provided that the original license and copyright notice are included. 

> © 2024 Chun-Cheng Kuo

See the [LICENSE](./LICENSE) file for full license text.

---

## Contact Information

- Email: cckuo881018@gmail.com
- LinkedIn: www.linkedin.com/in/chunchengkuo1018/
