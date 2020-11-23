# Bamboo Specs


* [Tutorial](https://confluence.atlassian.com/bamboo/tutorial-create-a-simple-plan-with-bamboo-java-specs-894743911.html)

```
mvn archetype:generate -B \
    -DarchetypeGroupId=com.atlassian.bamboo -DarchetypeArtifactId=bamboo-specs-archetype \
	-DarchetypeVersion=7.1.4 \
    -DgroupId=com.atlassian.bamboo -DartifactId=bamboo-specs -Dversion=0.1.0-SNAPSHOT \
    -Dpackage=cybersyn -Dtemplate=minimal
```