# PETs
Data protection technology
## possible disclosure formats
(1)Disclosing only a set of previously determined aggregates  
(2)Allowing specific queries to the database  
(3)Disclosing microdata  

### CIA
`Confidentiality` 
</br>
`Integrity`: information modification
</br>
`Availability`

### The 3 meanings of privacy
`Privacy as confidentiality`:disclosure of information is prevented,or in a way that cannot be linked back to the individual.
</br>
`Privacy as control`:providing individuals with means to control the disclosure of their information.
</br>
`Privacy as practie`:transparency
(privacy as practice was not applied as users did not have information about how secure the data storage was)
</br>
### A taxonomy of data privacy-4 dimensions
'Purpose': Single, Reuse same, Reuse selected, Reuse any, Any
</br>
'Visibility': Owner, Third Party, All
</br>
`Granularity`: What level of detail is made available?  
Existential, Partial, Specific
</br>
`Retention`:For how long is the data kept?
### Techniques to support privacy
`Privacy design strategies`:  
Minimize(less data collected);Hide(encryption);Inform(Inform data subjects);Control(access control)
</br>
`Privacy design patterns`:during System design  
Support the concept of` privacy by design`  
Use of dummies; Anonymous&pseudonymity
`Privacy-enhancing technologies`:during system development


### GDPR
`data subject`:natural person  
`Personal data`:any information relating to an identified or identifiable natural person.  
`identifiable natural person`: one who can be identified ,directly or indirectly.
`Processing`: any operation or set of operations which is performed on personal or on sets of personal data.  
`Controller`: natural or legal person, public authority, agency or other body which, alone or jointly with others, *determines the purposes and means of the processing of personal data*
</br>
`Processor`:natural or legal person, public authority, agency or other body which processes personal data on behalf of the controller.  
GDPR does not talk about ownership of data.  

#### GDPR stipulates obligations for controllers

#### Possible legal bases for processing personal data
(1) Consent of the data subject
</br>
(2)Necessary for the performance of a contact  
(3)Public interest
</br>
(3)Vital interest of the data subject
</br>

### Adversary model
Passive adversary ; Active adversary
</br>
`Computationally unbounded adversary`: information-theoretic or unconditional 
Computational bounded adversary
</br>
Honest-but-curious;Malicious
</br>
Local;Global
Internal;External;
Static;Adaptive
</br>

## Privacy metrics(measure the level of data protection)


such metrics describe protection against a given type pf adversary.Different adversary types may require different metrics
<img width="382" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/2e3aa354-510d-45b3-af6d-bb2e0dfd0461">
</br>

#### who can calculate the metrics
defender, attacker, all-knowing entity
</br>
If metric depends on the ground truth,attacker may not be able to compute it;  
If metric depends on the attacker's findings, defender may not be able to compute it;  

### Uncertainty of the adversary's findings Metrics

#### Anonymity set size
The anonymity set for a data subject x is the set of data subjects that the adversary cannot distinguish from x.
the relation between anonymity set size and k-annymity:k=anonymity set size.
#### Entropy
Consider probabilities  
the closer the entropy to  1,the higher the entropy, the more "random" the data  
the entropy is highest if all values have the same probability  
This metric is calculated by the *data holder* to understand the uncertainty of the information that may be obtained by an attacker.

### Metrics based on information gain


#### Amount of the leaked information
Number of disclosed information items  
do not consider the sensitivity of different pieces of information.

#### Relative entropy(Kullback-Leibler Divergence)
metrics measuring the distance between the distribution found by the adversary(Q) and the real distribution(P).  
IF P and Q are the same, the adversary was highly successful.
Obly an *omnipotent entity* can claculate this.The ground truth of the real distribution is necessary to calculate it.
<img width="248" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/bb79c51e-351c-491a-8079-6c8a68f361c9">

</br>

### Data similarity metrics
metrics measuring the privacy provided by a dataset, without an explicit adversary.
#### k-anonymity
this technique based on generalization will
reduce data availability
</br>
<img width="287" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/04b8c9d2-122b-4a69-911f-dfeb25fb2c99">

</br>
<img width="335" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/6efbff02-85b7-4091-b235-537cda8bcf25">

</br>
disregards several aspects:re-release after a change  
can not prevent attribute disclosure
</br>
*attacks on k-anonymity*: 
</br>
homogeneity attack;
</br>
background knowledge attack

#### Indistinguishability metrics
`differential privacy`  
`Geo-indistinguishability`

### metrics measuring the adversary's success
#### Adversary's success rate
Probability that the adversary can compromise a data record.  
Ratio of successes for the adversary, in a large number of attempts.  


### Error-based metrics
metrics measuring how wrong the adversary's findings are
#### Adversary's expected estimation error
Expected value of the distance between the ground truth and the adversary's guess
</br>
<img width="759" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/5443efa4-6364-4fa6-956e-6d22f88da290">
</br>
### Time-based metrics
Metrics measuring the time needed by either the adversary or the defender to win.  

### metrics based on accuracy/precision
#### size of uncertainty region
Adversary manages to narrow down the data subject's position to a region R. 


### Beaver's multiplication protocol(2PC)
Beaver triples are generated during the preprocessing phase. (Using OT,Beaver triple can be generated)  
Beaver triplets can be used in the multiplication of secret-shared numbers.  
If a multiplication triplet is reused in further multiplications, this leaks information  
</br>
<img width="515" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/73fd742c-f3f3-40c8-a735-c616c7b67351">
</br>
<img width="508" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/7db9803a-fab5-4ac8-b819-162e5ee532d1">
</br>
### additive secret sharing
boolean secret sharign
<img width="574" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/519ec6e4-ff53-4427-86db-74c4dcaaffd4">
</br>
### Multiplication protocol
Assumption: a precomputed multiplication triplet
a,b are random numbers  
c = a × b  
a,b,c are secret-shared: P1 has a1,b1,c1; P2 has a2,b2,c2;  
Multiplication of secret0shared numbes x and y:
P1 computes x1-a1;  
P2 computes x2-a2;  
They reconstruct x-a;  
P1 computes y1-b1;  
P2 computes y2-b2;  
They reconstruct y-b;  
x × y =(x-a+a)×(y-b+b)=(x-a)×(y-b)+(x-a) × b +(y-b) × a + c  
one of them computes (x-a)×(y-b)  
P1 computes (x-a) × b1+(y-b) × a1 + c1  
p2 computes (x-a) × b2+(y-b) × a2 + c2

### shamir secrect sharing 



<img width="476" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/8fee5dce-cef6-4f0e-b9f2-556de2381724">

</br>
<img width="459" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/f29de629-ef20-4d93-a30a-e311a1bdc521">
</br
<img width="242" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/7b19afa2-861b-42f1-9c2d-ce352844d057">


</br>

### Oblivious transfer
oblivious transfer is efficient only when the function has constant size.  
OT is based on asymmetric cryptography, which is costly.  
<img width="682" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/9668a677-d6f5-448f-8587-43566a57b20c">
</br>

#### implementation using asymmetric cryptography
Only Alice has the private key needed for decryption;  
Encryption can be done by anyone using Alice's public key;  
<img width="645" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/0e59e3ef-7cdd-4ef8-86e2-bded8ef51cf7">
</br>

#### using OT to  do multiplying secret-shared 
<img width="643" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/f885217f-fe6f-4a6b-a3ae-e77d51370eaa">

#### 1-out-of -n OT
a possible reduction to standart OT  
Alice and BOb perform n-1 standard OTs.  


### Goldreich-Micali-Wigderson (GMW)
sepcial case of additive secret sharing,using(OT and Boolean sectet sharing)
</br>
compute any function that can be efficiently computed.
</br>
For some gates, the two parties perform the same steps, for other gates ,they perform different steps.  
Requires interacction for each AND gate → potentially large number of communication rounds.  
</br>
<img width="453" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/6e70cd21-5fca-4c96-9636-3f90fe3942b5">

</br>
<img width="544" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/2e2751cb-70b4-4aa4-a827-a0b422463393">
</br>
<img width="570" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/b18b4198-fcaf-4d4a-ad22-19d9586ff6b8">
</br>
Requires interaction for each AND gate→ potentially large number of communication rounds.
</br>

#### Boolean circuit for the millionaires problem

### Garbled circuits
also using OT, but without using additive or Boolean secret-sharing  
the roles of the parties are asymmetric  
constant number of communication rounds.  
<img width="660" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/2ef299e9-4082-4a1c-9692-afc739f4035e">
</br>
<img width="644" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/64b90546-b997-44a3-b2cc-7333522ffc0e">
</br>
Instead of garbling a single gate, we are going to garble the whole circuit representation of f. How
do we garble f?

#### free-XOR
For an XOR gate, no garbled table is created.  
Alice chooses a random number R of the same length as the labels,  

#### non-garbled outputs
Alice uses the real values (0 or 1) as labels for the output wires.  
Bob learns the result directly, without further communication.  
Only applicable if Bob should learn the result.  

## Homomorphic encryption
Implementing MPC using HE  
### GC with Bob having no imput can be seen as an implementation of HE

### Partially homomorphic encryption
one operation can be evaluated homomorphically
#### RSA 
#### Benaloh :homomorphic addition
#### ElGamal:homomorphic multiplication
#### Paillier:homomorphic addition

### Somewhat homomorphic encryption
Multiple operations can be evaluated homomorphically, but only a limited number of times
#### Garbled circuits
unbounded, but predefined number of homomorphic Boolean operations  
Ciphertext size grows with every operation significantly  
#### BGN

#### SYY
### Fully homomorphic encryption
Multiple operations can be evaluated homomorphically an unlimited number of times
#### DGHV
Enc(m):  c = m+2r+p × q  
Dec(c):   (c mod p) mod 2  
Works if m+2r<p  
c1+c2=(m1+m2)+2(r1+r2)+p(q1+q2)  
c1*c2=( m1+2r1)(m2+2r2)+p(pq1q2+m1q2+m2q1+2r1q2+2r2q1)  
(c1+c2) mod p= (m1+m2)+2(r1+r2)  
c1*c2 mod p=( m1+2r1)(m2+2r2)  
密文之和的噪音是各自密文的噪音之和；而密文乘积的噪音是噪音之积  

### Possible disclosure formats
`Disclosing only a set of previously determined aggregates`
`Allowing specific queries to the database`
`Disclosing microdata`
#### quasi-identifiers
attributes whose values when taken together can potentially identify an individual.

### l-diversity
<img width="339" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/893496ad-99f6-42f7-a264-3563255c478f">

</br>
*Skewness attack*:l-diversity disregards the skewness of the overall distribution
</br>
*Similarity attack*:l-diversity disregards the semantic similarity among attribute values

#### distinct l-diversity
ensure there are at
least l distinct values for the sensitive attribute in each
equivalence class.
</br>
No protection against probabilistic inference
</br> 
#### Entropy l-diversity
<img width="321" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/5fa440cc-cf26-47ea-aa5c-b25e0d61e571">


</br>

#### Recursive l-diversity
<img width="320" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/f4049521-07b4-4bd9-875e-e7d391e21be6">

</br>

### t-closeness:privacy beyond k-anonymity and l-diversity
the distance between the two distribution should be no more than a threshold t.  

#### Vatiational distance 

#### Kullback-Leibler distance 

#### Earth mover distance

## differential privacy
### ϵ -differential privacy

### privacy budget ϵ
Privacy hyper-parameter,indicating the maximum distance permitted between the query results for two adjacents datasets.
`Impact on noise`  
Smaller ϵ, higher amount of noise.

### scale
statistical dispersion of the probability distribution. In this context, the spread of the DP query results.  
`Impact on noise`  
The higher the scale, the higher the proability of high noise.
#### Laplace mechanism
<img width="535" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/576eaed0-489f-4df2-ab4d-1e97c2bc9f66">
</br>

### sensitivity
Sensitivity of the query,representing the maximum possible change in the query output if a subject is added, removed, or changed in the dataset.  
<img width="570" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/f2689b48-c057-40d6-8f28-2a28cce94116">
</br>
`Impact on noise`  
with ϵ being constant, higher sensitivity will lead to higher s becase s = ▲/ϵ， which means there is a high probability of high noise being added to query result. 




#### example
<img width="407" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/c5d6aa42-8dda-438e-86c2-cb9095765b11">


## Access control
DAC(Discretionary access control)
</br>
MAC(Mandatory access control)
</br>
*Access control matrix*
Conceptual representation,not practical as a real implementation.
### RBAC（Role-Based Access Control）
Users can have several roles.
### ABAC（Attribute-Based Access Control）
<img width="565" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/85933e86-7fcf-44b0-b02a-bf5f26f7803a">
</br>
In theory, you could even give the same person different permissions based on where the person logs in or what the person tries to do on a different day of the week.

#### Usage Control (A generalization of attribute-based access control)

### Bell-LaPadula scheme

## Policy management
Policy: a set of access control rules.
</br>
Policy languages: XACML

## TEE

### static TEE solutions
predefined protected area
### dynamic TEE soluctions
protected areas can be defined on the fly
#### Intel SGX
Secure enclaves
</br>
Enclave content is encrypted
</br>
Encryption key is only stored in the CPU


## anonymous communication
Encryption can be used to protect the content of communication.  
However, metadata remains unprotected.  
like  
(1)Sender  
(2)Receiver  
(3)time  
(4)Number of messages  
Anonymous communication aims at keeping metadata secret.
### protecting the sender
`Sender-message unlinkability`: it is not noticeable who sends which message.  
`Sender-receiver unlinkability`: it is not noticeable who sends to whom.  
`Sender unobservability`:it is not noticeable whether a potential sender sends.  
### protection against attacks based on message length:
`Padding`  
### protection against attacks based on timing:
`Artificial delays in message forwarding`

### Mix(delay-tolerant)
A mix collects a given number of incoming messages into a batch, then flushes them out in lexicographic order.  
Thus avoiding timing-based attacks.  
</br>
<img width="385" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/7c397423-737e-4cf5-bcf7-47178eaf6810">
</br>

Mix networks work well when the traffic is high  
Appropriate for delay-tolerant applications  
application:anonymous e-mail.  
#### Mix selection strategies
Selection based on reputation  
#### Flushing strategies
`Threshold mix`: flush when number of incoming messages is larger than a threshold  
`Continuous mix`: flush out messages individually after a ramdom delay  
`Pool mix`: only flush out a fraction of the batch, keep the rest for later.  

### onion routing(latency- critical)
Encryption is done in layers. Alice and server1 exchanges keys and she encrypts her message. Then, Alice and server2 exchanges keys and she encrypts again, creating layers of encryption. Alice then sends the whole layered encrypted message to Bob, and each server will only be decrypt a layer to reveal the address of the other server, which will finally lead to Bob.

### Mix networks versus onion routing
`Difference`: Mixes delay forwarding,onion routers forward immediately.  
so mix is resistant against timing analysis.  
onion routing is fast, allowing use in latency-critical scenarios  
Onion routing targets lower layer in networking stack  
In contrast, mix networks are application-specific.




### Random walk
peer to peer communication  
random selection of next node  
the destination replies are relayed through the same nodes in reverse order.  
Lower p=more walking
Higher p=risk of de-anonymization  
formula for the expected length of the walk: 1/p

### unlinkability versus unobservability
The protocols so far achieve sender unlinkability, but not sender unobservability.  
Dummy traffic can be added to achieve also unobservability.  
### DCnet
Suppose, for example, that after the coin tossing, cryptographer A and B share a secret bit 1, A and C share 0
, and B and C share 1.

#### Dining cryptographers(DC) problem
<img width="841" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/40892815-97c3-4c20-8275-1ce7f7eac018">
</br>

##### Further mechanisms to handle
`Collisions`  : If two cryptographers paid for the dinner, their messages will cancel each other out, and the final XOR result will be 
0.
`Disruptions`:Any malicious cryptographer who does not want the group to communicate successfully can jam the protocol so that the final XOR result is useless, simply by sending random bits instead of the correct result of the XOR. This problem occurs because the original protocol was designed without using any public key technology and lacks reliable mechanisms to check whether participants honestly follow the protocol.

### Attacks on machine learning

#### poisoning attack
#### Evasion attack
#### Impersonate attack
#### Inversion attack
Aim: reconsturct training data
#### Membership inference attack
Train several shadow models with similar structure on similar data.

### countermeasure in the training phase
</br>
<img width="742" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/b6b907da-338b-4ffa-b8a8-ed764b47959c">

</br>

### Protecting integrity
#### Reject on Negative Impact(RONI)
</br>
The RONI technique can help to reduce the risk of poisoning attacks.

#### Adversarial training
Include adversarial samples in the training data, with the correct label
### DPSGD
If the gradients are not bounded, we’ll make them so ourselves! Let C be the target bound for the maximum gradient norm. For each sample in the batch, we compute its parameter gradient and if its norm is larger than C, we clip the gradient by scaling it down to C. Mission accomplished — all the gradients now are guaranteed to have norm bounded by C, which we naturally call the clipping threshold. 

### Machine learning as a Service
#### Secure neural network inference as 2PC
discuss the pros and cons of 2 servers performing a 2 party secure neural network inference protocol instead of server and client performing
## Location privacy
### Location perturbation
Position d changed to a different value d'  
The distance(d,d') determines the trade-off between utility and privacy.  
### Cloaking(Spatial)
Position replaced with a region  
The larger the region. the lower the utility  
Number of users in the region determines privacy(anonymity set size).
</br>

### Location l-diversity
Users in the cloaking region have at least l semantically different locations.

### Spatiotemporal cloaking
### Dummy locations
Adding locations of fake persons
#### Adaptive-interval cloaking
The desired degree of anonymity is specified by the parameter kmin, the minimum acceptable anonymity set size.   
<img width="511" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/3794ad49-50d2-4ad8-bdbd-7d81b05a45a8">

#### Mix zone
No location tracking within the mix zone  
Users are assigned new pseudonyms when leaving the mix zone.  
### Geo-indistinguishability
the user's location x is not distinguishable from any other location z within a radius r form x  
level of distinguishability:l = ε × r

### Distance between positions

#### Euclidean(planar) distance

#### Spherical distance
### Distance between trajectories

#### Frechet distance
Distance between two curves
</br>
Suppose a man is walking a dog. Assume the man is walking on one curve and the dog on
another curve. Both can adjust their speeds but are not allowed to move backwards. The Frechet distance of ´
the two curves is then the minimum length of leash necessary to connect the man and the dog.
</br>
<img width="548" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/3d037786-38da-46a2-9986-a0a5e07c19eb">
</br>
<img width="372" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/a81a4a99-aeb3-4a70-b81d-761739d579dc">
</br>
calculate all possible couplings between the two poly-lines. 
```
AC, BD, BE
AC, AD, BE
```
```
AC = 1, BD = 1, BE = 2
AC = 1, AD = √2/2, BE = 2
```
The Fréchet distance is the smallest of the maximum pairwise distances. In this case, both maxima are two, so the minimum of both is also 2.
#### Dynamic time wraping
Dynamic time warping does not require sequence pairs of the same length.
<br>
<img width="485" alt="image" src="https://github.com/zhang-mickey/PETs/assets/145342600/d3ccce9c-41b4-4e26-8c3b-19123eef3ba2">

</br>
Find the best matching between two discrete signal sequences
</br>
dynamic programming to compute DTW distance
</br>
