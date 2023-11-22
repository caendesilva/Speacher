# Speacher - Easy CLI OpenAI Text-to-Speech

## Overview

Speacher is a command-line interface (CLI) application written in PHP that enables you to leverage the 
[OpenAI Text-to-Speech API](https://platform.openai.com/docs/guides/text-to-speech) to convert text
into stunningly realistic speech right from the command line, without effort. Listen below!

https://github.com/caendesilva/Speacher/assets/95144705/7578939a-1e53-41a8-9a5c-4d4ec19e52d0

### Features

- Simple and intuitive command-line interface.
- Utilizes the OpenAI Text-to-Speech API for high-quality speech synthesis.
- Easily converts text input into speech output, either from arguments or input files.

### Requirements

- PHP 8.1 or higher must be installed on your system.
- OpenAI API key (sign up at [OpenAI](https://platform.openai.com/signup) to obtain your key)
- Notice: The API costs money to use, thus you must set up billing in your OpenAI account to use this application. 
  See the OpenAI [pricing page](https://openai.com/pricing#audio-models) for more information.

## Installation

First, download the `speacher` file and make it executable:

```bash
curl https://github.com/caendesilva/speacher/releases/latest/download/speacher -o speacher
chmod +x speacher
sudo mv speacher /usr/local/bin/speacher
```

Next, configure your OpenAI API key:

```bash
speacher --set-key <YOUR_API_KEY>
```

_The installation step can also be used to update the application to the latest version._

## Usage

Run the `speacher` command followed by the text you want to convert to speech:

```bash
speacher "Hello, this is Speacher. How can I help you today?"
```

This will create a file named 'speacher-xxx.mp3' in the current directory. You can also specify the output file name:
    
```bash
speacher "Hello, this is Speacher. How can I help you today?" --output=speech.mp3
```

You can also specify the input text from a file:

```bash
speacher --input=script.txt
```

### Options

These are the available options for the `speacher` command:

| Option        | Description                              |
|---------------|------------------------------------------|
| -h, --help    | Display the help message                 |
| -v, --version | Display this application version         |
| -i, --input   | Specify the input file path              |
| -o, --output  | Specify the output file path             |
| --voice       | Specify the voice to use                 |
| --model       | Specify the model to use                 |
| --key         | Specify the OpenAI API key for this call |
| --set-key     | Set the OpenAI API key in the config     |
| --edit-config | Edit the global configuration file       |

### Configuration

You can also edit the global configuration file to set the default options for the `speacher` command. Open the file using the `--edit-config` option:

```bash
speacher --edit-config
```

The default options are:

```json
{
    "key": "null",
    "voice": "alloy",
    "model": "tts-1",
    "format": "mp3"
}
```

## Information

### License & Terms

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.

Remember that the [OpenAI Usage Policy](https://openai.com/policies/usage-policies) requires disclosing that the audio is AI-generated and not a human voice.

### Acknowledgments

- Powered by the OpenAI Text-to-Speech API. Visit [OpenAI](https://www.openai.com/) for more information.
- Console application built with [MinimaPHP](https://git.desilva.se/MinimaPHP/).

---

Feel free to contribute, report issues, or make suggestions! This project is not affiliated with OpenAI.

