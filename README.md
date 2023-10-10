# PETs
Data protection technology
### CIA
Confidentiality 
Integrity
Availability
### The 3 meanings of privacy
Privacy as confidentiality:disclosure of information is prevented,or in a way that cannot be linked back to the individual.
</br>
Privacy as control:providing individuals with means to control the disclosure of their information.
</br>
Privacy as practie:transparency
(privacy as practice was not applied as users did not have information about how secure the data storage was)
</br>
### A taxonomy of data privacy-4 dimensions
Purpose: Reuse any
</br>
Visibility: Third Party, All
</br>
Granularity: Specific
</br>
Retention
### Techniques to support privacy
Privacy design strategies:Minimize(less data collected);Hide(encryption);Inform(Inform data subjects);Control(access control
</br>
System design: Use of dummies; Anonymous&pseudonymity
### Adversary types
Passive adversary ; Active adversary
</br>
Computationally unbbounded adversary; Computational bounded adversary
</br>
Honest-but-curious;Malicious
</br>
Local;Global
Internal;External;
Static;Adaptive
</br>
### Privacy metrics(measure the level of data protection)
such metrics describe protection against a given type pf adversary.Different adversary types may require different metrics
#### who can calculate the metrics
defender, attacker, all-knowing entity
If metric depends on the ground truth,attacker may not be able to compute it;
If metric depends on the attacker's findings, defender may not be able to compute it;

#### Uncertainty of the adversary's findings Metrics

##### Anonymity set size
the relation between anonymity set size and k-annymity:k=anonymity set size.
##### Entropy
the closer the entropy to  1,the higher the entropy, the more "random" the data
This metric is calculated by the data holder to understand the uncertainty of the information that may be obtained by an attacker.
#### Metrics based on information gain

##### Amount of the leaked information
##### Relative entropy
metrics measuring the distance between the distribution found by the adversary and the real distribution.
Obly an omnipotent entity can claculate this.The ground truth of the real distribution is necessary to calculate it.

#### Data similarity metrics
metrics measuring the privacy provided by a dataset, without an explicit adversary.
##### k-anonymity
disregards several aspects:re-release after a change

#### Error-based metrics
metrics measuring how wrong the adversary's findings are
##### Adversary's expected estimation error
<img width="759" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/5443efa4-6364-4fa6-956e-6d22f88da290">
