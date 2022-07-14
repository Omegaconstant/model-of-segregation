# The Schelling Model of Segregation
Implementation of the Schelling’s model of global patterns of spatial segregation evolved from the effect of homophily operating at a local level.
<br/>App Link- [https://omegaconstant-the-schelling-model-of-segregation-file-wkvya9.streamlitapp.com/](https://omegaconstant-the-schelling-model-of-segregation-file-wkvya9.streamlitapp.com/)
## Homophily
- <strong>Definition</strong>: Homophily (origin: greek -- homós: 'same, common' & philía: 'friendship, love') can be defined as a sociological tendency of individuals to associate and bond with similar others, like based on parameters such as: race & ethnicity or sex or age or religion or interests & hobbies or education, occupation, organizational role and social class or may be the combination of multiple such factors etc. It provides us with a first, fundamental illustration of how a network’s surrounding contexts can drive the formation of its links & how in general the network would evolve over time.
- <strong>Mechanisms Underlying Homophily</strong>:
  1. <strong>Selection</strong>: In the case of immutable characteristics such as race or ethnicity, geography, family-ties, organizations etc. the tendency of people to form friendships with others who are like them is often termed selection, in that people are selecting friends with similar characteristics. This cause may be explicit as observed in more local level or small groups or can be implicit as seen in more global level. For example, when people live in same locality, attend same institute, or work for same organisation that are relatively homogeneous compared to the population at large, the social environment is already favoring opportunities to form friendships with others like oneself.
  2. <strong>Social Influence</strong>: With characteristics that are more mutable — behaviors, activities, interests, beliefs, opinions, cognitive processes — the feedback effects between people’s individual characteristics & their links in the social network become significantly more complex. The process of selection still operates, with individual characteristics affecting the connections that are formed. But now another process comes into play as well: people may modify their behaviors to bring them more closely into alignment with the behaviors of their friends. This process has been variously described as socialization and social influence, since the existing social connections in a network are influencing the individual characteristics of the nodes.
- <strong>Effects of homophily</strong>:
  1. According to one study ([Source](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4516978/)), perception of interpersonal similarity improves coordination and increase the expected payoff of interactions, above and beyond the effect of merely "liking others." Another study ([Source](https://www.jstor.org/stable/1519727?origin=crossref)) claims that homophily produces tolerance and cooperation in social spaces. However, homophilic patterns can also restrict access to information or inclusion for minorities ([Source](https://ui.adsabs.harvard.edu/abs/2018NatSR...811077K)).
  2. The effects of homophily on the diffusion of information and behaviors are also complex. Some studies have claimed that homophily facilitates access information ([Source](https://arxiv.org/abs/1006.1702)), the diffusion of innovations and behaviors ([Source](https://media.timesfreepress.com/docs/2010/01/Obesity_studies_0104.pdf)), and the formation of social norms ([Source](https://repository.upenn.edu/cgi/viewcontent.cgi?article=1604&context=asc_papers)). Other studies ([Source1](https://academic.oup.com/qje/article-abstract/127/3/1287/1923572?redirectedFrom=fulltext&login=false) [Source2](https://arxiv.org/abs/physics/0609213)), however, highlight mechanisms through which homophily can maintain disagreement, exacerbate polarization of opinions, lead to self segregation between groups, and slow the formation of an overall consensus.
  3. As online users have a degree of power to form and dictate the environment, the effects of homophily continue to persist. On Twitter, terms such as “Stan Twitter”, “Black Twitter”, or “Local Twitter” ([Source](https://www.theatlantic.com/technology/archive/2018/07/how-twitter-became-home-to-the-teen-status-update/564404/)) have also been created and popularized by users to separate themselves based on specific dimensions.
  4. Homophily is a cause of homogamy—marriage between people with similar characteristics ([Source](https://smg.media.mit.edu/papers/Fiore/fiore_donath_chi2005_short.pdf)). Homophily is a fertility factor; an increased fertility is seen in people with a tendency to seek acquaintance among those with common characteristics ([Source](https://www.demographic-research.org/Volumes/Vol29/37/)). Governmental family policies have a decreased influence on fertility rates in such populations ([Source](https://www.demographic-research.org/Volumes/Vol29/37/)).
  
## A Spatial Model of Segregation
- <strong>Introduction</strong>: One of the most readily perceived effects of homophily is in the formation of ethnically and racially homogeneous neighborhoods in cities. Traveling through a metropolitan area, one finds that homophily produces a natural spatial signature; people live near others like them, and as a consequence they open shops, restaurants, and other businesses oriented toward the populations of their respective neighborhoods. The tendency of people to live in racially homogeneous neighborhoods produces spatial patterns of segregation that are significantly apparent in everyday life. 
- <strong>The Schelling Model</strong>: A famous model due to Thomas Schelling shows how global patterns of spatial segregation can arise from the effect of homophily operating at a local level. There are many factors that contribute to segregation in real life, but Schelling’s model focuses on an intentionally simplified mechanism to illustrate how the forces leading to segregation are remarkably robust — they can operate even when no one individual explicitly wants a segregated outcome.
  1. <strong> Assumptions & Parameters</strong>:
      1. We assume that there is a population of individuals, let's call agents; each agent is of type RED or type BLUE, which represent some immutable characteristic (such as: race, ethnicity, country of origin, culture or native language etc.) serving as the basis for homophily. The agents reside in the houes in a 2D geography of a city, modelled by the cells of the grid. <em>Neighbour</em> denotes the adjacent cell wrt a concerned cell even inlcuding the diagonal ones.
      2. The fundamental constraint driving the model is that each agent wants to have at least some fraction of it's neighbour as an agent of his/her community. We will assume that there is a threshold t(0<= t<= 1) common to all agents: if an agent discovers that fewer fraction than t of its neighbors are of the same type as itself, then it has an interest in moving to a new cell randomly. Such an agent can be called as unsatisfied with its current location.
      3. Mean Simlarity Ratio: It is the arithmetic mean of similarity ratio (ratio of no. of neighbours of same characteristics as compared to total number of neighbours) calculated for all individual agents over the entire grid.
  2. <strong> Interpretations of the Model </strong>: 
      1. The first and most basic one is that spatial segregation is taking place even though no individual agent is actively seeking it. Like incase the paramater(t) is too low, an agent would be perfectly happy to be in the minority among its neighbors.
      2. From a random start, it is very hard for the collection of agents to find such integrated patterns. Much more typically, agents will attach themselves to clusters of others like themselves, and these clusters will grow as other agents follow suit. Moreover, there is a compounding effect, as the rounds of movement unfold, in which agents who fall below their threshold depart for more homogeneous parts of the grid, causing previously satisfied agents to fall below their thresholds and move as well — an effect that Schelling describes as the progressive “unraveling” of more integrated regions. In the long run, this process will tend to cause segregated regions to grow at the expense of more integrated ones. The overall effect is one in which the local preferences of individual agents have produced a global pattern that none of them necessarily intended.
  3. <strong> Some Limitations of this code as a model </strong>:
      1. <strong> Effect of Characteristics of threshold parameter</strong>: <br/> The model tends to simulate the entire effect based on a relative similarity threshold value(t), whose value lies in [0,1]. This might not play a very significant role in the long run, when the relative no. of empty space is comparatively low; but it can alter some distribution if we have a comparable amount of empty space. Where this can be made to absolute thershold, such as t specific number of neighbours are required to be of same community as compared to relatve parameter.
      2. <strong> Dynamics of Movement</strong>: In Schelling Model, we can have different possibilities of movement method (i.e. the specific details of how the movement of agents within a round is controlled), such as :
          1. the agents can be scheduled to move in a random order.
          2. or in an order that sweeps downward along rows of the grid.
          3. they can move to the nearest location that will make them satisfied or to a random one.
         <br/>In this modelling, we have taken this parameter to be random.
      3. <strong> Other real-life Factors</strong>: Factors such as immigration, emigration, births, deaths, etc might affect the demography-distribution in the local area in real-life. While most population models account for these factors, the given implementation does not, since it is just an idealistic model.
  4. <strong> Observations on effects of some paramters</strong>:<br/>
      1. <strong>Population Size</strong>: For substantial population size, the similarity ratio does not depend on the population size, as long as all other factors are kept constant.<br/><br/> For example, consider these simulations.<br/><br/>
          Population = <strong>5000</strong><br/>
          Empty House Ratio = 0.25<br/>
          Similarity Threshold = 0.30<br/>
          No. of iterations = 20<br/>![PopulationA](https://user-images.githubusercontent.com/83154020/178934821-cb1b58fd-7166-4a27-b6d6-df63f0d7767f.png)
          <br/><br/>
          Population = <strong>10000</strong><br/>
          Empty House Ratio = 0.25<br/>
          Similarity Threshold = 0.30         
          No. of iterations = 20<br/>![PopulationB](https://user-images.githubusercontent.com/83154020/178935044-e2d3d52d-5ff1-4079-b708-0d28b8f24dfc.png)
          <br/>
      2. <strong>Empty houses ratio</strong>: The empty houses ratio should influence how fast & how high the mean similarity ratio reaches its asymptotic value. The greater this ratio, the more choices any “dissatisfied” agents have, leading to a faster chance of convergence to the ideal state of the system with higher mean similarity ratio.<br/><br/> For example, consider these simulations.<br/><br/>
          Population = 5000<br/>
          Empty House Ratio = <strong>0.25</strong><br/>
          Similarity Threshold = 0.30<br/>
          No. of iterations = 20<br/>![emptyHousesRatioA](https://user-images.githubusercontent.com/83154020/178935664-f0a7c0d0-ef55-4f5d-8af8-bbf74e9fa900.png)
          <br/><br/>
          Population = 5000<br/>
          Empty House Ratio = <strong>0.80</strong><br/>
          Similarity Threshold = 0.30<br/>
          No. of iterations = 20<br/>![emptyHousesRatioB](https://user-images.githubusercontent.com/83154020/178936271-83e07565-11c7-421c-b04b-c7e799e73cb2.png)
      3. <strong>Similarity Theshold</strong>: The similarity threshold is expected to be the only parameter that directly & significantly affects the mean similarity ratio in this model. It is obvious that for low similarity thresholds, the agents are “satisfied” regardless of the mean similarity ratio, which leads to lower mean similarity ratios, while for higher thresholds, a high mean similarity ratio must occur.<br/><br/> For example, consider these simulations.<br/><br/>
          Population = 5000<br/>
          Empty House Ratio = 0.25<br/>
          Similarity Threshold = <strong>0.30</strong><br/>
          No. of iterations = 20<br/>![similarityThesholdA](https://user-images.githubusercontent.com/83154020/178935664-f0a7c0d0-ef55-4f5d-8af8-bbf74e9fa900.png)
          <br/><br/>
          Population = 5000<br/>
          Empty House Ratio = 0.25<br/>
          Similarity Threshold = <strong>0.70</strong><br/>
          No. of iterations = 20<br/>![similarityThesholdB](https://user-images.githubusercontent.com/83154020/178945706-0f38fb9b-b38b-45cb-abba-fa0d8e01ffef.png)
          <br/><br/>
      4. <strong>Number of iterations</strong>: Sometimes, it takes a quite larger number of iterations to achieve the equlibrium state.<br/><br/>
          Population = 3000<br/>
          Empty House Ratio = 0.50<br/>
          Similarity Threshold = 0.85<br/>
          No. of iterations = <strong>10</strong><br/>![iterationA](https://user-images.githubusercontent.com/83154020/178947068-a3614119-f192-4f9d-84a7-b6802726ed95.png)
          <br/><br/>
          Population = 3000<br/>
          Empty House Ratio = 0.50<br/>
          Similarity Threshold = 0.85<br/>
          No. of iterations = <strong>200</strong><br/>![iterationB](https://user-images.githubusercontent.com/83154020/178948356-a58b1f2c-0d80-4cd0-b375-8b7f43139983.png)
          <br/><br/>
  5. <strong>Conclusion</strong>: <br/>
      Viewed at a still more general level, the Schelling model is an example of how characteristics that are fixed and unchanging (such as race or ethnicity) can become highly correlated with other characteristics that are mutable. In this case, the mutable characteristic is the decision about where to live, which over time conforms to similarities in the agents’ (immutable) types, producing segregation. But there are other, non-spatial manifestation of the same effect, in which beliefs and opinions become correlated across racial or ethnic lines, and for similar underlying reasons: as homophily draws people together along immutable characteristics, there is a natural tendency for mutable characteristics to change in accordance with the network structure.
      
## References:
1. Chapter 4: Networks in Their Surrounding Contexts, Section 4.5: A Spatial Model of Segregation (Page 107- 115)<br/> [Networks, Crowds, and Markets: Reasoning about a Highly Connected World](https://www.cs.cornell.edu/home/kleinber/networks-book/)<br/>By: David Easley, Jon Kleinberg
2. [Homophily: Wikipedia Page](https://en.wikipedia.org/wiki/Homophily#cite_note-20)
3. [Schelling's Model of Segregation: Wikipedia Page](https://en.wikipedia.org/wiki/Schelling%27s_model_of_segregation)
