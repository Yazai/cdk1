# CDK の最初のプロジェクト(python)

- 参照
aws cdk workshop を元に進める。
- https://summit-online-japan-cdk.workshop.aws/30-python/20-create-project/100-cdk-init.html



## 環境設定 Windows 10 + vscode + python3.8
### 初期設定(vscodeのterminal)
```cmd

python -m venv venv
echo "venv\" > .gitignore

# vs code で powershellを実行許可(venvのため)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process

# これでterminalが(venv) c:\....の様に表示されてvenv環境になればOK。
.\venv\Scripts\activate
```
### editorで起動時に毎回上記設定が読み取られるようにする
vscode の設定(setting.json)で下記を追加。起動時にvenvをActivateさせる。
```json
{
  "terminal.integrated.profiles.windows": {
    "PowerShell": {
      "source": "PowerShell",
      "args": [
        "-NoExit",
        "-Command",
        "Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process;.\\venv\\Scripts\\activate"
      ],
    }
  },
  "terminal.integrated.defaultProfile.windows": "PowerShell"
}
```

### 環境復元時（プロジェクトフォルダで）
```cmd
python -m venv venv
pip install -r requirements.txt
```