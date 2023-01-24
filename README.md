# Vinted fork for Apache Kyuubi

We only use [Spark-Ranger plugin](https://kyuubi.readthedocs.io/en/master/security/authorization/spark/index.html) from this project.


WTD:
- from project root dir run `build/mvn clean package -pl :kyuubi-spark-authz_{scala_version} -DskipTests -Dspark.version={spark_version} -Dranger.version={ranger_version}`
- you'll find spark plugin jar under `extensions/spark/kyuubi-spark-authz/target`
- upload the jar to cloudsmith raw-hosted-oom repo
- upload transitive dependencies as well if their versions have changed from those already in cloudsmith. They will be under `/extensions/spark/kyuubi-spark-authz/target/scala-{scala_version}/jars`
- do not upload `ranger-plugins-*` jars, these we build from Apache Ranger fork

for more info see https://kyuubi.readthedocs.io/en/master/security/authorization/spark/build.html
