# HuMIdb dataset (Human Mobile Interaction database)
HuMIdb dataset, a novel multimodal mobile database that comprises more than 5 GB from a wide range of mobile sensors acquired under unsupervised scenario.

## INSTRUCTIONS FOR DOWNLOADING HuMIdb dataset
1) [Download license agreement](http://atvs.ii.uam.es/atvs/licenses/HuMIdb_license_agreement.pdf), send by email one signed and scanned copy to **atvs@uam.es** according to the instructions given in point 2.
 
 
2) Send an email to **atvs@uam.es**, as follows:

   *Subject:* **[DATABASE: HuMIdb dataset]**

   Body: Your name, e-mail, telephone number, organization, postal mail, purpose for which you will use the database, time and date at which you sent the email with the signed license agreement.
 

3) Once the email copy of the license agreement has been received at ATVS, you will receive an email with a username, a password, and a time slot to download the database.
 

4) [Download the DATASET](http://atvs.ii.uam.es/atvs/intranet/HuMIdb), for which you will need to provide the authentication information given in step 4. After you finish the download, please notify by email to **atvs@uam.es** that you have successfully completed the transaction.
 

5) For more information, please contact: **atvs@uam.es**


## DESCRIPTION OF HuMIdb DATASET
The dataset includes 14 sensors (see Table 1 for the details) during natural human-mobile interaction performed by more than 600 users. For the acquisition, we implemented an Android application that collects the sensor signals while the users complete 8 simple tasks with their own smartphones and without any supervision whatsoever (i.e., the users could be standing, sitting, walking, indoors, outdoors, at daytime or night, etc.). The acquisition app was launched on Google Play Store and advertised in our research web site and various research mailing lists. After that, the participants were self-selected around the globe producing more varied participants than previous state-of-the-art mobile databases. All data captured in this database have been stored in private servers and anonymized with previous participant consent according to the GDPR (General Data Protection Regulation).

![](https://github.com/BiDAlab/HuMIdb/blob/master/Table_1.png)  
Table 1. Description of all sensor signals captured in HuMIdb. E=Event-based acquisition. The timestamp parameter is captured for all sensors.

Fig. 1 shows all tasks included in the HuMIdb. The task *a* is designed to acquire keystroking from fixed and free text. In tasks *b* and *d*, the users have to perform both swipe up and swipe down gestures to complete both tasks, meanwhile the task *c* is focused on tap gestures. Tasks *e* and *f* are designed to draw in the air with the smartphone a circle and a cross respectively. Task *g* records the user saying *‘I am not a robot’*, and finally, in task *h* the user has to draw with the finger the digits 0 to 9 over the touchscreen. Note that the 14 sensors available (see Table 1) are acquired during the execution of all tasks, although some sensors present a key role in some of them. For example, the accelerometer signal is captured during the entire session even though it could be more relevant in tasks *e* and *f*. This heterogeneous information can be used to improve the patterns obtained from the main sensor for each task. Additionally, all tasks have a right swipe button that is acquired in addition to the swipe patterns. 

![](https://github.com/BiDAlab/HuMIdb/blob/master/Figure_1.png)

Figure 1. The mobile interfaces designed for the 8 mobile HuMI tasks: *a*) keystroking, *b*) swipe up, *c*) tap and double tap, *d*) swipe down, *e*) circle hand gesture, *f*) cross hand gesture, *g*) voice, and *h*) finger handwriting.



The acquisition protocol comprises 5 sessions with at least 1 day gap among them. It is important to highlight that in all sessions, the 1-day gap refers to the minimum time between one user ﬁnishes a session and the next time the app allows to have the next session. At the beginning of each task, the app shows a brief pop-up message explaining the procedure to complete each task. The application also captures the orientation (landscape/portrait) of the smartphone, the screen size, resolution, the model of the device, and the date when the session was captured.

Regarding the age distribution, 25.6% of the users were younger than 20 years old, 49.4% are between 20 and 30 years old, 19.2% between 30 and 50 years old, and the remaining 5.8% are older than 50 years old. Regarding the gender, 66.5% of the participants were males, 32.8% females, and 0.7% others. Participants performed the tasks from 14 different countries (52.2%/47.0%/0.8% are European, American, and Asian respectively) using 179 different devices.
Fig. 1 shows an example of the handwriting task (for digit “5”) and the information collected during the task. Note how a simple task can generate a heterogeneous flow of information related with the user behavior: the way the user holds the device, the power and velocity of the gesture, the place, etc.

Fig. 2 shows an example of the handwriting task (for digit “5”) and the information collected during the task. Note how a simple task can generate a heterogeneous flow of information related with the user behavior: the way the user holds the device, the power and velocity of the gesture, the place, etc.

![](https://github.com/BiDAlab/HuMIdb/blob/master/Figure_2.png)  
Figure 2. Full set of data generated during one of the HuMIdb task.

#### HuMIdb STRUCTURE
THe structure of HuMIDV is described in Figure 3; the data is stored in nested folders with the MAC number to identify each user´s folder. Inside the user´s folder, there are between 1 and 5 folders corresponding to the different sessions the user has completed and 3 CSV files with the Bluetooth, WiFi and GPS data signals acquired during the entire session. Finally, in each session there are one folder for each task that contains all sensors captured during the task.

![](https://github.com/BiDAlab/HuMIdb/blob/master/Figure_3.png)  
Figure 3. Structure of the nested folders of HuMi database: User→ Sessions→ Tasks→ Sensors.

#### FILES FORMAT
+ .txt files: it just contains two columns with the **{x̂, ŷ}** mouse coordinates.
  + COLUMN 1: represents the **x̂** coordinate.

  + COLUMN 2: represents the **ŷ** coordinate.

+ .ana files: each row contains a log-normal signal extracted from the synthetic mouse trayectory, this log-normal signal is definded by 6 parameters. One parameter in each column:  

  + COLUMN 1: represents the *D* parameter.

  + COLUMN 2: represents the *t<sub>0</sub>* parameter.

  + COLUMN 3: represents the *μ* parameter.

  + COLUMN 4: represents the *σ* parameter.

  + COLUMNS 5 : represents the *θ<sub>s</sub>* parameter.
  
  + COLUMNS 6 : represents the *θ<sub>e</sub>* parameter.
  
  + COLUMNS 7, 8: are zeros.
  

#### FILES NOMENCLATURE
The nomenclature followed to name the files of the function-based method is: NNNN_y=A_vp=B_task=C.txt

+ NNNN: indicates the number of the sample.

+ A: indicates the shape of the trajectory:

  + 0 = linear.
  
  + 1 = quadratic.
  
  + 2 = exponential.
  
+ B: indicates the velocity profile:

  + 0 = constant velocity.
  
  + 1 = logarithmic velocity.
  
  + 2 = Gaussian velocity.
  
  
+ C: indicates the task (1-8) of the human mouse database in which the trayectory was synthetized. This is necessary because the function-based method needs the initial [*x̂<sub>1</sub>, ŷ<sub>1</sub>*] and the end [*x̂<sub>M</sub>, ŷ<sub>M</sub>*] points of the human trayectory to synthetyse.
.
#### REFERENCES
For further information on the benchmark and on different applications where it has been used, we refer the reader to (all these articles are publicly available in the [publications](http://atvs.ii.uam.es/atvs/listpublications.do) section of the BiDA group webpage).

+ [1] A. Acien, A. Morales, J. Fierrez, R. Vera-Rodriguez. BeCAPTCHA-Mouse: Synthetic Mouse Trajectories and Improved Bot Detection. *arXiv:2005.00890*, 2019. [[pdf](https://arxiv.org/pdf/2005.00890.pdf)]

+ [2] C. Shen, Z. Cai, X. Guan, R. Maxion. Performance evaluation of anomalydetection algorithms for mouse dynamics, *Computers & Security*, 45: 156–171, 2014.

+ [3] M. Djioua, R. Plamondon. A new algorithm and system for the characterization of handwriting strokes with delta-lognormal parameters, *IEEE Transactions on Pattern Analysis and Machine Intelligence*, 31(11): 2060–2072, 2009.

Please remember to reference article [1] on any work made public, whatever the form, based directly or indirectly on any part of the BeCAPTCHA-Mouse benchmark.
