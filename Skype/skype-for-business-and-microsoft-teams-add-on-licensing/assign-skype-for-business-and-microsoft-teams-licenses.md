---
title: "Asignar Skype para Business y Microsoft Teams licencias"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Asignar Skype para Business y Microsoft Teams licencias

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/fd41934d-f2eb-4a1b-89d8-32cb37702b33). 
  
Este artículo proporciona sugerencias sobre cómo asignar licencias a los usuarios para características como conferencias de Audio, el sistema telefónico y llamar a los planes. También proporciona secuencias de comandos para asignar licencias en masa.
  
 **Importante**: vea[Skype para Business y Microsoft Teams licencias de complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información acerca de las licencias necesita comprar y **cómo comprar**, dependiendo de su plan de Office 365 - para que los usuarios obtengan conferencias de Audio, números de teléfono gratuitos y la capacidad de llamar a números de teléfono fuera de su empresa.
  
## Sistema y planes de llamada de teléfono: sugerencias y secuencias de comandos para la asignación de licencias

### ¿Qué debe saber antes de asignar conferencias de Audio, el sistema telefónico y llamar a planear licencias

- **IMPORTANTE**: Para poder ver la opción **Voz** en el panel de navegación izquierdo del Centro de administración de Skype Empresarial, primero tiene que adquirir como mínimo una **licencia de Enterprise E5**, una licencia del complemento **Sistema telefónico** o una licencia del complemento **Audioconferencia**.
    
- **Con conectividad de RTC local para usuarios de híbrido?** Si es así, solo necesita asignar una licencia de **Sistema telefónico**. Debe **no** asignar un Plan de llamada.
    
- **Latencia después de la asignación de licencias**: debido a la latencia entre Office 365 y Skype Empresarial Online, posiblemente puede tardar hasta 24 horas para un usuario que se va a asignar un Plan de llamada después de asignar una licencia. Si después de 24 horas el usuario no está asignado a un Plan de llamar, por favor,[Póngase en contacto con el soporte de Office 365 para empresas: ayuda para administradores](http://technet.microsoft.com/library/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b%28Office.14%29.aspx).
    
- **Mensajes de error**: se recibe un mensaje de error si todavía no lo ha adquirido el número correcto de licencias. Si necesita comprar más licencias de llamar a planear, elija **comprar más**.
    
- **Pasos siguientes**: después de asignar licencias de Plan de llamar a los usuarios, debe obtener los números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización. Para obtener instrucciones detalladas, vea[Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Cómo asignar una licencia de sistema telefónico y planear una llamada a un usuario

Los pasos son los mismos como asignar una licencia de Office 365. Vea [Asignar o cancelar licencia para Office 365 para empresas](http://technet.microsoft.com/library/997596b5-4173-4627-b915-36abac6786dc%28Office.14%29.aspx).
  
### Cómo asignar licencias de sistema telefónico y llamar a planear en masa

1. Instale los **servicios en línea sesión Ayudante de Microsoft para profesionales de TI RTW**. ¿No tiene instalado el módulo? Vea[Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.
    
2. Instalar el **Windows Azure Active Directory Module.** ¿No tiene instalado el módulo? Para obtener instrucciones de descarga y sintaxis cmdlet, vea[Administrar Azure AD con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .
    
3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:
    
    En este ejemplo se asigna una **licencia Enterprise E3** junto con un **Sistema telefónico** y una licencia de **Llamar a planear nacionales**.
    
    El nombre de las licencias o los nombres de producto en la secuencia de comandos que se indican en texto de cursiva (consulte **sistema telefónico y Plan de llamar a los nombres de producto o SKU usado para secuencias de comandos**, después en el ejemplo).
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice.
Connect-MSOLService

#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users.
$users = Get-Content $OFD.filename

#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### Sistema telefónico y planes de llamar a los nombres de producto o SKU usado para secuencias de comandos

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|E5 Enterprise (con el sistema telefónico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefónico  <br/> |MCOEV  <br/> |
|Plan de llamadas internacionales  <br/> |MCOPSTN2  <br/> |
|Plan de llamadas nacionales  <br/> |MCOPSTN1  <br/> |
|Créditos de comunicaciones  <br/> |MCOPSTNPP  <br/> |
   
## Conferencias de audio: Sugerencias y secuencias de comandos para la asignación de licencias

### Lo que debe saber antes de la asignación de licencias de conferencias de Audio

- **Proveedor de servicios de audioconferencia de terceros**: si ha alguien está configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando se asigna una licencia de **Conferencias de Audio**, se cambiarán para usar Microsoft como el conferencias de audio proveedor de servicios. Se puede cambiar al proveedor de terceros.
    
- Pasos siguientes: después de asignar licencias de **Conferencias de Audio**, debe asignar un proveedor de servicios de audioconferencia. Siga uno de estos procedimientos:
    
  - [Asignar Microsoft como proveedor de conferencias de audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - O bien, [Asignar a un tercero como el proveedor de conferencias de audio](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### Cómo asignar una licencia de conferencias de Audio a un usuario

Los pasos son los mismos como asignar una licencia de Office 365. Vea [Asignar o cancelar licencia para Office 365 para empresas](http://technet.microsoft.com/library/997596b5-4173-4627-b915-36abac6786dc%28Office.14%29.aspx).
  
### Cómo asignar licencias de conferencias de Audio en masa

1. Descargue e instale [Microsoft Online Services sesión Asistente para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Descargar e instalar la **Windows Azure Active Directory Module.** Para obtener instrucciones de descarga y sintaxis cmdlet, vea[Administrar Azure AD con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .
    
    Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:
    
    El nombre de las licencias o los nombres de producto en la secuencia de comandos aparecen en texto de cursiva. Ver [Nombres de productos de conferencias de audio o SKU usado para secuencias de comandos](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku) para todos los nombres de producto.
    
    En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de conferencias de Audio.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService

#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    } 

  ```

### Nombres de productos de conferencias de audio o SKU usado para secuencias de comandos
<a name="sku"> </a>

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Audioconferencia  <br/> |MCOMEETADV  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> | STANDARDPACK <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|E5 Enterprise (sin audioconferencia)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|E5 Enterprise (con las conferencias de Audio)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## Créditos de comunicaciones

### Lo que debe saber antes de la asignación de licencias de créditos de comunicaciones

- **Los clientes de Enterprise E5**: incluso si los usuarios se asignan licencias Enterprise E5, aun así es recomendable asignarlos licencias de **Créditos de comunicaciones**.
    
- **Pasos siguientes**: después de asignar estas licencias, debe obtener los números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización. Para obtener instrucciones detalladas, vea[Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Cómo asignar una licencia de créditos de comunicaciones a un usuario

Los pasos son los mismos como asignar una licencia de Office 365. Vea [Asignar o cancelar licencia para Office 365 para empresas](http://technet.microsoft.com/library/997596b5-4173-4627-b915-36abac6786dc%28Office.14%29.aspx).
  
### Cómo asignar licencias de créditos de comunicaciones de forma masiva

Eche un vistazo a la secuencia de comandos para asignar licencias de **Conferencias de Audio**. Actualizar con la información de asignación de licencias de **Créditos de comunicaciones**.
  
## Artículos relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Agregar fondos y administrar créditos de comunicaciones](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

