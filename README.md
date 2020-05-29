# HuMIdb database(Human Mobile Interaction database)
HuMIdb is a novel multimodal mobile database that comprises more than 5 GB from a wide range of mobile sensors acquired under unsupervised scenario.

## INSTRUCTIONS FOR DOWNLOADING HuMIdb database
1) [Download license agreement](http://atvs.ii.uam.es/atvs/licenses/HuMIdb_license_agreement.pdf), send by email one signed and scanned copy to **atvs@uam.es** according to the instructions given in point 2.
 
 
2) Send an email to **atvs@uam.es**, as follows:

   *Subject:* **[DATABASE: HuMIdb database]**

   Body: Your name, e-mail, telephone number, organization, postal mail, purpose for which you will use the database, time and date at which you sent the email with the signed license agreement.
 

3) Once the email copy of the license agreement has been received at ATVS, you will receive an email with a username, a password, and a time slot to download the database.
 

4) [Download the DATASEBASE](http://atvs.ii.uam.es/atvs/intranet/HuMIdb), for which you will need to provide the authentication information given in step 4. After you finish the download, please notify by email to **atvs@uam.es** that you have successfully completed the transaction.
 

5) For more information, please contact: **atvs@uam.es**


## DESCRIPTION OF HuMIdb DATABASE
The database includes 14 sensors (see Table 1 for the details) during natural human-mobile interaction performed by more than 600 users. For the acquisition, we implemented an Android application that collects the sensor signals while the users complete 8 simple tasks with their own smartphones and without any supervision whatsoever (i.e., the users could be standing, sitting, walking, indoors, outdoors, at daytime or night, etc.). The acquisition app was launched on Google Play Store and advertised in our research web site and various research mailing lists. After that, the participants were self-selected around the globe producing more varied participants than previous state-of-the-art mobile databases. All data captured in this database have been stored in private servers and anonymized with previous participant consent according to the GDPR (General Data Protection Regulation).

![](https://github.com/BiDAlab/HuMIdb/blob/master/Table_1.png)  
Table 1. Description of all sensor signals captured in HuMIdb. E=Event-based acquisition. The timestamp parameter is captured for all sensors.

Fig. 1 shows all tasks included in the HuMIdb. The task *a* is designed to acquire keystroking from fixed and free text. In tasks *b* and *d*, the users have to perform both swipe up and swipe down gestures to complete both tasks, meanwhile the task *c* is focused on tap gestures. Tasks *e* and *f* are designed to draw in the air with the smartphone a circle and a cross respectively. Task *g* records the user saying *‘I am not a robot’*, and finally, in task *h* the user has to draw with the finger the digits 0 to 9 over the touchscreen. Note that the 14 sensors available (see Table 1) are acquired during the execution of all tasks, although some sensors present a key role in some of them. For example, the accelerometer signal is captured during the entire session even though it could be more relevant in tasks *e* and *f*. This heterogeneous information can be used to improve the patterns obtained from the main sensor for each task. Additionally, all tasks have a right swipe button that is acquired in addition to the swipe patterns. 

![](https://github.com/BiDAlab/HuMIdb/blob/master/Figure_1.png)

Figure 1. The mobile interfaces designed for the 8 mobile HuMI tasks: *a*) keystroking, *b*) swipe up, *c*) tap and double tap, *d*) swipe down, *e*) circle hand gesture, *f*) cross hand gesture, *g*) voice, and *h*) finger handwriting.

The acquisition protocol comprises 5 sessions with at least 1 day gap among them. It is important to highlight that in all sessions, the 1-day gap refers to the minimum time between one user ﬁnishes a session and the next time the app allows to have the next session. At the beginning of each task, the app shows a brief pop-up message explaining the procedure to complete each task. The application also captures the orientation (landscape/portrait) of the smartphone, the screen size, resolution, the model of the device, and the date when the session was captured.

Regarding the age distribution, 25.6% of the users were younger than 20 years old, 49.4% are between 20 and 30 years old, 19.2% between 30 and 50 years old, and the remaining 5.8% are older than 50 years old. Regarding the gender, 66.5% of the participants were males, 32.8% females, and 0.7% others. Participants performed the tasks from 14 different countries (52.2%/47.0%/0.8% are European, American, and Asian respectively) using 179 different devices.
Fig. 2 shows an example of the handwriting task (for digit “5”) and the information collected during the task. Note how a simple task can generate a heterogeneous flow of information related with the user behavior: the way the user holds the device, the power and velocity of the gesture, the place, etc.

![](https://github.com/BiDAlab/HuMIdb/blob/master/Figure_2.png)  
Figure 2. Full set of data generated during one of the HuMIdb task.

#### HuMIdb STRUCTURE
The structure of HuMIdb is described in Figure 3; the data is stored in nested folders with the MAC number to identify each user´s folder. Inside the user´s folder, there are between 1 and 5 folders corresponding to the different sessions the user has completed and 3 CSV files with the Bluetooth, WiFi and GPS data signals acquired during the entire session. Finally, in each session there are one folder for each task that contains all sensors captured during the task. The *'swipe.csv'* file corresponds to the right swipe button.

![](https://github.com/BiDAlab/HuMIdb/blob/master/Figure_3.png)  
Figure 3. Structure of the nested folders of HuMi database: User→ Sessions→ Tasks→ Sensors.

#### FILES FORMAT
+ info.json file: it contains information related to the smartphone used. ScreenWidth, screenHeight, numberWidth, numberHeight, mac, lenguage, mail, gender, age, num_session (completed), time_session1, time_session2, time_session3, time_session4, time_session5, model.

+ bluetooh.csv files:  

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the name of the bluetooth transmitter.

  + COLUMN 3: represents the MAC.

+ gps.csv files:  

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the latitude.  
  
  + COLUMN 4: represents the longitude.

  + COLUMN 5: represents the altitude.

  + COLUMN 6: represents the bearing.

  + COLUMN 7: accuracy.
  
+ wifi.csv files:  

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the name.

  + COLUMN 3: represents the level.  
  
  + COLUMN 4: represents the info.

  + COLUMN 5: represents the chanel.

  + COLUMN 6: represents the frequency.
  
+ micro.3gp files: audio data.

+ Touch gesture files (swipe.csv, f_X_touch.csv, scroll_X_touch.csv, and touch_touch.csv):

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the x coordinate data.  
  
  + COLUMN 4: represents the y coordinate data.

  + COLUMN 5: represents the pressure.

  + COLUMN 6: represents the action (finger_down= 0, movement= 2, finger_up= 1).
  
+ sensor_grav.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the gravity data.
  
+ sensor_gyro.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the x axis data of the gyroscope.  
  
  + COLUMN 4: represents the y axis data of the gyroscope.
  
  + COLUMN 5: represents the z axis data of the gyroscope.
  
+ sensor_humd.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the humidity data.  
  
+ sensor_lacc.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the x axis data of the linear accelerometer.  
  
  + COLUMN 4: represents the y axis data of the linear accelerometer.
  
  + COLUMN 5: represents the z axis data of the linear accelerometer.
  
+ sensor_ligh.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the light level data.
  
+ sensor_magn.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the x axis data of the magnetometer.  
  
  + COLUMN 4: represents the y axis data of the magnetometer.
  
  + COLUMN 5: represents the z axis data of the magnetometer.
  
+ sensor_nacc.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the x axis data of the accelerometer.  
  
  + COLUMN 4: represents the y axis data of the accelerometer.
  
  + COLUMN 5: represents the z axis data of the accelerometer.
  
+ sensor_prox.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the proximity level data.

+ sensor_temp.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the orientation (portrait= 1, landscape= 0).

  + COLUMN 3: represents the temperature data.
  
+ key_data.csv files:

  + COLUMN 1: represents the timestamp in miliseconds.

  + COLUMN 2: represents the entry field where it was typed (N= name, S= surname, A= age, T= text). (See Fig. 1 task *a* for details)

  + COLUMN 3: represents the ASCII code of the key typed.
  
#### REFERENCES
For further information on the benchmark and on different applications where it has been used, we refer the reader to (all these articles are publicly available in the [publications](http://atvs.ii.uam.es/atvs/listpublications.do) section of the BiDA group webpage).

+ [1] A. Acien, A. Morales, J. Fierrez, R. Vera-Rodriguez, O. Delgado-Mohatar, "BeCAPTCHA: Bot Detection in Smartphone Interaction using Touchscreen Biometrics and Mobile Sensors", arXiv:2005.13655, 2020. [[pdf](https://arxiv.org/ftp/arxiv/papers/2002/2002.00918.pdf)]

Please remember to reference article [1] on any work made public, whatever the form, based directly or indirectly on any part of the HuMI database.
