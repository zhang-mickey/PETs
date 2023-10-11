# PETs
Data protection technology
### CIA
Confidentiality 
</br>
Integrity
</br>
Availability

### The 3 meanings of privacy
*Privacy as confidentiality*:disclosure of information is prevented,or in a way that cannot be linked back to the individual.
</br>
_Privacy as control_:providing individuals with means to control the disclosure of their information.
</br>
*Privacy as practie*:transparency
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
*Privacy design strategies*:Minimize(less data collected);Hide(encryption);Inform(Inform data subjects);Control(access control)
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
</br>
If metric depends on the ground truth,attacker may not be able to compute it;
If metric depends on the attacker's findings, defender may not be able to compute it;

#### Uncertainty of the adversary's findings Metrics

##### Anonymity set size
the relation between anonymity set size and k-annymity:k=anonymity set size.
##### Entropy
the closer the entropy to  1,the higher the entropy, the more "random" the data
This metric is calculated by the *data holder* to understand the uncertainty of the information that may be obtained by an attacker.
#### Metrics based on information gain

##### Amount of the leaked information
##### Relative entropy
metrics measuring the distance between the distribution found by the adversary and the real distribution.
Obly an *omnipotent entity* can claculate this.The ground truth of the real distribution is necessary to calculate it.

#### Data similarity metrics
metrics measuring the privacy provided by a dataset, without an explicit adversary.
##### k-anonymity
disregards several aspects:re-release after a change

#### Error-based metrics
metrics measuring how wrong the adversary's findings are
##### Adversary's expected estimation error
<img width="759" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/5443efa4-6364-4fa6-956e-6d22f88da290">
</br>

### Beaver's multiplication protocol(2PC)
Beaver triples are generated during the preprocessing phase. (Using OT,Beaver triple can be generated)
</br>
<img width="515" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/73fd742c-f3f3-40c8-a735-c616c7b67351">
</br>
<img width="508" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/7db9803a-fab5-4ac8-b819-162e5ee532d1">
</br>
### additive secret sharing
boolean secret sharign
<img width="574" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/519ec6e4-ff53-4427-86db-74c4dcaaffd4">
</br>

### shamir secrect sharing 



<img width="476" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/8fee5dce-cef6-4f0e-b9f2-556de2381724">

</br>
<img width="459" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/f29de629-ef20-4d93-a30a-e311a1bdc521">
</br
<img width="242" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/7b19afa2-861b-42f1-9c2d-ce352844d057">


</br>

### Oblivious transfer
oblivious transfer is efficient only when the function has constant size.
<img width="682" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/9668a677-d6f5-448f-8587-43566a57b20c">
</br>

#### implementation using asymmetric cryptography
<img width="645" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/0e59e3ef-7cdd-4ef8-86e2-bded8ef51cf7">
</br>

#### multiplying secret-shared 
<img width="643" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/f885217f-fe6f-4a6b-a3ae-e77d51370eaa">

### Goldreich-Micali-Wigderson (GMW)
sepcial case of additive secret sharing,using(OT and Boolean sectet sharing)
compute any function that can be efficiently computed.
<img width="544" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/2e2751cb-70b4-4aa4-a827-a0b422463393">
</br>
<img width="570" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/b18b4198-fcaf-4d4a-ad22-19d9586ff6b8">

</br>


### Garbled circuits
<img width="660" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/2ef299e9-4082-4a1c-9692-afc739f4035e">
</br>
<img width="644" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/64b90546-b997-44a3-b2cc-7333522ffc0e">
</br>
Instead of garbling a single gate, we are going to garble the whole circuit representation of f. How
do we garble f?
