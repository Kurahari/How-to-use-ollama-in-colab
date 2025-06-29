# How-to-use-Ollama-in-colab
An easy way to make Ollama run on colab T4
## Installation & running
1.Set up Colab notebook to support command-line

```bash
!pip install colab-xterm
%load_ext colabxterm
```

2.Installing and serving Ollama

  First we need to open xterm terminal
```bash
%xterm
```
  Then using the following command in terminal to install Ollama
```bash
curl https://ollama.ai/install.sh | sh
```
  Once Ollama is installed, we can start the server using the following command:
```bash
ollama serve
```
  After we started the server, we can start pulling the model that we want.(in this example I use [deepseek-r1:7b](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-7B))
```bash
ollama pull deepseek-r1:7b
```

3.Verifying the Model

in [ ]
```bash
!ollama list
```
4.Run Ollama in Colab

in [ ]
```bash
%pip install -U langchain-ollama
```
Let's test
```bash
import ollama

response = ollama.chat(model='deepseek-r1:7b', messages=[
    {'role': 'user', 'content': 'Can you write a code that output Hello World in Python?'},
])
print(response.message.content)
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
## License

[MIT](https://choosealicense.com/licenses/mit/)
