DecisionNEET: Neural Engine for Execution and Thought 🤖🚀🛰️
Get up and running with general AI for aerospace and robotics.
Welcome to DecisionNEET, the versatile AI library designed for advanced decision-making in robotics and aerospace applications. With DecisionNEET, you can leverage the power of large language models to process flexible inputs, execute complex tasks, and control motor systems efficiently.

Downloads and Installation
macOS
Download

Windows (Preview)
Download

Linux
sh
Copy code
curl -fsSL https://example.com/install.sh | sh
Manual install instructions

Docker
The official DecisionNEET Docker image decisionneet/decisionneet is available on Docker Hub.

Libraries
decisionneet-python
decisionneet-js
Quickstart
To run and interact with DecisionNEET:

sh
Copy code
decisionneet run model_name
Model Library
DecisionNEET supports a range of models available for different applications:

Model	Parameters	Size	Download Command
AstroMind	8B	4.7GB	decisionneet run astromind
RoboBrain	70B	40GB	decisionneet run robobrain:70b
SatelliteSage	3.8B	2.3GB	decisionneet run satellitesage
MarsNavigator	14B	7.9GB	decisionneet run marsnav
TerraCortex	9B	5.5GB	decisionneet run terracortex
Note: Ensure you have sufficient RAM to run larger models (8 GB for 7B models, 16 GB for 13B models, and 32 GB for 33B models).

Customize a Model
Import from GGUF
Create a Modelfile with the following content to import a GGUF model:

plaintext
Copy code
FROM ./local_model.gguf
Then, create and run the model:

sh
Copy code
decisionneet create example -f Modelfile
decisionneet run example
Customize a Prompt
Models from the DecisionNEET library can be customized with specific prompts. For example, to customize the astromind model:

sh
Copy code
decisionneet pull astromind
Create a Modelfile:

plaintext
Copy code
FROM astromind

PARAMETER temperature 1

SYSTEM """
You are a friendly assistant for space missions.
"""
Create and run the customized model:

sh
Copy code
decisionneet create space_assistant -f ./Modelfile
decisionneet run space_assistant
CLI Reference
Create a Model
sh
Copy code
decisionneet create mymodel -f ./Modelfile
Pull a Model
sh
Copy code
decisionneet pull model_name
Remove a Model
sh
Copy code
decisionneet rm model_name
Copy a Model
sh
Copy code
decisionneet cp model_name new_model_name
Multiline Input
For multiline input, use """:

sh
Copy code
>>> """Hello,
... world!
... """
Multimodal Models
For multimodal models:

sh
Copy code
>>> What's in this image? /path/to/image.png
Pass the Prompt as an Argument
sh
Copy code
decisionneet run model_name "Summarize this file: $(cat README.md)"
REST API
DecisionNEET provides a REST API for running and managing models.

Generate a Response
sh
Copy code
curl http://localhost:11434/api/generate -d '{
  "model": "astromind",
  "prompt":"Why is the sky blue?"
}'
Chat with a Model
sh
Copy code
curl http://localhost:11434/api/chat -d '{
  "model": "astromind",
  "messages": [
    { "role": "user", "content": "why is the sky blue?" }
  ]
}'
See the API documentation for all endpoints.

Documentation
Introduction: Overview of the framework and the structure of the docs.
Tutorials: Hands-on guides to build specific applications.
How-to Guides: Answers to specific tasks and goals.
Conceptual Guide: In-depth explanations of key parts of the framework.
API Reference: Detailed documentation of every class and method.
Contributing
We welcome contributions to DecisionNEET! Whether it's a new feature, bug fix, or documentation improvement, your input is valuable. For detailed information on how to contribute, see our contribution guide.

Community and Support
Join our Discord to connect with other users, share ideas, and get support.

License
DecisionNEET is dual-licensed under the AGPL-3.0 and a commercial license. For commercial use or projects generating significant revenue, please contact Your Contact Information.



Happy coding with DecisionNEET! 🤖🚀🛰️
