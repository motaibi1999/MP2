# MP2
Mohammed Alotaibi - MIA170030

PART 1: 

1) download Android Standard Libraries
2) Run AndroidInstrument
3) When you will run the file in Eclipse, please right click the java file. Then go to Run As → Run Configurations → Arguments and put,
-android-jars path/to/android-platforms -process-dir sqlite.db.apk
4) a new apk file will be generated under ./sootOutput


PART 2: 
1) You need to upload the apk in the Github repo.
2) You need to generate a keystore once and use it to sign your unsigned apk. Use the keytool provided by the JDK found in %JAVA_HOME%/bin/
keytool -genkey -v -keystore my.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias app
3) zipalign -p 4 my.apk my-aligned.apk
4) jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my.keystore my-app.apk my_alias_name
5) jarsigner -verify -verbose my_application.apk
