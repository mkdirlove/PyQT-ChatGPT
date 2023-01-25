<h1 align="center">
  <br>
  <a href="https://github.com/mkdirlove/PyQT-ChatGPT"><img src="https://github.com/mkdirlove/PyQT-ChatGPT/blob/main/logo.png" alt="PyQT-ChatGPT"></a>
  <br>
  A graphical user interface for ChatGPT using PyQT5 in Python.
  <br>
</h1>

### Installation ang usage

```
python3 -m pip install PyQt5 openai
```
```
git clone https://github.com/mkdirlove/PyQT-ChatGPT.git
```
```
cd PyQT-ChatGPT
```
```
python3 pyqt-chatgpt.py
```

### Then edit file to match your config

Open the file in any text / code editor and go to line 62 and put your API key.

If you don't have an API key, you can create at https://beta.openai.com/account/api-keys

```python
def getInputValue(self):
    query = self.lineEdit.text()
    openai.api_key = "PUT_YOUR_API_KEY_HERE"
    response = openai.Completion.create(
    model="text-davinci-003",
    prompt=f"{query}",
    temperature=1,
    max_tokens=3500,
    top_p=1,
    frequency_penalty=0.2,
    presence_penalty=0
    )
    res = response["choices"][0]["text"]
    self.textEdit.clear()
    self.textEdit.append(f"ChatGPT: {res}")
```

<h1 align="center">
  <br>
  Sample Output
  <br>
  <img src="https://github.com/mkdirlove/PyQT-ChatGPT/blob/main/chatgpt-qt.png" alt="PyQT-ChatGPT">
</p>
