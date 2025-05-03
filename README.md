# pyenv-win 安裝與設置（Windows 版本專用）

步驟 1：下載 pyenv-win

前往 GitHub Releases 頁面下載最新版 pyenv-win：

https://github.com/pyenv-win/pyenv-win/releases

下載 .zip 壓縮檔，例如：

pyenv-win-3.1.1.zip

步驟 2：解壓縮到使用者目錄

在 PowerShell（建議用「以系統管理員身份執行」）中執行：

Expand-Archive -Path "C:\Users\Tibame\Downloads\pyenv-win-3.1.1.zip" -DestinationPath "$env:USERPROFILE\pyenv"

解壓後的結構應該是：

C:\Users\Tibame\pyenv\pyenv-win-3.1.1\pyenv-win\

步驟 3：檢查現有環境變數（非必要步驟，但可用於確認）

[System.Environment]::GetEnvironmentVariable("PYENV", [System.EnvironmentVariableTarget]::User)

[System.Environment]::GetEnvironmentVariable("PATH", [System.EnvironmentVariableTarget]::User)

步驟 4：設置環境變數（User 層級）

# 設定 PYENV 變數

[System.Environment]::SetEnvironmentVariable("PYENV", "$env:USERPROFILE\pyenv\pyenv-win-3.1.1\pyenv-win", [System.EnvironmentVariableTarget]::User)

# 加入 PATH，包含 bin 和 shims

[System.Environment]::SetEnvironmentVariable("PATH", "$env:USERPROFILE\pyenv\pyenv-win-3.1.1\pyenv-win\bin;$env:USERPROFILE\pyenv\pyenv-win-3.1.1\pyenv-win\shims;$env:PATH", 

[System.EnvironmentVariableTarget]::User)

步驟 5：重新啟動 PowerShell 或 VS Code Terminal

步驟 6：確認 pyenv 安裝成功

pyenv --version

接下來就可以使用：

pyenv install 3.11.0

pyenv global 3.11.0

補充建議（可選）：

C:\Users\Tibame\.pyenv\

這樣路徑會比較乾淨，也符合官方建議路徑。

為了未來升級方便，可以把 pyenv-win 解壓到：


