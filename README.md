# maven-upload

An easy way to upload to bintray and generate pom.xml using new Maven Plugin

For more information refer to this [article](https://medium.com/@kostasdrakonakis/how-to-distribute-your-own-android-library-through-jitpack-or-jcenter-and-maven-central-from-174c356e818a)


gradle.properties file
```gradle_properties
libraryVersion = 100.00.01
libraryName = LogWriter
libraryDescription = A custom log writer for android.
publishedGroupId = com.adept.coffeelab
artifact = log-writer
bintrayRepo = CommonLibraries
bintrayName = fine-log-writer
bintray_gpg_passphrase=passphrase
bintray.gpg.password=password
siteUrl = https://github.com/rzrasel/And-Log-Writer
gitUrl = https://github.com/rzrasel/And-Log-Writer.git
developerId = developerId
developerName = Rz Rasel
developerEmail = rztest@gmail.com
licenseName = The Apache Software License, Version 2.0
licenseUrl = http://www.apache.org/licenses/LICENSE-2.0.txt
allLicenses = ["Apache-2.0"]
```

local.properties file
```local_properties
bintray.apikey=bintray api key
bintray.gpg.password=password
bintray.user=user
```
