# maven-upload

### GIT Command
```git_command
git init
git remote add origin https://github.com/rzrasel/maven-upload.git
git remote -v
git fetch && git checkout master
git add .
git commit -m "Add Readme & Git Commit File"
git pull
git push --all
```

An easy way to upload to bintray and generate pom.xml using new Maven Plugin

For more information refer to this [article](https://medium.com/@kostasdrakonakis/how-to-distribute-your-own-android-library-through-jitpack-or-jcenter-and-maven-central-from-174c356e818a)

### Step 1. Create a Sonatype account for uploading to Maven Central (Optional)
To create an issue like described, go to <a href="https://issues.sonatype.org/secure/Dashboard.jspa" data-href="https://issues.sonatype.org/secure/Dashboard.jspa" class="markup--anchor markup--p-anchor" rel="nofollow noopener" target="_blank">Sonatype Dashboard</a> and login with account created. And then click at <a href="https://issues.sonatype.org/secure/CreateIssue.jspa?issuetype=21&amp;pid=10134" data-href="https://issues.sonatype.org/secure/CreateIssue.jspa?issuetype=21&amp;pid=10134" class="markup--anchor markup--p-anchor" rel="nofollow noopener" target="_blank"><strong class="markup--strong markup--p-strong">Create</strong></a><strong class="markup--strong markup--p-strong"> </strong>placed at the top menu.

### Step 4. Enable auto signing for Bintray
First step is to generate a key via command line with the command below. (In case you use Windows, please do it under <a href="https://www.cygwin.com/" data-href="https://www.cygwin.com/" class="markup--anchor markup--p-anchor" rel="nofollow noopener" target="_blank">cygwin</a> or <a href="http://cmder.net/" data-href="http://cmder.net/" class="markup--anchor markup--p-anchor" rel="nofollow noopener" target="_blank">cmder</a>)
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

<br />
When you done with all of this modifications open terminal from Android Studio and execute the tasks:
#### Gradlew Install:

| OS | Command | Description |
| -- | ------- | ----------- |
| Windows | gradlew install | Gradlew Install |
| Mac | ./gradlew install | Gradlew Install |
| Linux | gradle install | Gradlew Install |

<br />
And after the task succesfully executed you should execute the task:
#### Bintray Upload:

| OS | Command | Description |
| -- | ------- | ----------- |
| Windows | gradlew bintrayUpload | Bintray Upload |
| Mac | ./gradlew bintrayUpload | Bintray Upload |
| Linux | gradle bintrayUpload | Bintray Upload |

<br />
Force gradle to delete cache dependencies in Mac/Linux
#### Delete Gradle Cache Dependencies:

| OS | Command | Description |
| -- | ------- | ----------- |
| Mac | rm -rf $HOME/.gradle/caches/ <br />rm -rf $HOME/.gradle/wrapper/<br /> | Delete Gradle Cache Dependencies |

<br />
Force gradle to redownload dependencies in Mac/Linux
#### Redownload Gradle Dependencies:

| OS | Command | Description |
| -- | ------- | ----------- |
| Windows | gradlew build --refresh-dependencies | Redownload Gradle Dependencies |
| Mac | ./gradlew build --refresh-dependencies | Redownload Gradle Dependencies |


<!---
When you done with all of this modifications open terminal from Android Studio and execute the tasks:
in Windows:
```
gradlew install
```
or if you are in Mac/Linux
```
gradle install
or
./gradlew install
```
-->
<!---
and after the task succesfully executed you should execute the task:
in Windows:
```
gradlew bintrayUpload
```
or if you are in Mac/Linux
```
gradle bintrayUpload
or
./gradlew bintrayUpload
```
-->
<!---
Force gradle to redownload dependencies in Mac/Linux

```
or
rm -rf $HOME/.gradle/caches/
rm -rf $HOME/.gradle/wrapper/
```
-->
<!---
Force gradle to redownload dependencies in Mac/Linux
```
gradlew build - -refresh-dependencies
or
./gradlew build - -refresh-dependencies
```
-->

Terminal / Command Line Command:

| OS | Command | Description |
| -- | ------- | ----------- |
| os | command | description |

Maven Upload Update





