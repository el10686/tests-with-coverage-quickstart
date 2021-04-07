This project has been set up to demonstrate a bug related with the jacoco dependency in Quarkus 1.13.0.

We create a simple project by running:
```
mvn io.quarkus:quarkus-maven-plugin:create \
    -DprojectGroupId=org.acme \
    -DprojectArtifactId=tests-with-coverage-quickstart
```
Then we add the jacoco dependency:
```
<dependency>
  <groupId>io.quarkus</groupId>
  <artifactId>quarkus-jacoco</artifactId>
  <scope>test</scope>
</dependency>
```
Running tests with `./mvnw clean verify` we can generate the jacoco report and everything works as expected.

However when we add kubernetes client dependency in the project and rerun the tests they fail with build errors.
To reproduce the bug:
```
git checkout add-kuberbetes-client-dep
./mvnw clean verify
```
