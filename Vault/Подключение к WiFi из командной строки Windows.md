[Статья](https://www.windowscentral.com/how-connect-wi-fi-network-windows-10)
`netsh wlan show profile`
`netsh wlan connect ssid=YOUR-WIFI-SSID name=PROFILE-NAME`
e.g  _netsh wlan connect ssid=tsunami name=tsunami_
![[wifi_cli_win1.jpg]]
#### Export Wi-Fi profile
`netsh wlan show profile`
`netsh wlan export profile PROFILE-NAME key=clear folder=PATH\TO\EXPORT\FOLDER`
e.g `netsh wlan export profile tsunami key=clear folder=C:\Users\m\Documents`
![[wifi_cli_win2.jpg]]
#### Import Wi-Fi profile
`netsh wlan add profile filename="PATH\TO\PROFILE.XML" Interface="YOUR-WIFI-ADAPTER-NAME" user=current`
e.g `netsh wlan add profile filename="C:\Users\m\Documents\wi-fi-tsunami.xml" Interface="WI-FI" user=current`
![[wifi_cli_win3.jpg]]
- **Quick tip:** If you have multiple wireless interfaces, you must also specify in the command which adapter you want to use. For example, `
- netsh wlan connect ssid=YOUR-WIFI-SSID name=PROFILE-NAME interface=Wi-Fi`