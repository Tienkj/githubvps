# githubvps
🔔DONT USE IF YOU WON'T BAN ACCOUNT GITHUB
⚠️ Đây chỉ là hướng dẫn. GitHub Actions không phải VPS 24/7. 
Sử dụng sai mục đích có thể bị GitHub ban account. 
Chỉ chạy thử CI/CD, deploy hoặc serverless free tier.
# Lưu ý: **đặt cảnh báo rõ ràng**: “⚠️  code này trên GitHub Actions, cực kỳ nguy hiểm!”.  

---

# CODE:
```yaml
name: TOOL TEST

on:
  workflow_dispatch:

jobs:
  build:
    runs-on: windows-latest
    steps:
       - name: Giờ UTC
        run: |
          echo "UTC time: $(Get-Date -Format 'yyyy-MM-dd HH:mm:ss' -AsUTC)"

      - name: Giờ Việt Nam
        run: |
          $vn = (Get-Date).ToUniversalTime().AddHours(7)
          echo "VN time: $($vn.ToString('yyyy-MM-dd HH:mm:ss'))"
      - name: CHATGPT
        run: |
          Invoke-WebRequest https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-windows-amd64.zip -OutFile ngrok.zip
          Expand-Archive ngrok.zip -DestinationPath ngrok
          .\ngrok\ngrok.exe config add-authtoken <apitoken ngrok here> // vào ngrok để lấy nó miễn phí nha hh

      - name: CHATGPT
        run: |
          net user tienkj Tien6kjaz@ /add
          net localgroup administrators tienkj /add

      - name: ?
        run: |
          Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server" -Name "fDenyTSConnections" -Value 0
          Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
          Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp" -Name "UserAuthentication" -Value 1

      - name: ?
        run: |
          Start-Process .\ngrok\ngrok.exe "tcp 3389" -WindowStyle Hidden

      - name: wait
        run: Start-Sleep -Seconds 10

      - name: hehe
        run: |
          $tunnel = Invoke-RestMethod -Uri "http://127.0.0.1:4040/api/tunnels"
          $addr = $tunnel.tunnels[0].public_url -replace "tcp://",""
         

      - name: keep
        run: Start-Sleep -Seconds 21600



