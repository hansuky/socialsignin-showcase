SocialSignIn Showcase
=====================

This is a showcase of a SocialSignIn webapp, as generated by the <a href="https://github.com/socialsignin/mvn-archetype-socialsignin-webapp">SocialSignin Webapp Maven Archetype</a>

This webapp delegates login for the application to 3rd party providers using spring-social-security
, removing the need for local username/passwords.   

Supported providers are *facebook*,*twitter*,*lastfm*,*mixcloud*,*soundcloud*,*linkedin* and *tumblr* (thanks to Sam Douglass 
for providing spring-social-tumblr module and helping us to showcase it here )

A demo controller is included to demonstrate how simple it is to access the API of the 3rd party provider
once the user is logged in using the SocialSignin provider modules.

This webapp uses:

1) <a href="https://github.com/SpringSocial/spring-social">Spring Social</a> provider modules  (Allows connection to 3 party provider APIs)

2) <a href="https://github.com/socialsignin/spring-social-security">spring-social-security<a/> ( Removes need for local user account management, delegating to 3rd party for login details - no
local usernames or passwords are needed. )

3) <a href="https://github.com/socialsignin/socialsignin-provider">socialsignin-provider</a> modules   ( Easy configuration of spring social providers using component scanning )

This app comes with an in-memory datasource configured for development purposes - this can be easily switched for a 
production datasource.

Properties which must be specified for this webapp (in src/main/resources/environment.properties) are
the clientIds and secrets for each provider.

Once you have cloned this project, you'll need to obtain client API accounts for your chosen
providers and ensure that the client ids and secrets are set in the environment.properties file.  

You will also need to configure the return urls set on each provider account to be http://localhost:8080/ 
(depending on the provider).  The exception to this is for Tumblr where the return url will need to be set to 
http://localhost:8080/signinOrConnect/tumblr

You can then start your project webapp using jetty:

mvn jetty:run

Go to http://localhost:8080/ to run the application


To generate your own sample application with your own chosen list of providers and for easy property configuration,
you can use our mvn archetype: https://github.com/socialsignin/mvn-archetype-socialsignin-webapp

