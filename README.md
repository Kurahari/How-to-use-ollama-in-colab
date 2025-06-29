# How-to-use-Ollama-in-colab
An easy way to make Ollama run on colab
## Installation
1.Set up Colab notebook to support command-line

```bash
!pip install colab-xterm
%load_ext colabxterm
```

2.Installing and serving Ollama

  First We need to open xterm terminal
```bash
%xterm
```
  Then run this to command in terminal to install Ollama
```bash
curl https://ollama.ai/install.sh | sh
```
## License

[MIT](https://choosealicense.com/licenses/mit/)
