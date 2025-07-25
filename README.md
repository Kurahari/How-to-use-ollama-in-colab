# How-to-use-Ollama-in-colab
An easy way to make Ollama run on colab T4 (My native language is not English so Sorry about every wrong spelling.)
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
    {
    'role': 'user',
    'content': 'Can you write a code that output Hello World in Python?'
    }
])
print(response.message.content)
```
## Contributing
- Please open an issue first to discuss what you would like to change.

- Please make sure to update tests as appropriate.

## Key Points to Consider
- It will not be as fast as running locally due to network latency and resource limitations of the T4.
- Be careful of your usage limits.
- Some features of Ollama may not work in the Colab due to its virtual machine nature.

## Best Practices
1. Use small models
2. If you need longer outputs, consider generating text in chunks rather than all at once.
3. Remember to save your notebook frequently, as Colab sessions can sometimes terminate unexpectedly.
4. After your session ends, you might want to remove Ollama to free up space:
```bash
!rm -rf /usr/local/bin/ollama
```
## License

[MIT](https://choosealicense.com/licenses/mit/)
