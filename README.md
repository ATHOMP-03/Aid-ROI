# For the Global Good: An Economic Case for Foreign Aid
Ashley Thompson




Abstract
In this paper I quantify the United States’ return on investment for foreign aid.  Tracking aid disbursements by recipient on over 20 years of panel data along with foreign direct investment data from the St. Louis Fed’s Federal Reserve Economic Data (FRED) database, I show that the distribution of foreign aid causes positive reciprocal investment back to the US.  To account for the wide variance in countries receiving aid, both military and economic, and their propensity to invest in the US, I manually employ augmented inverse propensity weighting (AIPW) to address bias on both sides, aid recipient and investor.  Results indicate that when given aid, countries will on average invest an additional $8 million than they otherwise would have.  This validates an optimistic view for global engagement, showing that investing in the global good is good for the US economy. 



























1. Introduction: 
Foreign aid is an important means of exercising “soft power.”  However, when compared with media or culture, it is often a more divisive one. Depending on one’s political stance, foreign aid can be either good or bad.  To some, it is simply ethical to give to those with less. To others, it is a waste of money that could be spent at home.  For others still, investment of foreign aid creates a rising tide that raises all boats, including that of the donor. This study seeks to clarify the impact of aid on the donor’s economy by the question specifically by asking “Does investment in global development through foreign aid increase foreign investment in the US?”.  
Building on previous research that indicates increased trade volume when perceived to be a good actor on the world stage (Like Me Buy Me, Rose, 2015).  However, as opposed to Rose’s exploration of trade volume and polling estimates of perception, I chose to look at a dollars for dollars comparison of aid money out to investment back in.  By using foreign aid dollars as our independent variable, and foreign direct investment as our dependent variable, I am framing the problem such that the treatment effect of aid represents an actual return on investment in dollars for dollars terms.  This also adds a more specific dimension to previous research on soft power which focused specifically on public perception and trade volume (Rose, 2015; Rose 2019; Fan et al, 2022).   
	For this study, I use linear regression with fixed effects and augmented inverse propensity weighting (AIPW) to address the inherent bias towards low income countries’ receipt of aid, and the bias that those same countries are less likely to invest in the US.  This approach allows us to model both the propensity to receive aid, and the propensity to invest for a doubly robust estimation of the treatment effect, specifically with AIPW.  Ultimately, I show that all else being equal, when the US invests in a country through foreign aid, that country returns that investment by investing $8 million more than they would have without aid.  This is modest, but it does show a positive return for a positive deed.  

2. Methodology:
To explore a possible causal link between US engagement in the world and US economic growth I used foreign direct investment (FDI) and foreign aid disbursements.  I postulate that FDI represents money that is exogenous to the US economy, and is thus pure growth in overall economic output.  Foreign aid dollars are just that, dollars disbursed to aid a foreign country.  Once inherent biases towards aid distribution and investment are addressed, these variables allow for a dollars to dollars comparison of aid’s impact on economic growth as indicated by FDI.

The Figure 1 (at right) shows the complex relationship between aid, investment, and the multitude of confounders influencing the two. This creates bias on both sides - aid receipt and direct investment in the US. To account for this, I first use linear regression accounting for year and country fixed effects and applying a 5 year lag (to allow aid to mature into investment). This model, incorporating fixed effects for countries and years to address time variance and endogenous country factors is modeled as follows:

FDIit = β0 + β1⋅Aidi,t−5 + β2⋅GDPit + β3⋅DefTrtyit + β4⋅BITit + β5⋅TrdTrtyit + β6⋅IGit + 𝛾i + 𝛿i + 𝜀i

FDI - Foreign direct investment in USD
Aid - Aid disbursements by in USD (note, t-5 applied for 5 year lag to FDI return)
GDP - Country gross domestic product by USD
DefTrty - Number of defense treaties in place with the US
BIT - Numer of bilateral investment treaties in place with the US
TrdTrty - Number of trade treaties in place with the US
IG - Income group of the country (1 to 4, 1 being low income, 4 being high income)
𝛾i - Country fixed effects
𝛿i - Year fixed efects
 𝜀i - Error term

Givne the bias on both sides of the aid - FDI relationship, I then ran AIPW with a binary treatment/control methodology to determine if there is, or is not, a positive effect of aid on FDI. I expanded the set of confounders to add robustness and to help further isolate the effects of aid, then used these to model both propensity to receive aid, and propensity to invest in the US. This was done by manually by creating a matrix of all covariates on which to build, then propensity scoring based on those covariates, modeling for outcome (prospective FDI), and finally applying AIPW to estimate the average treatment effect (ATE) as follows: 

-	Covariate Matrix Compilation:  Our matrix of covariates will consist of factors likely to impact the distribution of aid, likelihood of investment in the US, and measures of endogenous US economic growth (to try and isolate only exogenous growth factors). 

-	Propensity scoring:  Propensity scoring by assigning treatment status to each country-year, then regressing treatment status on each country against the covariate matrix to determine a likelihood of receiving treatment (aid).

-	Outcome modeling: To predict potential outcomes, I regress FDI on the covariate matrix to determine an estimator to predict FDI amounts for each country should the be treated.  

-	AIPW Estimation: To generate an average treatment effect.

Specifically I used the following estimation equation:
 
𝞃- Average change in investment from countries receiving aid
𝝻- Modeled/predicted outcome conditional on treatment and observable confounders
𝒆(𝙓𝑖) - Propensity score
𝘿𝑖 - Treatment status (received aid = 1, all else = 0)
𝙓𝑖 - Set of observable characteristics (matrix of confounders)
𝒀𝑖 - Outcomes (treated: i = 1, untreated: i = 0) 
3. Data:
Foreign Aid Data: Foreign aid data consists of approximately 37,000 observations documenting all foreign aid transactions from fiscal year 2000 to 2024.  These were sorted to reflect only disbursements, and then summed for each country by year to simplify analysis. These were compiled as country-year panel data, then all other data was matched to this county-year format. 

FDI Data: FDI data was collected from the St Louis Federal Reserve and was extracted as panel data documenting investment by sector, by year, for each country from which the US received direct investment.  This data was summed for each country by year, and compiled into country-year panel data and added to the master set to be used in the analysis. 

Covariates and Confounders: 
-	Factors influencing aid distribution: Data was collected from numerous sources that influences the potential distribution of aid.  This included country GDP, country location and shared treaty status for defense and trade treaties.  This allows for countries receiving high amounts of aid to be treated differently than those receiving little to none. 

-	Factors influencing FDI: Poor countries have little ability to invest in the US.  For this reason, each country’s GDP data, treaty status with the US, location, etc, were compiled to allow outcome modeling.  

-	Endogenous US Growth Factors: To account for endogenous US economic growth, US GDP data was included for each country-year, as was performance of the Dow Jones.  This allows for rough baseline measurements of US economic growth.  These are required to understand if aid is increasing in distribution simply due to greater US spending power, or if it is distributed to achieve more global economic goals.  This also allows us to begin to separate out that fraction of growth contributed by FDI.  


4. Results
Linear regression showed limited applicability in this instance.  As indicated in Table 1, only GDP and Defense Treaty status indicated any influence on FDI, however, these results did not exhibit low enough standard errors (SEs) to imply any statistical significance.  This was expected, given the level of bias that exists on both sides of the Aid-FDI equation.  

AIPW results provided an estimated ATE of $8 million, (Table 2) suggesting that countries receiving aid on average invest $8 million more in the US economy than similar countries not receiving aid.  This is consistent with past literature suggesting that countries benefit economically by doing good in the world (Rose, 2015).  However, the relatively high standar deviation (SD) indicates that there is much heterogeneity in treatment effects.  This is likely due to the high variance in amounts of aid provided by each county.  We can also see that treated observations dominate the sample (pscore, Table 2).  This reflects the distribution of aid (treatment) to most of the sample.  Downselecting to a roughly half and half group could yield better results. 

Furthermore, balance testing and propensity score distribution confirms that further refinement of the sample is needed to further hone in on the impact of aid. Balance testing (Table 3) indicates that the treated and untreated groups vary widely in their confounders.  This makes them not necessarily great reresentations of each other for evaluating the effect of treatment on the potentially untreated.  This is confirmed in propensity score distrubutions, as seen in Figure 2.  However, there is substantial enough overlap to look see that the AIPW (or other doubly debiased method) provides the best means of looking at the causal relationship between aid and FDI.  

5. Discussion
While further research is certainly warranted to isolate the causal influence of foreign aid on domestic economic growth.  There is a clear case to be made that investing in the world benefits the American economy, and that dollars spent helping other countries develop find their way  home in terms of economic prosperity.  This is compelling in that it supports the role of agencies such as the US Agency for International Development, Department of State, and even the Department of Defense in remaining engaged and cultivating growth globally so that our economy expands at home.  However, given the limited overlap in how countries receive aid and invest in the US, further research is needed to truly illustrate a causal link.  I indend to pursue this link by continuing to expand the set of confounders used for modeling both aid distribution, and FDI.  I also intend to collapse the sample to trim of those countries that have traditionally received a great deal of aid but which do not invest outside their countries.  This appears to be true of places that receive a great deal of military aid, which makes sense given that they are usually in a state of conflict while receiving such assistance.  Focusing the study further on infrastructure development and other humanitarian aid will likely yield different results.  However, I am pleased to see that there is evidence, albeit slight, that investing in the world, benefits the economy at home.  

6. References

Rose, Andrew K. 2019. “Agent Orange: Trump, Soft Power, and Exports.” NBER Working Paper 25439. Cambridge, MA: National Bureau of Economic Research. https://doi.org/10.3386/w25439.

Fan, Haichao, Yichuan Hu, Lixin Tang, and Shang-Jin Wei. 2022. “Is American Soft Power a Casualty of the Trade War?” NBER Working Paper 29999. Cambridge, MA: National Bureau of Economic Research. https://doi.org/10.3386/w29999.

Rose, Andrew K. 2015. “Like Me, Buy Me: The Effect of Soft Power on Exports.” NBER Working Paper 21537. Cambridge, MA: National Bureau of Economic Research. https://doi.org/10.3386/w21537.

U.S. Department of State and U.S. Agency for International Development. n.d. “ForeignAssistance.gov Data.” https://foreignassistance.gov/data.

Federal Reserve Bank of St. Louis. n.d. “FRED, Federal Reserve Economic Data.” https://fred.stlouisfed.org/.

The World Bank. n.d. “DataBank.” https://databank.worldbank.org/home.

International Trade Administration. n.d. “All Trade Agreements.” https://www.trade.gov/all-trade-agreements.

United States International Trade Commission. n.d. “USITC DataWeb.” https://dataweb.usitc.gov/.

Office of the United States Trade Representative. n.d. “Free Trade Agreements.” https://ustr.gov/trade-agreements/free-trade-agreements.

U.S. Department of State. n.d. “Treaties in Force.” https://www.state.gov/treaties-in-force
<img width="468" height="644" alt="image" src="https://github.com/user-attachments/assets/6fab9024-845b-4ad2-928c-1d9c0b27be84" />

