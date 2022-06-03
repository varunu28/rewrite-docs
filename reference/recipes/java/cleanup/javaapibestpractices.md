# Java API best practices

** org.openrewrite.java.cleanup.JavaApiBestPractices**
_Use the Java standard library in a way that is most idiomatic._

## Source

[Github](https://github.com/openrewrite/rewrite), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite/rewrite-java/7.24.0/jar)

* groupId: org.openrewrite
* artifactId: rewrite-java
* version: 7.24.0


## Usage

This recipe has no required configuration parameters and comes from a rewrite core library. It can be activated directly without adding any dependencies.

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.22.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.cleanup.JavaApiBestPractices")
}

repositories {
    mavenCentral()
}

```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.25.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.cleanup.JavaApiBestPractices</recipe>
          </activeRecipes>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipesorg.openrewrite.java.cleanup.JavaApiBestPractices`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Use `Map#containsKey`](../../java/cleanup/usemapcontainskey.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.cleanup.JavaApiBestPractices
displayName: Java API best practices
description: Use the Java standard library in a way that is most idiomatic.
recipeList:
  - org.openrewrite.java.cleanup.UseMapContainsKey

```
{% endtab %}
{% endtabs %}