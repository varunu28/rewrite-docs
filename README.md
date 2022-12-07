# Introduction to OpenRewrite

## **Large-Scale Automated Source Code Refactoring**

OpenRewrite enables large-scale distributed source code refactoring for framework migrations, vulnerability patches, and API migrations with an early focus on the Java language.

## Semantic Code Search and Transformation

The OpenRewrite project is a [semantic code search](https://en.wikipedia.org/wiki/Semantic\_search) and transformation ecosystem for Java and other source code. It consists of a platform of prepackaged refactoring recipes for common framework migration and stylistic consistency tasks. It also allows you to define custom recipes to achieve a wide range of source code transformations.

## What Does OpenRewrite Do?

OpenRewrite works by making changes to [Abstract Syntax Trees](/concepts-and-explanations/abstract-syntax-trees.md) (AST) representing your source code and printing the modified trees back into source code. You can then review the changes in your code and commit. Modifications to the AST are performed in [Visitors](/concepts-and-explanations/visitors.md) and visitors are aggregated into [Recipes](/concepts-and-explanations/recipes.md). OpenRewrite recipes make minimally invasive changes to your source code that honor the original formatting.

For example, if you want to consistently use static imports across all of your test files, rather than doing this manually, you could use the UseStaticImport visitor provided by OpenRewrite. Applied to the file below, you can see the changes this generates.

```java
// Before OpenRewrite
import org.junit.Assert;
...

Assert.assertTrue(condition);
```

```java
// After OpenRewrite
import static org.junit.Assert.assertTrue;
...

assertTrue(condition);
```

## Next Steps

* If you want to learn how to configure Maven or Gradle to use OpenRewrite and then use the tools to perform code transformations, check out the [Getting Started Guide](getting-started/getting-started.md).
* If you want to learn how to write your own recipe, check out the [Authoring Recipes Section](tutorials/authoring-recipes/).
