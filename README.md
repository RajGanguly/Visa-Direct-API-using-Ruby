# Visa-Direct-API-using-Ruby
A sample API created using visa developer which debits a particular amount from the sender's account


#####################################################################################################
Here are the prerequisite to make the API running and the steps as i've understood.
1) Login to https://developer.visa.com/

    Click on Dashboard to see an existing app that should be pre-created(let's say the name of the app be VisaPay) and then click on it.

2)  You will be able to see UserId and Password in base64 encoded format which needs to be used as request body
for every request string (See attached .rb)

3) Find private key(which is only available upon creation of the project) to the sandbox server and a client-server certificate file also included in the project directory.

4) Store this two files in a secured location in a new directory.

5) Run this two commands inside the directory of step (4)
openssl pkcs12 -export -in cert.pem -inkey "key_Visa-Pay.pem" -certfile cert.pem -out visaPay_keyAndCertBundle.p12
openssl pkcs12 -info -in visaPay_keyAndCertChainBundle.p12

These 2 commands will create a keystore named visaPay_keyAndCertChainBundle.p12 using the private key and the certificate.
This step is very important


6) Replace line no 58 and 59 with the path of directory as created in step 4.

7) Use your current gemset and install the following gems and compile the attached .rb file.
    rest-client, pem.       
(Install open-ssl for ruby <= 1.9)

8) Check the test data from the visa account to see different responses.

