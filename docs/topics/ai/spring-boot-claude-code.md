[//]: # (title: Create a task manager app with Spring Boot and Claude)

In this tutorial, you'll learn how to use [Claude](https://claude.com/product/overview) to create a Kotlin app to manage tasks. The tutorial uses Spring Boot
to manage the backend infrastructure, while Claude handles the rest. 

> As with any AI-powered tool, Claude can make mistakes. Review Claude's changes and only use it with code you trust.
> For more information on Claude's security policy, see [Claude Code Docs](https://code.claude.com/docs/en/security).
> 
{style="note"}

## Set up the environment

> This tutorial uses Claude through the JetBrains AI assistant, but you can also work through the tutorial steps using
> Claude Code in the terminal.
>
{style="tip"}

1. Download and install the latest version of [IntelliJ IDEA](https://www.jetbrains.com/idea/download/).
2. Install the [JetBrains AI Assistant](https://plugins.jetbrains.com/plugin/22282-jetbrains-ai-assistant).
3. Activate Claude Agent in one of the following ways:
   * [Using a JetBrains AI subscription](https://www.jetbrains.com/help/ai-assistant/activate-agents.html#activate-claude-agent-with-jbai-subscription)
   * [Using an API key](https://www.jetbrains.com/help/ai-assistant/activate-agents.html#activate-claude-agent-with-api-key)
   * [Using Anthropic Console](https://www.jetbrains.com/help/ai-assistant/activate-agents.html#activate-agent-with-provider-specific-method)

## Create a project

> You can also create a Spring Boot project using [Spring's web-based project generator](https://start.spring.io/#!language=kotlin&type=gradle-project-kotlin).
>
{style="tip"}

Create a new Spring Boot project in IntelliJ IDEA:

1. In IntelliJ IDEA, select **File** | **New** | **Project**.
2. In the panel on the left, select **New Project** | **Spring Boot**.
3. Specify the following fields and options in the **New Project** window:

   * **Name**: task-manager-demo
   * **Language**: Kotlin
   * **Type**: Gradle - Kotlin

     > This option specifies the build system and the DSL.
     >
     {style="tip"}

   * **Package name**: org.jetbrains.kotlin.taskmanagerdemo
   * **JDK**: jbr-21

     > If you don't have a JDK installed, you can download it from the dropdown list.
     >
     {style="note"}

   * **Java**: 17

     > If you don't have Java 17 installed, you can download it from the JDK dropdown list.
     >
     {style="tip"}

   ![Create Spring Boot project](create-spring-claude-project.png){width=800}

4. Make sure that you specified all the fields, then click **Next**.
5. Select the latest stable Spring Boot version in the **Spring Boot** field.
6. Select the **Web | Spring Web** dependency.

   ![Set up Spring Boot project](spring-claude-dependency.png){width=800}

7. Click **Create** to generate and set up the project.

   The IDE generates and opens the new project. It may take some time to download and import the project dependencies.

## Create a development plan

In your project:

1. Open the ![AI Chat](ai-chat.png){width=25}{type="joined"}**AI Chat** tool window and in the bottom-left select **Claude Agent**.
2. Click ![Operation mode](operation-mode.png){width=25}{type="joined"} and select **Mode: Plan Mode**.
   Claude Agent is now ready to plan without executing actions.

   > For more information about the different operation modes, see [Select operation mode](https://www.jetbrains.com/help/ai-assistant/claude-agent.html#select-operation-mode).
   >
   {style="tip"}

3. Write a prompt asking Claude to create a task manager app. Share some details on what you think it should include. For example:

   ```text
   I'd like to create a task manager application for managing tasks, such as a grocery list. 
   It should have a basic UI and include categories, due dates, priorities, and status tracking. 

   Use VCS while working. Work step by step and create commits at each stage so I can review the changes afterward.
   ```

   > For guidance on how to design your prompt, see [Claude Code best practices](https://code.claude.com/docs/en/best-practices).
   >
   {style="tip"}

   Claude explores the existing project structure and suggests a plan.

4. Review the plan carefully before proceeding. If you want to make some modifications, select **No, keep planning** and share your follow-up comments.
5. When you're ready to proceed, select the **Yes ...** option that you are most comfortable with.

   ![Ready to code](ready-to-code.png){width=600}

   > For more information on the different options, see [Claude Code permission modes](https://code.claude.com/docs/en/best-practices).
   >
   {style="tip"}

6. Claude exits Plan Mode and begins working. Wait until it's complete.

## Review the commits

Before running the app, review the generated changes carefully:

1. Open the **Git** window to see the list of commits. 
2. Select a commit and double-click each modified file to review the diff in IntelliJ IDEA's side-by-side viewer.

![Side by side viewer](side-by-side-viewer.png){width=600}

## Run the app

Once you are happy with the changes, run the app:

1. Run the `bootRun` Gradle task or enter the following command in the terminal:

   ```bash
   ./gradlew bootRun
   ```

2. In a browser, open the localhost URL. Typically, it's:

   ```text
   http://localhost:8080
   ```

   You should now see the basic UI that Claude created.

   ![Run the app](run-spring-claude-app.png){width=800}

## Test the app

Now it's time for you to test the app.

### Test UI manually

Start by testing the UI functionality. Complete some simple actions:

1. Create a task and test the form fields.
2. Edit a task to check that changes persist.
3. Change the status of a task.
4. Delete a task.
5. Change the category of a task.

If any of these actions don't work, send a new prompt to Claude asking it to investigate and fix the problem.

### Run unit tests

Claude also creates some tests automatically. Check that all the tests pass by running:

   ```bash
   ./gradlew test
   ```

Alternatively, in the `src/test` directory, open a test and click the run icon in the gutter. A successful test shows 
a checkmark in the gutter.

If any test doesn't work, send a new prompt to Claude asking it to investigate and fix the problem.

## Make refinements

Now that the initial task is complete, you can make refinements. For example, let's improve the UI so users can edit
tasks directly in the list.

You can send a prompt like:

```text
As a next step, allow users to edit tasks inline. For example, let users click on a task title to edit it directly in the list,
and update fields like priority, due date, or status without leaving the current view. 
This change should make the app feel faster and more intuitive to use.
```

Just as before, Claude explores the existing project structure and suggests a plan.
After you accept the plan, wait for Claude to finish, review the changes, and then run the app again.

<img src="make-refinements-claude.gif" alt="Refine your Spring Boot app with Claude" width="600"/>

Congratulations! You used Claude to plan, build, test, and refine a Kotlin Spring Boot application directly in IntelliJ IDEA.

## What's next?

* Learn about Kotlin AI skills
* Check out our tutorial on using Junie with Kotlin AI skills
