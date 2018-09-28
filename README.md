# maven-upload

An easy way to upload to bintray and generate pom.xml using new Maven Plugin

For more information refer to this [article](https://medium.com/@kostasdrakonakis/how-to-distribute-your-own-android-library-through-jitpack-or-jcenter-and-maven-central-from-174c356e818a)

### Step 1. Create a Sonatype account for uploading to Maven Central (Optional)
To create an issue like described, go to <a href="https://issues.sonatype.org/secure/Dashboard.jspa" data-href="https://issues.sonatype.org/secure/Dashboard.jspa" class="markup--anchor markup--p-anchor" rel="nofollow noopener" target="_blank">Sonatype Dashboard</a> and login with account created. And then click at <a href="https://issues.sonatype.org/secure/CreateIssue.jspa?issuetype=21&amp;pid=10134" data-href="https://issues.sonatype.org/secure/CreateIssue.jspa?issuetype=21&amp;pid=10134" class="markup--anchor markup--p-anchor" rel="nofollow noopener" target="_blank"><strong class="markup--strong markup--p-strong">Create</strong></a><strong class="markup--strong markup--p-strong"> </strong>placed at the top menu.

### Step 4. Enable auto signing for Bintray
```enable_auto_signing_for_bintray
gpg --gen-key
gpg --list-keys
gpg --keyserver hkp://pool.sks-keyservers.net --send-keys PUBLIC_KEY_ID
gpg -a --export yourmail@gmail.com > public_key_sender.asc
gpg -a --export-secret-key yourmail@gmail.com > private_key_sender.asc
```

build.gradle project level
```build_gradle_project
classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.4'
classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'

1.7.3
classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'

1.8.4
classpath "com.jfrog.bintray.gradle:gradle-bintray-plugin:1.8.4"

2.1
classpath 'com.github.dcendents:android-maven-gradle-plugin:2.1'
```

build.gradle library level
```build_gradle_lib
apply from: 'https://raw.githubusercontent.com/rzrasel/maven-upload/master/bintray.gradle'
apply from: 'https://raw.githubusercontent.com/rzrasel/maven-upload/master/publications.gradle'
```

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
