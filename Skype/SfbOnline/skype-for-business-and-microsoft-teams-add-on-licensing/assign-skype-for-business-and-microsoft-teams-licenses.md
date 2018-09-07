---
title: Asignar licencias de Skype for Business y Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: af2b7357c5dbe9e11b84ac87e0f72721d10a6a30
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856057"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Asignar licencias de Skype for Business y Microsoft Teams

Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios para acceder a características como las Audioconferencias, el Sistema telefónico y los Planes de llamadas. También proporciona scripts para asignar varias licencias a la vez.

> [!IMPORTANT]
> Vea [Licencias de complementos para Skype for Business y Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información sobre qué licencias necesitará comprar y **cómo comprarlas**, dependiendo de su plan de Office 365, para que los usuarios puedan realizar Audioconferencias, consigan números gratuitos y puedan llamar a números de teléfono fuera de su negocio.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias

Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas

- **¿Está usando conectividad RTC local para los usuarios híbridos?** Si es así, solo necesita asignar una licencia de **Sistema telefónico**. **NO** tiene que asignar un Plan de llamadas.

- **Latencia tras la asignación de licencias**: Debido a la latencia entre Office 365 y Skype Empresarial Online, es posible que se necesiten hasta 24 horas para que a un usuario se le asigne un Plan de llamadas después de que asignes una licencia. Si transcurridas 24 horas al usuario no se le ha asignado un Plan de llamadas, por favor [Póngase en contacto con el servicio de soporte técnico para los productos empresariales - Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto. Si necesita comprar más licencias de Plan de llamadas, seleccione **Comprar más**.
    
- **Siguientes pasos**: después de asignar licencias de Plan de llamadas a sus usuarios, tendrá que obtener los números de teléfono para su organización y asignarlos a los miembros de esta. Si desea consultar las instrucciones paso a paso, vea [Configurar Planes de llamadas](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Cómo asignar una licencia de Sistema telefónico y Plan de llamadas a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva

1. Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**. ¿No tiene instalado el módulo? Consulte [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.

2. Instale el **Módulo Microsoft Azure Active Directory**. ¿No tiene instalado el módulo? Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [Administrar Azure AD con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

  En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.

  El nombre de las licencias o de los productos en el script se muestran en letra cursiva (vea **Nombres de productos o SKU de Sistemas telefónicos y Planes de llamadas usados para scripting**, tras el ejemplo).

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nombres de productos o SKU de Sistemas telefónicos y Planes de llamadas usados para scripting

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Enterprise E5 (con Sistema telefónico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefónico  <br/> |MCOEV  <br/> |
|Plan de llamadas internacionales  <br/> |MCOPSTN2  <br/> |
|Plan de llamada nacional  <br/> |MCOPSTN1  <br/> |
|Créditos de comunicaciones  <br/> |MCOPSTNPP  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferencia: sugerencias y scripts para asignar licencias

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Lo que necesita saber antes de asignar licencias de Audioconferencias

- **Proveedor de servicios de audioconferencia de terceros**: si hay alguien ya configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de **Audioconferencia**, cambiará para usar Microsoft como proveedor de audioconferencias. Puede volver a cambiar al usuario al proveedor de terceros.

- Siguientes pasos: tras asignar licencias de **Audioconferencia**, es necesario asignar un proveedor de audioconferencias.
 Consulte [Asignar a Microsoft como proveedor de audioconferencias].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Cómo asignar una licencia de Audioconferencia a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Asignar licencias de Audioconferencia de forma masiva

1. Descargue e instale el [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

    El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva. Consulte [Nombres de productos o SKU de Audioconferencias usados para scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para ver todos los nombres de productos.

    En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de Audioconferencia.

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nombres de productos de Audioconferencia o SKU usados para scripting
<a name="sku"> </a>

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Audioconferencia  <br/> |MCOMEETADV  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (sin Audioconferencia)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (con Audioconferencia)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Créditos de comunicaciones

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Lo que necesita saber antes de asignar licencias de Créditos de comunicaciones

- **Clientes de Enterprise E5**: incluso aunque a sus usuarios se les hayan asignado licencias de Enterprise E5, se recomienda asignarles licencias de **Créditos de comunicaciones**.
    
- **Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta. Si desea consultar las instrucciones paso a paso, vea [Configurar Planes de llamadas](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Cómo asignar una licencia de Créditos de comunicaciones a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Cómo asignar licencias de Créditos de comunicaciones de forma masiva

Eche un vistazo al script de ejemplo para asignar licencias de **Audioconferencias**. Actualícelo con la información de asignación de licencias de **Créditos de comunicaciones**.

## <a name="related-topics"></a>Temas relacionados
  
[Configurar Planes de llamada](/microsoftteams/set-up-calling-plans)
  
[Agregar fondos y administrar Créditos de comunicaciones](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
