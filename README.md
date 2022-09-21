## Getting Started

Without keystore, both the server and client will fail. This video show how to generate keystore using keytool program. Then run server and client with keystore and password.


Type the following command in your command window to create a keystore named examplestore and to generate keys:

$ keytool -genkey -alias signFiles -keystore examplestore
$ keytool -genkey -alias example -keyalg RSA -sigalg SHA256withRSA -keysize 2048 -validity 3650 -keystore keystore.jks

Examples not sure if it is required.
keytool -certreq -alias <alias> -keystore <keystore>.jks -file <file>.csr -sigalg SHA1WithRSA

You will be prompted to enter passwords for the key and keystore. The password in this example is "password".

(reference: https://docs.oracle.com/javase/tutorial/security/toolsign/step3.html)

Run SSL server and client by entering the commands:
$ java -Djavax.net.ssl.keyStore=keystore -Djavax.net.ssl.keyStorePassword=password "...JavaSSLServer.java"
$ java -Djavax.net.ssl.trustStore=keystore -Djavax.net.ssl.trustStorePassword=password "...JavaSSLClient.java"
