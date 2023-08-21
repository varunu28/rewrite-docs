# Use correct web-app namespace values

**org.openrewrite.xml.liberty.WebDDNamespaceRule**

_Namespace values in web.xml must be consistent with the descriptor version._

## Source

[GitHub](https://github.com/openrewrite/rewrite-liberty/blob/main/src/main/resources/META-INF/rewrite/was-to-liberty.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-liberty/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-liberty/1.0.0-rc.1/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-liberty
* version: 1.0.0-rc.1


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-liberty:1.0.0-rc.1` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.1.25")
}

rewrite {
    activeRecipe("org.openrewrite.xml.liberty.WebDDNamespaceRule")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-liberty:1.0.0-rc.1")
}
```
{% endcode %}
{% endtab %}
{% tab title="Maven POM" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.4.1</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.xml.liberty.WebDDNamespaceRule</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-liberty</artifactId>
            <version>1.0.0-rc.1</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}

{% tab title="Maven Command Line" %}
{% code title="shell" %}
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-liberty:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.xml.liberty.WebDDNamespaceRule
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change XML Attribute of a specific resource version](../../xml/changenamespacevalue.md)
  * elementName: `web-app`
  * newValue: `http://java.sun.com/xml/ns/j2ee`
  * versionMatcher: `2.4`
  * searchAllNamespaces: `false`
* [Change XML Attribute of a specific resource version](../../xml/changenamespacevalue.md)
  * elementName: `web-app`
  * newValue: `http://java.sun.com/xml/ns/java`
  * versionMatcher: `2.5,3.0`
  * searchAllNamespaces: `false`
* [Change XML Attribute of a specific resource version](../../xml/changenamespacevalue.md)
  * elementName: `web-app`
  * newValue: `http://xmlns.jcp.org/xml/ns/javaee`
  * versionMatcher: `3.1+`
  * searchAllNamespaces: `false`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.xml.liberty.WebDDNamespaceRule
displayName: Use correct web-app namespace values
description: Namespace values in web.xml must be consistent with the descriptor version.
recipeList:
  - org.openrewrite.xml.ChangeNamespaceValue:
      elementName: web-app
      newValue: http://java.sun.com/xml/ns/j2ee
      versionMatcher: 2.4
      searchAllNamespaces: false
  - org.openrewrite.xml.ChangeNamespaceValue:
      elementName: web-app
      newValue: http://java.sun.com/xml/ns/java
      versionMatcher: 2.5,3.0
      searchAllNamespaces: false
  - org.openrewrite.xml.ChangeNamespaceValue:
      elementName: web-app
      newValue: http://xmlns.jcp.org/xml/ns/javaee
      versionMatcher: 3.1+
      searchAllNamespaces: false

```
{% endtab %}
{% endtabs %}

## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.xml.liberty.WebDDNamespaceRule)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.