# TikTok Hackathon

Scrolling through TikTok should feel like a personalized adventure. Using mathematics and algorithms to deliver ads that do not just interrupt but to engage, entertain and inspire.

## Our team: TikTok on the Clock

- Emily Chee
  - Emily is interested in delving into and enhancing the digital world. WIth a focus on data analytics, she is learning to master the art of managing vast datasets and enhancing data accuracy. Her experience as an avid social media user, gives her a unique insight into user experiences and trends. And yes, she's a proud coffee addict.
  - [Emily's LinkedIn](https://www.linkedin.com/in/emily-chee-1144391a8/)
<br /><br />
- Jeanelle Boey
  - Jeanelle is passionate about harnessing the power of big data to unearth innovative solutions within the tech industry, with a specific focus on advancing machine learning models. During her leisure hours, she indulges in the art of baking and in crafting the perfect matcha latte.
  - [Jeanelle's LinkedIn](https://www.linkedin.com/in/jeanelleboey/)
<br /><br />
- Joash Tan
  - Joash is fascinated in the wonders of how digitalisation can revolutionize the future of our world. With experience in web/app development, he is built with the skill sets for front-end development and UI/UX but his passion still lies in data analytics. In his free time, he enjoys writing music-related blogs and doubles as a part-time physics tutor.
  - [Joash's LinkedIn](www.linkedin.com/in/tanjoash)
<br /><br />
- Justin Wong
  - Justin is a tech enthusiast and he founded a club to educate others about the intricacies of tech startups. He also enjoys fishing during the weekends and has a newfound passion for fishing on kayaks.
  - [Justin's LinkedIn](https://www.linkedin.com/in/justinwongwj/)
<br /><br />
- Raynard Chai
  - Raynard is driven by a passion for empowering businesses to scale sustainably while making a positive social impact. Being fluent in business analytics, operations research, and social science, he brings a diverse skill set to the table. Outside of his professional pursuits, Raynard enjoys regular runs and indulges in photography as a creative outlet.
  - [Raynard's LinkedIn](https://www.linkedin.com/in/cycraynard/)

## Methodology

**Abstract**: Optimizing Advertisement Moderation with Stochastic Optimization

**Background**:
Internet companies heavily rely on advertisements for revenue generation. These advertisements are pivotal only post their moderation to ensure they pose no risk to the platform, users, or advertisers. There exists a dire need to prioritize ad content that is most valuable or risk-laden, enhancing the review process's efficiency. Moreover, aligning an ad with the best-fit moderator based on various dimensions becomes crucial for maintaining review accuracy.

### Our Approach:

**Ad Scoring**:

We propose a weighted system to score the advertisements. We will be using use scaled features 'punish_num' and 'avg_ad_revenue'. The formula we employed is:
$\text{ad score} = w_1 \times (\text{punish num}) + w_2 \times (\text{avg ad revenue})$

Ads are then ranked from highest to lowest score, indicating their priority for review.

**Moderator Scoring**:

Recognizing the importance of having adept moderators, we've also devised a scoring system for them. The scoring is influenced by the moderator's average handling time (inverse relation) and their accuracy. The mathematical representation is:
$\text{moderator score} = v_1 \times \frac{1}{\text{handling time}} + v_2 \times \text{accuracy}$
Following this, moderators are ranked from highest to lowest indicating their proficiency.

**Matching Algorithm**:

Subsequently, we deployed a matching algorithm to pair high-priority ads with top-performing moderators. This seeks to achieve a synergetic match where both the ad's significance and the moderator's competence are optimized.

**Optimization Using Genetic Algorithm**:

To realize the twin objectives of revenue maximization and risk mitigation, we've framed the following objective functions:

$\text{Estimated revenue rate} = \text{accuracy} \times \frac{\text{avg ad revenue}}{\text{handling time}}$

$\text{Estimated riskiness} = (1 - \text{accuracy}) \times \text{punish num}$

These functions will be solved using a genetic algorithm to reach an optimal solution.

## File strucutre
- Preprocessing
  - tiktok_eda_preprocessing.ipynb takes into account the raw dataset: ads and moderators and does some visualisation and preprocessing to give the output csv to run in our optimization model.

- Optimization
  - tiktok_optimization_model.ipynb takes the preprocessed data from tiktok_eda_preprocessing.ipynb and runs the optimization model to give the desired output.
