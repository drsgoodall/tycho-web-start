Tycho Web Start Example

This is an example java web start project using Tycho. This is based on the Eclipse RCP product.



Note: The eclipse plug-ins are already signed by Eclipse and use an SHA1 digest. This is the default for Java 6. For java 7 SHA256 is the default. Using java 7 can cause extra signatures to be added and cause the existing SHA1 signature verification to fail.

If and sign your jars using java 6 key signer (and possibly use java 6 keytool to create your signing key) then the existing SHA1 values will be reused.


Creating the key

keytool -keystore keystore.jks -genkey -alias mysigner

Building

mvn clean package -Djarsigner.alias=mysigner -Djarsigner.storepass=changeit -Djarsigner.keystore=keystore.jks
