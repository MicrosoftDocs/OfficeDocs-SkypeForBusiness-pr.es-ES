---
title: Asignar licencias de Skype Empresarial
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: f2b2e2ad4952b55fade7e0b8eddb1755ea3f2cea
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887819"
---
# <a name="assign-skype-for-business-licenses"></a>Asignar licencias de Skype Empresarial

This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.

> [!IMPORTANT]
> Consulte [licencias complementarias de Skype empresarial](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información sobre las licencias que necesita comprar y **Cómo** realizarlas, en función de su plan de 365 de Office, para que los usuarios reciban conferencias de audio, números gratuitos y la posibilidad de llamar a números de teléfono fuera de su empresa.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias

Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas

- **Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.

- **Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.
    
- **Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Cómo asignar un sistema telefónico y una licencia de plan de llamadas a un usuario

The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva

1. Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.

2. Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.

3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

   En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.

   El nombre de las licencias o nombres de productos en la secuencia de comandos se muestra en cursiva (consulte **nombres de producto del plan de llamadas y sistemas telefónicos o SKU usados para scripting**, después del ejemplo).

   ```powershell
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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Sistema telefónico y planes de llamadas nombres de producto o SKU usados para scripting

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Enterprise E5 (con Sistema telefónico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefónico  <br/> |MCOEV  <br/> |
|Plan de llamadas internacionales  <br/> |MCOPSTN2  <br/> |
|Plan de llamadas nacionales (3000 min Estados Unidos/1200 mín. planes de la UE)  <br/> |MCOPSTN1  <br/> |
|Plan de llamadas nacionales (120)  <br/> |MCOPSTN5  <br/> |
|Plan de llamadas nacionales (240)  <br/> |MCOPSTN6  <br/> |
|Créditos de comunicaciones  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferencias: sugerencias y scripts para asignar licencias

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Lo que debe saber antes de asignar licencias de audioconferencia

- **Proveedor de servicios de audioconferencia de terceros**: si alguien ya está configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de **audioconferencia** , se cambiará para usar Microsoft como el proveedor de servicios de audioconferencia. Puede volver a cambiar al usuario al proveedor de terceros.

- Pasos siguientes: después de asignar las licencias de **audioconferencia** , debe asignar un proveedor de servicios de audioconferencia. Consulte [Asignar a Microsoft como proveedor de audioconferencias].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Cómo asignar una licencia de audioconferencia a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Cómo asignar licencias de audioconferencia en masa

1. Descargue e instale [el ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

    El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva. Ver los nombres de los [productos de audioconferencia o las SKU usadas para los scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) de todos los nombres de productos.

    Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de audioconferencia.

    ```powershell
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nombres de los productos de audioconferencias o SKU usados para scripting
<a name="sku"> </a>

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Audioconferencia  <br/> |MCOMEETADV  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (sin Audioconferencia)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (con audioconferencias)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Créditos de comunicaciones

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Lo que debe saber antes de asignar licencias de créditos de comunicaciones

- **Clientes de Enterprise E5**: incluso si los usuarios tienen asignadas licencias Enterprise E5, le recomendamos que les asigne licencias de **créditos para comunicaciones** .
    
- **Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta. Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Cómo asignar una licencia de créditos de comunicaciones a un usuario

Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Cómo asignar las licencias de crédito de comunicaciones a granel

Eche un vistazo a la secuencia de comandos de ejemplo para asignar licencias de **audioconferencia** . Actualícelo con la información para asignar licencias de **créditos de comunicaciones** .

## <a name="related-topics"></a>Temas relacionados
  
[Configurar planes de llamadas](/microsoftteams/set-up-calling-plans)
  
[Agregar fondos y administrar los créditos de comunicaciones](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
