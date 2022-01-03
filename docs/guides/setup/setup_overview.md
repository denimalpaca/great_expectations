---
title: "Setup: Overview"
---
# [![Setup Icon](../../images/universal_map/Gear-active.png)](setup_overview.md) Setup: Overview 

import UniversalMap from '/docs/images/universal_map/_universal_map.mdx';

<!--Use 'inactive' or 'active' to indicate which Universal Map steps this term has a use case within.-->

<UniversalMap setup='active' connect='inactive' create='inactive' validate='inactive'/>

<!-- Only keep one of the 'To best understand this document' lines.  For processes like the Universal Map steps, use the first one.  For processes like the Architecture Reviews, use the second one. -->

:::note Prerequisites
- Completing [Step 1: Setup](/docs/tutorials/getting_started/initialize_a_data_context) of the Getting Started tutorial is recommended.
:::
	
Getting started with Great Expectations is quick and easy.  Once you have completed setup for your production deployment, you will have access to all of the features of Great Expectations from a single entry point: Your Data Context.  You will also have your Stores and Data Docs configured in the manner most suitable for your project's purposes.

## The Setup process

<!-- Brief outline of what the process entails.  -->

Setup entails ensuring your system is prepared to run Great Expectations, installing Great Expectations itself, and initializing your deployment. Optionally, you can also tweak the configuration of some components, such as Stores and Data Docs. We'll look at each of these things in sequence.

Note: configuration of Datasources, Expectation Suites, and Checkpoints will be handled separately. We consider those to be configuration of components after your main Great Expectations deployment is set up.

<!-- The following subsections should be repeated as necessary.  They should give a high level map of the things that need to be done or optionally can be done in this process, preferably in the order that they should be addressed (assuming there is one). If the process crosses multiple steps of the Universal Map, use the <SetupHeader> <ConnectHeader> <CreateHeader> and <ValidateHeader> tags to indicate which Universal Map step the subsections fall under. -->

### 1. System Dependencies

The first thing to take care of is making sure your work environment has the utilities you need to install and run Great Expectations.  These include a working Python install (version 3.8 or greater), the ability to pip install Python packages, an internet connection, and a browser so that you can use Jupyter notebooks.  Best practices are to use a virtual environment for your project's workspace.

If you are having trouble with any of these, our documentation on [Supporting Resources](/docs/reference/supporting_resources) will direct you to more information and helpful tutorials.

## 2. Installation

Installing Great Expectations is a simple pip command.  From the terminal, execute:

```markup title="Terminal command:"
pip install great_expectations
```

Running this command in an environment configured to accept Python pip install commands will handle the entire installation process for Great Expectations and its dependencies.  

See our [guides for the installation process](/docs/guides/setup/installation/index) for more information.

## 3. Initialize a Data Context

Your Data Context contains the entirety of your Great Expectations project and provides the entry point for all of the primary methods you will use to configure and interact with Great Expectations.  That's why the first thing you'll do once you've installed Great Expectations will be to initialize your Data Context.  This is another one-line command.  Simply go to the root folder for your project and execute:

```markdown title="Terminal command:"
great_expectations init
```

Running this command will initialize your Data Context in the directory that the command is run from.  It will create the folder structure a Data Context requires to organize your project.

See our [guides for configuring your Data Context](/docs/guides/setup/configuring_data_contexts/index) for more information.

## 4. Optional Configurations

Once your Data Context is initialized, you'll be all set to start using Great Expectations.  However, there are a few things that are configured by default to operate locally which you may want to configure to be hosted elsewhere.  We include these optional configurations in our Setup instructions.  Using the Data Context, you can easily create and test your configurations.

### Stores

Stores are the locations where your Data Context stores information about your Expectations, your Validation Results, and your Metrics.  By default, these are stored locally.  But you can reconfigure them to work with a variety of backends.  

See our [guides for configuring Stores](/docs/guides/setup/configuring_metadata_stores/index) for more information.

### Data Docs

Data Docs provide human readable renderings of your Expectation Suites and Validation Results.  As with Stores, these are built locally by default.  However, you can configure them to be hosted and shared in a variety of different ways.  

See our [guides on configuring Data Docs](/docs/guides/setup/configuring_data_docs/index) for more information.

## Wrapping up

<!-- This section is essentially a victory lap.  It should reiterate what they have accomplished/are now capable of doing.  If there is a next process (such as the universal map steps) this should state that the reader is now ready to move on to it. -->

That's all there is to the Setup step.  Once you have your Data Context initialized you will almost always start from your Data Context (as illustrated below) for everything else you do through Great Expectations.

```markdown title="Python code:"
import great_expectations as ge
context = ge.get_context()
```

From here you will move on to the next step of working with Great Expectations: Connecting to Data.