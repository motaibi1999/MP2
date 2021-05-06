# MP2
Mohammed Alotaibi - MIA170030

PART 1: 

1) download Android Standard Libraries
2) Run AndroidInstrument
3) When you will run the file in Eclipse, please right click the java file. Then go to Run As → Run Configurations → Arguments and put,
-android-jars path/to/android-platforms -process-dir sqlite.db.apk

![Screen Shot 2021-05-06 at 12 24 02 AM](https://user-images.githubusercontent.com/61093335/117246027-740ad780-ae01-11eb-848d-28f0d1311bff.png)



![Screen Shot 2021-05-06 at 12 24 02 AM](https://user-images.githubusercontent.com/61093335/117246036-7836f500-ae01-11eb-9fb9-66ca779804c4.png)

4) a new apk file will be generated under ./sootOutput


![Screen Shot 2021-05-06 at 12 24 25 AM](https://user-images.githubusercontent.com/61093335/117246044-7bca7c00-ae01-11eb-8fd4-e30a70cc51fb.png)



PART 2: 
1) You need to upload the apk in the Github repo.
2) You need to generate a keystore once and use it to sign your unsigned apk. Use the keytool provided by the JDK found in %JAVA_HOME%/bin/keytool -genkey -v -keystore my.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias app


![Screen Shot 2021-05-06 at 12 09 08 AM](https://user-images.githubusercontent.com/61093335/117246160-ba603680-ae01-11eb-8fe1-27f48ed85c15.png)


4) zipalign -p 4 my.apk my-aligned.apk
5) jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my.keystore my-app.apk my_alias_name
6) jarsigner -verify -verbose my_application.apk
