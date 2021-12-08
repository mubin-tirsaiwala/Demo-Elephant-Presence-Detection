![Head Page](/assets/front_page_acoustics.png)

# Elephant Presence Detection from Infrasonic Rumbles
This repo is only for demonstrating Elephant presence detection project. All the development codes are kept confidential.

### Project Description :
---
> As humans continue to encroach natural settlements, Human Elephant Conflicts are on a constant rise. The giants require much larger landscape for their daily activities and their habitats are being cut down due to deforestation and urbanization. In India, around 300 people are killed annually in Human Elephant Conflicts (HEC).  

In an attempt to mitigate Human Elephant Conflicts, this project attempts to identify presence of elephants by their acoustic calls.  
To further reduce the damage, we perform acoustic surveillance of forests for illegal activities.  

#### Elephant Presence Detection :
Built on the fact that, majority of the times, elephants communicate through rumbles which are in the infrasonic range, this project aims to classify difference between infrasonic noise and rumbles.  
Being in the infrasonic range, the rumbles can travel upto **10Kms** without attenuating and we can detect elephant's presence long before their arrival.  
But in the infrasonic range, noise component is very high for which we designed specific cepstrum coefficients as features for our models.  
To take temporal nature of voice into account, we trained custom LSTM models and deployed them on ST controllers.  

#### Forest Acoustic Surveillance :
Apart from elephant presence detection, we have also designed models to perform acoustic surveillance of forest for monitoring Illegal Poaching and Timber Harvesting activity.  
Chainsaw and gunshot sounds are detected which are in the human audible range. Apart from these, we also detect elephant presence for their calls which are not in the infrasonic range.
Forest officials are alerted if any suspicious activity present.  

Currently, field validations are going on in Kerela and Assam.

### Results and Recognitions :
---
* Achieved 98% accuracy on balanced test set for elephant presence detection from infrasonic rumbles.
* Achieved 99% accuracy on balanced test set for forest surveillance models. *(Classes are Gunshots, Elephant Calls(audible range) and Chainsaw sounds.)*
* Received grants from state governments of India for working towards huge issue of HEC in many parts of the country.

### Project flow and Demonstration:
---
1. Strategically placed microphone traps are set in the forest monitoring continuously. As soon as any suspicious activity is noticed, slave controllers communicate the data to a master controller which takes further action.
2. In case of elephant rumbles detection, results are sent from multiple sources to the master controller.
3. Master controller triangulates the locations and tries to predict the location of the elephant herd.
4. A signal is sent out as an alert if distance is lower than a set threshold.

All the audio files used in the demo below can be found in [assets](/assets) folder.  
In the demo, we show how our models identify the sounds. Note that there are no hardware accelerators used for this demo and the models are not optimized for latency. These things are considered in the hardware deployment part though.