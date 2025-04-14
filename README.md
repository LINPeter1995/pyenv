# pyenv下載與設置

1.下載 pyenv-win

https://github.com/pyenv-win/pyenv-win/releases

2.在終端機下這指令可將壓縮檔解壓縮到使用者目錄的 .pyenv 資料夾中📁

Expand-Archive -Path "C:\Users\你的使用者名稱\Downloads\pyenv-win-3.1.1.zip" -DestinationPath "$env:USERPROFILE\.pyenv"

3.檢查現有的環境變數：

[System.Environment]::GetEnvironmentVariable("PYENV", [System.EnvironmentVariableTarget]::User)
[System.Environment]::GetEnvironmentVariable("PATH", [System.EnvironmentVariableTarget]::User)

4.設置環境變數

設定 PYENV 變數

[System.Environment]::SetEnvironmentVariable("PYENV", "$env:USERPROFILE\.pyenv\pyenv-win-3.1.1\pyenv-win", [System.EnvironmentVariableTarget]::User)

設定 PATH 變數，包含 pyenv 的 bin 和 shims 目錄

[System.Environment]::SetEnvironmentVariable("PATH", "$env:USERPROFILE\.pyenv\pyenv-win-3.1.1\pyenv-win\bin;$env:USERPROFILE\.pyenv\pyenv-win-3.1.1\pyenv-win\shims;$env:PATH", [System.EnvironmentVariableTarget]::User)

5.重啟 PowerShell 或 VS Code 終端機輸入

pyenv --version

pyenv install 3.11.0b4

pyenv global 3.11.0b4
