
## Go do it exercises 

The MyHero Demo application leverages service discovery with Consul for the APP to find and access the DATA tier.  Take a look at the configuraiton in Marathon after deploying to see how it is passed in.  _Hint: look at the environment variables_.  Then take a look at the actual code for [myhero_app](https://github.com/hpreston/myhero_app) and see if you can find the parts of the code where the DNS lookup is happening.  

