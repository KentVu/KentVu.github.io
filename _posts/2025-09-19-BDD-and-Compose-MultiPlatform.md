---
layout: post
author: kent
title: BDD and Compose MultiPlatform
---

I've been obsessed with BDD recently, and eagerly trying BDD in my pet project that's using CMP (#Kotlin).
But the result seems pessimistic.

First thing is to think of how to apply BDD into my current CMP project.
Til now the only way I can get CMP UI Tests to work (runnning `runComposeUiTest()`) is to run it directly from a JUnit's @Test function, that is:
```kotlin
@Test fun ...() = runComposeUiTest() {
  // Here we can call Jetpack locator, assertor etc..
}
``` 
Otherwise, for example: running from another JUnit runner like `@RunWith(Cucumber::class)`, or kotest's `BehaviorSpec`.., could result in the test run hangs forever, one time is when entering `setContent {...}`, the other time is when asserting `assertIsDisplayed()`.. 

Obviously, when using `createComposeRule()`, if not using Compose's default Runner (test class that's not annotated with `@RunWith`), the rule doesn't get initialized (somehow), and you'll get `lateinit property is not initialized` kinda error..

## Which way to try?

The goal of BDD is to get business people involved to the development process. To do that, we must somehow present them with a kind of readable executable documentation (Example/Scenario in BDD terms). As stated earlier, CMP UI Testing requires to be executed on it own, so any tool that requires it own Test Runner is out of question.. :(
So what comes to my mind when thinking how to apply BDD into a CMP project:
- Using **kotest**'s BehaviorSpec, and try to express as naturally as possible the scenario (so I can show it to my (imaginary) stakeholder),
  ❌ Kotest requires it own test runner!!
- **Cucumber**: the same!!
- **JBehave**: Seem promissing with its promise of not interfering with testing framework, with its `Embedder`, but integrating seems involving a lot of work because of its old age, Java centric, POM only support and not widely adopted, I'll be on my own figuring how to write `build.gradle.kts`, converting pom declaration, and good luck looking for support on the internet...

<!--
To support running CMP UI Tests, 

Doing a simple Google search come immediately Cucumber.

The problem with CMP Ui testing is 

The dominant tool in this field that's closest to Kotlin is Cucumber 
-->
