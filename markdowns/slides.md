---

marp: true
theme: default
color: #000
backgroundColor: #fff
paginate: true
enableHtml: true	


---
# Exploring Test Value

Clinical Informatics Lecture

Mark A. Zaydman MD, PhD
September 29, 2022

---

# Learning objectives

- Describe the overlap and distinction between test accuracy and test value
- Apply Bayesian analysis to update a prior belief given a test result
- Appreciate that lab tests have associated risks and harms
- Apply decision analysis to model test value
- List non-analytical factors that impact the value of a lab result

<br>

Course materials at: https://github.com/MarkZaydman/Lecture-TestValue.git


---

# Why this lecture matters

- Decisions regarding test utilization should be based on the value provided by testing
- Accuracy metrics provide an incomplete description of test value
- There is a critical need to define and quantify value in order to optimize test utilization
 
---


A 50 year old man with a history of HTN, HLD, T2DM, and obesity presents to the ED with squeezing chest pain, shortness of breath, and dizziness. 

<!-- On physical exam he is pale, diaphoretic, and in apparent discomfort. -->

<!-- <img src="../../Test_Accuracy/Activity/STEMI.jpeg" width="300" alt="pic"/> -->
<br>
<!-- <block align="middle"> -->

**A STAT ECG reveals ST-segment elevations in consecutive leads.**
<!-- </block> -->

<br>

<ins> What is the most appropriate next step in management?</ins>

1. Order CK-MB
2. Order LDH
3. Order conventional cardiac troponins
4. Order high sensitivity cardiac troponins
5. Cardiac catheterization

</block>

---

# Key Concepts

1. The value of a test result may vary with context
2. The value of the test depends on more than just the accuracy of the test

---

# Test value is multifactorial

### <ins>A valuable test provides</ins>

- actionable information
- to the right person
- at the right time
- in the right format

<br>

<block align="center">

**A test can be accurate but fail to provide value**

</block>

---

# <ins>Actionable Information</ins>

1. Changes the clinical scenario in a 'non-negligible' way
2. This change warrants some action that would not have otherwise occurred
3. Resources are available to take the indicated action
4. There is a net benefit to patient outcomes

---

# Key Question

<!-- <br> -->

*How can we quantify the impact of test result on a patient's disease probability?*

<br>
<br>

(Hint: we could use Bayes Theorem)

<!-- ---

# Actionable information

- Accuracy is a prerequisite
- Has the result changed the clinical scenario in a meaningful way?
  1. Did the test change the clinical scenario?
     - Bayes theorem
     - Information theory
  2. Was the change be actionable?
     - Defining decision points
       - Cost benefit analysis
       - Decision analysis
  3. Are resources available to act?
  4. Was there a net benefit? -->

---

# Bayes Theorem

<br>

$$P(D|+)=\frac{P(D)P(+|D)}{P(+)}\qquad (Bayes\; Theorem)$$

<br>

- Bayes' theorem allows us to update a prior belief in light of new evidence
- Bayes' theorem relates the probability of the hypothesis given the evidence to the probability of the evidence given the hypothesis

---


# Conditional probability

<!-- <img align="right" src="./../Figures/Graphical_Bayes_Path1.png" hspace=1 vspace=40 width="500" alt="pic"/>  -->
$P(D|+)=\frac{P(D\,\cap\, +)}{P(+)}$ 

- $P(D|+)$ : "The probability of disease given a positive test"
- $P(D \, \cap \,+)$ : "The probability of disease and a positive test"
- $P(+)$ : "The probability of a positive test" 



---
<!-- 
# Bayes theorem (proof)
<block align="middle">
<img align="middle" src="./../Figures/Apply_RealisticTest.png" hspace=25 vspace=20 width="800" alt="pic"/>

*("Realistic" test from last class)*
</block>
 -->


<!-- --- -->

# Realistic test (from last class)

<block align="middle">
<img align="middle" src="./Figures/Graphical_Bayes.png" hspace=25 vspace=20 width="850" alt="pic"/>
</block>

<!-- <br> -->
<!-- There are two ways to compute the number of true positives that must be equivelant -->
<!-- $P(A|B)$ = Conditional Probability, "The probability of A given B" -->

---

# Bayes' theorem (proof)
<block align="left">
<img align="right" src="./Figures/Graphical_Bayes.png" hspace=2 vspace=4 width="550" alt="pic"/> 

<br> 

$N_{TP}=N_{total}P(+)P(D|+)$
$\qquad=(100)(0.15)(\frac{8}{15})=8$



$N_{TP}=N_{total}P(D)P(+|D)$
$\qquad=(100)(0.10)(\frac{8}{10})=8$


</block>

<br>


$$\cancel{N_{total}}*P(+)*P(D|+)=\cancel{N_{total}}*P(D)*P(+|D)$$

<br>

$$P(D|+)=\frac{P(D)*P(+|D)}{P(+)}\qquad (Bayes\; Theorem)$$

---

# What does Bayes theorem mean?

The answer to this question becomes more evident if we convert from probability to odds

---
<!-- # Bayes theorem makes more sense if we think in odds -->
<!-- # Thinking in probability versus odds versus log odds -->

<ins>**Probability versus odds**</ins> 

<block align="middle">
<img align="middle" src="./Figures/Apply_RealisticTest.png" hspace=25 vspace=40 width="500" alt="pic"/>
</block>



<ins>Probability of disease</ins> - ratio of # diseased individuals to the total of individuals

$$P(disease)=\frac{N_{diseased}}{N_{diseased}+N_{healthy}}=\frac{10}{10+90}=\frac{1}{10}=0.1$$


<ins>Odds of disease</ins> ratio of diseased to not diseased (healthy ) individuals

$$O(disease)=\frac{N_{diseased}}{N_{Total}-N_{diseased}}=\frac{N_{diseased}}{N_{healthy}}=\frac{10}{90}=\frac{1}{9}=0.11$$

---

# Converting between odds and probabilities

$$O(disease)=\frac{P(disease)}{1-P(disease)}\qquad P(disease)=\frac{O(disease)}{1+O(disease)}$$

---

# <ins>Expressing Bayes' theorem in terms of odds</ins>

<block align="left">

$P(D|+)=\frac{P(D)P(+|D)}{P(+)}\qquad \qquad \quad \color{red}\,P(+)=P(+|D)P(D)+P(+|H)P(H)$

$P(D|+)=\frac{P(D)P(+|D)}{\color{red}P(+|D)P(D)+P(+|H)P(H)}\qquad\color{orange}\times\frac{\frac{1}{P(D)P(+|D)}}{\frac{1}{P(D)P(+|D)}}$

$P(D|+)=\color{orange}\frac{1}{1+\frac{P(+|H)P(H)}{P(+|D)P(D)}}\qquad \qquad\qquad\color{green}\frac{P(+|H)}{P(+|D)}=\frac{1}{LR^+},\color{blue}\;\frac{P(H)}{P(D)}=\frac{1-P(D)}{P(D)}=\frac{1}{O_{pre}(D)}$

$P(D|+)=\frac{1}{1+\frac{1}{\color{green}LR^+\color{blue}O_{pre}(D)}}\qquad \qquad\qquad \color{purple}rearrange$

$\color{purple}\frac{1-P(D|+)}{P(D|+)}=\frac{1}{LR^+O_{pre}(D)}\color{black} \qquad \qquad\qquad  \frac{1-P(D|+)}{P(D|+)}=\frac{1}{O_{post}(D)}$ 

<br>

$\boxed{O_{post}(D)=LR^+O_{pre}(D)}$

</block>

---

## Bayes allows us to refine a prior belief in light of new evidence

$$\boxed{\color{red}O_{post}(D)\color{black}=\color{blue}LR\color{black}*\color{green}O_{pre}(D)}$$

$$\color{red}posterior\;belief\color{black}=\color{blue}evidence\color{black}*\color{green}prior\;belief$$

<br>

Note that our new (posterior) belief depends on:
- the strength of the prior belief
- the strength of the evidence

---

$$Post_{odds}=LR*Pre_{odds}$$ 

<img align="middle" src="./Figures/PrePostOdds.png" hspace=200 vspace=2 width="800" alt="pic"/> 

---

$Post_{odds}=LR*Pre_{odds}$ <img align="middle" src="./Figures/PrePostOdds.png" hspace=100 vspace=2 width="400" alt="pic"/> 

$log Post_{odds}=\log LR + \log Pre_{odds}$ <img align="middle" src="./Figures/PrePostLogOdds.png" hspace=60 vspace=2 width="400" alt="pic"/>

$Post_{prob}=\frac{1}{1+\frac{1-Pre_{prob}}{LR*Pre_{prob}}}$ <img align="middle" src="./Figures/PrePostProb.png" hspace=60 vspace=2 width="400" alt="pic"/> 

<!-- *(Note: the math is a lot easier in odds)* -->
<!-- ###### $Post_{prob}=\frac{1}{1+\frac{1-Pre_{prob}}{LR*Pre_{prob}}}\quad Post_{odds}=LR*Pre_{odds}\quad \log Post_{odds}=\log LR + \log Pre_{odds}$  -->

---

<img align="left" src="./Figures/PrePostProb.png" hspace=100 vspace=2 width="900" alt="pic"/> 

---

A patient has a positive mammogram ($Se=97\%, Sp=64.5\%$). The background prevalence of breast cancer among similar patients is 0.2%. She has no significant additional risk factors. 


<br>

1. ***Compute the pre test and post test odds of breast cancer for this patient***

2. ***Compute post test probability***

---

A patient has a positive mammogram ($Se=97\%, Sp=64.5\%$). The background prevalence of breast cancer among similar patients is 0.2%. She has no significant additional risk factors. 

$LR^+=\frac{P(+|D)}{P(+|H)}=\frac{Se}{1-Sp}=\frac{0.97}{1-0.645}=\frac{0.97}{0.355}=2.7\approx 3$

<br>

1. ***Compute the pre test and post test odds of breast cancer for this patient***

$Pre_{odds}=\frac{0.002}{1-0.002}\approx 0.002$
$Post_{odds}=LR*Pre_{odds}=3*0.002=0.006$

2. ***Compute post test probability***

$Post_{prob}=\frac{0.006}{1-0.006}=0.00603\approx0.006$

Note how similar the odds and probabilities were in this case

---

# Odds and probability are similar when low

<block align="middle"> $\qquad O(disease)=\frac{P(disease)}{1-P(disease)}$ <img align="middle" src="./Figures/OddsVsProbability.png" hspace=6 vspace=2 width="600" alt="pic"/>
</block>

<!-- $\lim_{P(disease\to0)} 1-P(disease)\approx 1 in the $ -->

$\lim_{P(disease)\to{0}}\;(1-P(disease)) \approx 1$
$\therefore\lim_{P(disease)\to{0}}\ \; O(disease)\approx P(Disease)$

---

# This can come in handy on an exam or in practice

## Question 999

*Blah blah blah blah* **prevalence is 1%** *blah blah blah blah* **Sensitivity is 0.8, specificity is 0.9** *blah blah blah blah blah blah blah blah blah blah blah blah*

What is the probability that the patient has the disease?

A. 1%
B. 4%
C. 10%
D. 20%
E. 50%

---


## Question 999

*Blah blah blah blah* **prevalence is 1%** *blah blah blah blah* **Sensitivity is 0.8, specificity is 0.9** *blah blah blah blah blah blah blah blah blah blah blah blah*

What is the probability that the patient has the disease?

$LR^+ = \frac{Se}{1-Sp}=\frac{0.8}{1-0.9}=\frac{0.8}{0.1}=8$
$Odds_{post}=LR^+Odds_{pre}=8*\frac{0.01}{1-0.01}\approx 8*0.01=0.08$

A. 1%
B. 7%
C. 10%
D. 20%
E. 50%

---

# Caution: this doesn't work if the prevalence is not low

*Blah blah blah blah* **prevalence is $\color{red}25\%$** *blah blah blah blah* **Sensitivity is 0.8, specificity is 0.9** *blah blah blah blah blah blah blah blah blah blah blah blah*

What is the probability that the patient has the disease?

$LR^+ = \frac{Se}{1-Sp}=\frac{0.8}{1-0.9}=\frac{0.8}{0.1}=8$
$Odds_{post}=LR^+Odds_{pre}=8*\frac{0.25}{1-0.25}=8*0.33=2.64$

$Prob_{post}=\frac{Odds_{post}}{1+Odds_{post}}=\frac{2.64}{1+2.64}=\frac{2.64}{3.64}=0.73$

---

# Let's take a break to discuss the activity


---

Applying Bayes theorem we can quantify the difference between the posterior and prior disease probability, **but how do we know when this difference is clinically meaningful?**

<!-- <img align="middle" src="./Figures/BayesianValue.png" hspace=60 vspace=20  width="400" alt="pic"/> $\color{green}Prevalence\; Threshold$ 

We have to define decision thresholds - at what probability do we treat?

(For more on prevalence threshold see *J. Balayla 2020 PLos One*) -->

---

# Decision analysis

- A formal process to decision making 
- Involves estimating the expected rates of desirable and undesirable outcomes 
- Estimates are compared for the actions being considered
- Can incorporate objective and subjective criteria

---

Expected rate of thrombosis without testing/treatment  <img align="middle" src="./Figures/DecisionAnalysisControlEvents.png" hspace=300 vspace=2 height="650" width="600" /> 

---


Expected rate of thrombosis with testing based treatment  <img align="middle" src="./Figures/DecisionAnalysisThromboticEvents.png" hspace=300 vspace=2 height="650" width="600" /> 

---

# Laboratory testing and resultant treatments have associated costs and harms

- If we only consider the information we gain we risk ignoring a net loss
- Our goal is to provide a net benefit and avoid a net harm
- Not all events carry equal value, so weighting of outcomes may be necessary

---

Expected number of bleeding events with testing/treatment
<img align="middle" src="./Figures/DecisionAnalysisBleedingEvents.png" hspace=300 vspace=2 height="650" width="600" /> 

---

# Computing metrics of utility

<br>

<!-- |Metric|No testing|Testing| -->
<!-- |:---:|:---:|:---:| -->
$ER=\frac{\#Events}{\#Patients}\qquad(Event Rate)$ 
<!-- |$\frac{4+0}{100}=0.04$|$\frac{3+0}{100}=0.03$| -->

$RR=\frac{Event\,Rate_{testing}}{Event\,Rate_{control}}=\frac{\frac{3+0}{100}}{\frac{4+0}{100}}=\frac{\frac{3}{100}}{\frac{4}{100}}=0.75\qquad (Relative\,Risk)$

$RRR=1-RR=1-0.75=0.25\qquad (Relative\,Risk\,Reduction)$

$ARR=ER_{testing}-ER_{control}=\frac{3}{100}-\frac{4}{100}=-0.01\;(Abs\,Risk\,Reduction)$ 


$NNT=\frac{1}{ARR}=\frac{1}{-0.01}=-100\qquad (Number\,Needed\,to\,Test)$

<br>

(Event = thrombosis or bleed)

---

# $NNT_{net}$ needed to treat depends on prevalence

<img align="middle" src="./Figures/NNT.png" hspace=300 vspace=2 height="650" width="700" /> 

---

# Acounting for clinician/patient values

<img align="middle" src="./Figures/NNT_RelWeight.png" hspace=300 vspace=2 height="650" width="700" /> 

---

# What if we had just treated presumptively

<img align="middle" src="./Figures/NNT_PresumptivelyRx.png" hspace=300 vspace=2 height="650" width="700" /> 

---

# Alternatively test value can be determined empricially

- Results of decision analysis depends on model assumptions
- If a principled approach is not accessible an RCT paradigm can be used
  - Randomize to test vs no test, compare outcomes


---


# Unexpected Value (a note on secondary data uses)

- Development of EMR has provided new opportunities for secondary (i.e. not the primary intended use) uses for laboratory data

- The value engendered by secondary data uses <ins>**should not be considered**</ins> in the management of test utilization for clinical purposes
  - Ordering of clinical testing billed to patient/patient insurance for secondary use purposes constitutes fraud
  

---

# Learning objectives

- Describe the overlap and distinction between test accuracy and test value
- Apply Bayesian analysis to update prior given a test result
- Appreciate that lab tests have associated risks and harms
- Apply decision analysis to model test value
- List non-analytical factors that impact the value of a lab result

<br>

Course materials at: https://github.com/MarkZaydman/Lecture-TestValue.git


