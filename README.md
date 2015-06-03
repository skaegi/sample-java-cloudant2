Press this button, to get your own copy of a Java sample demonstrating Cloudant running in Bluemix !

[![Deploy To Bluemix](https://bluemix.net/deploy/button.png)](http://bluemix.net/deploy)

This sample illustrates the new way of configuring a pipeline using a config file, located at ".bluemix/pipeline.yml" from the root of the repository.

The config file is creating 2 stages:
1. Ant builder stage (using build.xml at the root by default)
2. Deploy stage (using a custom script defined in the config file)

Note that the config file is using environment variables to abstract away target locations so it will work nicely with the Deploy to Bluemix button, setting these variables based on user selection:

1. ${CF_APP} - the selected app name to deploy
2. ${CF_TARGET_URL} - a Bluemix region (CF API URL)
3. ${CF_ORGANIZATION_ID} - an organization to deploy to in the selected region
4. ${CF_SPACE_ID} - a space in the selected organization

Also note that the config files is customizing the deploy script to also create a backend service (Cloudant) right before the CF PUSH action.
In earlier version of the Deploy To Bluemix button, service creation had to be driven via a manifest.yml unofficial extension ("declared-services"). This is no longer necessary using this new support for pipeline configuration.
