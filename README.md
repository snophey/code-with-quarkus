# code-with-quarkus

This repo provides a minimal example that reproduces an issue with overlaying lists from a YAML configuration with environment variables.
To reproduce the bug perform the following steps:

0. (Make sure you're on the `main` branch. This branch uses Quarkus 3.15.3)
1. Set set the environment variable `APP_WORDS` to some custom value (e.g. `export APP_WORDS=if,you,see,this,then,everything,is,fine`).
2. Run the Quarkus application: `./mvnw clean compile quarkus:dev`
3. Run `curl localhost:8080/words` and observe the output. Your custom words should be printed.
4. Switch to the `quarkus-3.18.1` branch: `git checkout quarkus-3.18.1`
5. Run the Quarkus application (repeat step 2.)
6. Run the curl command from step 3. Observe that the words from `application.yaml` are not overwritten by your environment variable.
