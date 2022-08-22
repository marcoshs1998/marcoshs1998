## Enable Keytool in Terminal
First, you must have install `Java JDK` on your machine with `JAVA_HOME` environment.

Add in environment variables this path:
```
%JAVA_HOME%\bin
```

Type in your prompt:
```
keytool
```

## Generate a ServerCertification

To generate you must set 
- alias     | alias for save in keystore
- keyalg    | algorithm
- keypass   | key for alias
- storepass | key for access keystore
- keystore  | keystore's filename 

Command:
```
keytool -genkey -alias {YOUR ALIAS NAME} -keyalg RSA -keypass {YOUR PASS} -storepass {YOUR OTHER PASS} -keystore {NAME FOR YOUR KEYSTORE}.jks`
```

When you press Enter, keytool prompts you to enter the server name, organizational unit, organization, locality, state, and country code.

## Export Certify from Keystore

To export you must set
- alias     | alias from keystore
- storepass | keystore secret
- file      | name of export file
- keystore  | path to keystore.jks

Command:
```
keytool -export -alias {YOUR ALIAS NAME} -storepass {YOUR OTHER PASS} -file {FILENAME}.cer -keystore {PATH TO KEYSTORE}.jks
```