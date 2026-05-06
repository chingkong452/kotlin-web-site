[//]: # (title: Create a task manager app with Spring Boot using Claude Code)

In this tutorial, you'll learn how to use [Claude Code](https://code.claude.com/docs/en/overview) to create a Kotlin app to manage tasks. The tutorial uses Spring Boot
to manage the backend infrastructure and Claude Code handles the rest. 

> As with any AI-powered tool, Claude Code can make mistakes. Review Claude's changes and only use it with code you trust.
> For more information on Claude's security policy, see [Claude Code Docs](https://code.claude.com/docs/en/security).
> 
{style="note"}

## Set up the environment

1. Download and install the latest version of [IntelliJ IDEA](https://www.jetbrains.com/idea/download/).
2. Install the [JetBrains AI Assistant](https://plugins.jetbrains.com/plugin/22282-jetbrains-ai-assistant).
3. Activate the Claude Agent in one of the following ways:
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

4. Make sure that you have specified all the fields and click **Next**.
5. Select the latest stable Spring Boot version in the **Spring Boot** field.

6. Select the following dependency: **Web | Spring Web**.

   ![Set up Spring Boot project](spring-claude-dependency.png){width=800}

7. Click **Create** to generate and set up the project.

   The IDE generates and opens a new project. It may take some time to download and import the project dependencies.

## Make a plan

In your project:

1. Open the ![AI Chat](ai-chat.png){width=25}{type="joined"}**AI Chat** tool window and select **Claude Agent**.
2. Click ![Operation mode](operation-mode.png){width=25}{type="joined"} and select **Mode: Plan Mode**.
   The Claude Agent is ready to plan without executing actions.

   > For more information about the different operation modes, see [Select operation mode](https://www.jetbrains.com/help/ai-assistant/claude-agent.html#select-operation-mode).
   >
   {style="tip"}

3. Create a prompt asking Claude to create a task manager app. Share some details on what you think it should include. For example:

   ```text
   I'd like to create a task manager application for managing tasks, such as a grocery list. 
   It should have a basic UI and include categories, due dates, priorities and status tracking. 

   Use VCS while working. Work step by step and make commits at each stage so I can review the changes afterward.
   ```

   > For more information on how to design your prompt, see [Claude Code best practices](https://code.claude.com/docs/en/best-practices).
   >
   {style="tip"}

   Claude Code explores the existing project structure and suggests a plan.

4. Review the plan carefully. If you want to make some modifications, select **No, keep planning** and share your follow-up comments.
5. When you're ready to proceed, select the **Yes ...** option that you are most comfortable with.

   ![Ready to code](ready-to-code.png){width=600}

   > For more information on the different options, see [Claude Code permission modes](https://code.claude.com/docs/en/best-practices).
   >
   {style="tip"}

6. Claude Code exits Plan Mode and starts work. Wait until it is complete.

## Review the commits

Before proceeding, review the changes in git commits carefully:

1. Open the **Git** tool window to see the list of commits. 
2. Select a commit and double-click on each modified file to review the diff in IntelliJ IDEA's side-by-side viewer.

![Side by side viewer](side-by-side-viewer.png){width=600}

## Run the app

Once you are happy with the changes, run the app:

1. Run the `bootRun` Gradle task or enter the following command in terminal:

   ```bash
   ./gradlew bootRun
   ```

2. In a browser, navigate to the local host URL. Typically, it's:

   ```text
   http://localhost:8080
   ```

   You see the basic UI that Claude created.

   ![Run the app](run-spring-claude-app.png){width=800}

## Test the app

Now it's time to test it.

### Test UI manually

Start with testing the UI functionality. Complete some simple actions:

1. Create a task and test the form fields.
2. Edit a task to check that changes persist.
3. Change the status of a task.
4. Delete a task.
5. Change the category of a task.

If any of these don't work, send a new prompt to Claude asking to investigate and fix the problem.

### Run unit tests

Claude automatically creates some tests. Check that all the tests pass by running:

   ```bash
   ./gradlew test
   ```

Alternatively, in the `src/test` directory, open a test and click the run icon in the gutter. A successful test shows 
a checkmark in the gutter.

If any test doesn't work, send a new prompt to Claude asking to investigate and fix the problem.

## Make refinements

Now the initial task is complete, you can make refinements. For example, let's improve the UI so that a user can edit
the tasks directly in the list.

You can send a prompt like:

```text
As a next step, allow tasks to be edited inline. For example, let users click on a task title to edit it directly in the list,
and update fields like priority, due date, or status without leaving the current view. 
This should make the app feel faster and more intuitive to use.
```

Just as before, Claude Code explores the existing project structure and repository and suggests a plan.
Once you've accepted the plan, Claude has completed its work, and you've reviewed the changes, run the app again.

<img src="make-refinements-claude.gif" alt="Refine your Spring Boot app with Claude" width="600"/>

Congratulations! You’ve created and refined your task manager app with the help of Claude Code.

## What's next?

* Learn about Kotlin AI skills
* Check out our tutorial about how to use Junie with Kotlin AI skills
