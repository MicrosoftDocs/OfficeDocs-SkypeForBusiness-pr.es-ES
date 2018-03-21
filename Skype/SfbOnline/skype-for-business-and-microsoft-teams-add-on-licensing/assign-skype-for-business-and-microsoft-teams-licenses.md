---
title: Asignar Skype para licencias de negocio y Teams de Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Aprenda cómo asignar Skype para licencias profesionales para el sistema telefónico, conferencias de Audio, llamando a los planes y créditos de comunicaciones. "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Asignar Skype para licencias de negocio y Teams de Microsoft

Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios características como conferencias de Audio, sistema de teléfono y llamar a los planes. También proporciona scripts para asignar varias licencias a la vez.
  
 **Importante**: Véase [Skype para negocios y equipos de Microsoft licencias adicionales](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información acerca de las licencias del cliente necesita comprar y **cómo comprar** , dependiendo de su plan de Office 365 - por lo que los usuarios obtienen las conferencias de Audio, números de teléfono gratuitos, y la posibilidad de llamar a números de teléfono fuera de su negocio.
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema y planes de llamada de teléfono: consejos y secuencias de comandos para asignar licencias

Lo que necesita saber antes de asignar las conferencias de Audio, sistema telefónico y Plan de llamadas licencias

- **¿Está usando conectividad RTC local para los usuarios híbridos?** Si es así, sólo necesita asignar una licencia de **Sistema de teléfono** . Debe **no** asignar un Plan de llamadas.
    
- **Latencia después de asignar licencias**: debido a la latencia entre Office 365 y Skype para los negocios en línea, posiblemente puede tardar hasta 24 horas para que un usuario asignará un Plan de llamadas después de asignar una licencia. Si después de 24 horas el usuario no está asignado a un Plan de llamadas, por favor, [en soporte técnico para los productos business - ayuda de Admin](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto. Si necesita adquirir más licencias de Plan de llamadas, elija **comprar más**.
    
- **Próximos pasos**: después de asignar licencias de Plan de llamadas a los usuarios, necesitará obtener sus números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización. Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Cómo asignar una licencia de sistema telefónico y Plan de llamadas a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Cómo asignar licencias de sistema telefónico y Plan de llamadas de forma masiva

1. Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**. ¿No tiene instalado el módulo? Consulte [Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.
    
2. Instale el **Módulo Microsoft Azure Active Directory**. ¿No tiene instalado el módulo? Consulte [administrar AD Azure mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obtener instrucciones de descarga y sintaxis del cmdlet.
    
3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:
    
  Este ejemplo asigna una **licencia de Enterprise E3** junto con un **Sistema de teléfono** y una licencia de **Plan de llamadas nacionales** .
    
  El nombre de las licencias o los nombres de producto en la secuencia de comandos se muestran en texto cursiva (Véase **sistema telefónico y Plan de llamadas nombres de producto o SKU utilizados para secuencias de comandos**, después del ejemplo).
    
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
  #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
  International Calling.
  for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 
  ```
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nombres de productos de sistema de teléfono y llamar a planes o SKU utilizados para secuencias de comandos

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|E5 Enterprise (con sistema de teléfono)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefónico  <br/> |MCOEV  <br/> |
|Plan de llamadas internacionales  <br/> |MCOPSTN2  <br/> |
|Plan de llamada nacional  <br/> |MCOPSTN1  <br/> |
|Créditos de comunicaciones  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Conferencias de audio: Los consejos y scripts para asignar licencias

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Lo que necesita saber antes de asignar licencias de conferencia de Audio

- **Proveedor de conferencia de audio de terceros**: si ya alguien está configurado para utilizar un proveedor de conferencia de audio de terceros, cuando se asigna una licencia de **Conferencias de Audio** , se modificarán para utilizar Microsoft como el conferencias de audio proveedor de servicios. Puede volver a cambiar al usuario al proveedor de terceros.
    
- Próximos pasos: después de asignar licencias de **Conferencias de Audio** , debe asignar un proveedor de conferencia de audio. Realice una de las acciones siguientes:
    
  - [Asignar a Microsoft como proveedor de servicios de audioconferencia](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - O bien, [asignar un tercero como el proveedor de conferencia de audio](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Cómo asignar una licencia de conferencia de Audio a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Cómo asignar licencias de conferencia de Audio de forma masiva

1. Descargue e instale el [Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:
    
    El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva. Ver [los nombres de productos de conferencia de Audio o SKU utilizados para secuencias de comandos](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para todos los nombres de producto.
    
    Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de conferencia de Audio.
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nombres de productos de audio conferencia o SKU utilizados para secuencias de comandos
<a name="sku"> </a>

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Audioconferencia  <br/> |MCOMEETADV  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|E5 de la empresa (sin conferencias de Audio)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|E5 Enterprise (con conferencias de Audio)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## <a name="communications-credits"></a>Créditos de comunicaciones

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Lo que necesita saber antes de asignar licencias de créditos de comunicaciones

- **Los clientes de empresa E5**: incluso si los usuarios se asignan licencias Enterprise E5, aun así es recomendable asignarlos licencias de **Créditos de comunicaciones** .
    
- **Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta. Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Cómo asignar una licencia de créditos de comunicaciones para un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Cómo asignar licencias de créditos de comunicaciones en masa

Observemos la secuencia de comandos para asignar licencias de **Conferencia de Audio** . Para actualizarlo con la información de asignación de licencias de **Créditos de comunicaciones** .
  
## <a name="related-topics"></a>See also

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[Configurar Planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Agregar fondos y administrar Créditos de comunicaciones](add-funds-and-manage-communications-credits.md)
  