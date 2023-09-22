# JSBundle Action Overview

## What is a JSBundle Action?

JsBundle Action is a piece of sequential actions that can be executed on the LLM serverless runtime. It is the main way for end users to create their own tools. Rebyte provides a GUI builder for end users to create/edit their own LLM callables. Rebyte provides a list of pre-built actions for common use cases, also private SDK for *software engineer* to build their own actions, and seamlessly integrate with the callable builder.

## Pre-built JSBundle Actions
In here, we provide a list of pre-built JSBundle Actions for common use cases, a typical JSBundle Action is to invoke another callable inside current callable, and do some data transformation before/after the callable is called. For example, you might have a callable **X** for handing user's air ticket booking request, and you want to invoke this callable **X** inside another callable, let's say trip planning callable **Y**. In this scenario, you can use in-house pre-built JSBundle Action **Callable Invoker** to invoke callable **X** inside callable **Y**.

## How to build a JSBundle Action?

please refer to the [JSBundle Action SDK](https://github.com/ReByteAI/rebyte-cli) for more details.
Note: JSBundle Action SDK is currently in early stage, feel free to do a PR if you find any issues.
