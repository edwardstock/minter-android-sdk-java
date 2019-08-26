# minter-android-sdk-java
Simple guide to help integrate Minter's SDK within pure Java/Kotlin project

## How to use Minter Android SDK within pure Java/Kotlin project

 1. Download required SDK from official bintray repository: https://bintray.com/minterteam/android
 2. There are 4 files: 
    - *-javadoc.jar
    - *-sources.jar
    - *.aar
    - *.pom
    
    You need *.aar one.
 3. AAR archive is an Android Archive. It's just a zip file, you can unzip it using `unzip`: 
 `unzip minter-android-core.aar`, or just rename `aar` file to `zip` and do it with preferred tool.
 4. After extraction, there will be stored some files. You need only **classes.jar**. Rename this file to library name. Example:
 we was download **minter-android-core** library, unpacked minter-android-core-0.4.0.zip; find in unpacked drectory **classes.jar** and rename it ito **minter-android-core-0.4.0.jar**
 5. Important thing: if you're want to sign transactions with minter-android-blockchain SDK, you MUST build or just download native JNI libraries for your system:
    * OSX (darwin): [link](https://github.com/edwardstock/minter-android-sdk-java/raw/master/res/minter_libs_darwin_amd64.zip)
    * Windows (64bit): [link](https://github.com/edwardstock/minter-android-sdk-java/raw/master/res/minter_libs_win64_x86_64.zip)
    * Linux: [link](https://github.com/edwardstock/minter-android-sdk-java/raw/master/res/minter_libs_linux_amd64.zip)
    
 6. Next: as android have some own classes, you should add it to your project as mocks (dummy classes with required names):
 [link](https://github.com/edwardstock/minter-android-sdk-java/raw/master/res/android_parcel_mocks.zip)
 
 7. Last important thing: to use native JNI libraries, java MUST know where are they located. You can try one of variants:
    - add JVM flag `-Djava.library.path=/path/to/native_libs`;
    - store libraries into system's library directory:
      - Linux: /usr/local/lib or /usr/lib
      - Darwin: /usr/local/lib
      - Windows: %windir%\System32 (??? - not sure)
    - try to add lib files directly to project dir (could work on windows, but not guaranteed)
 
 7. Example projects for pure java:
    * Gradle: [link](https://github.com/edwardstock/minter-android-sdk-java/raw/master/res/minter-gradle-test.zip)
    * Maven: [link](https://github.com/edwardstock/minter-android-sdk-java/raw/master/res/minter-mavan-test.zip)
    
    
## Common problems:

- UnsatisfiedLinkageException - Java can't find native libraries