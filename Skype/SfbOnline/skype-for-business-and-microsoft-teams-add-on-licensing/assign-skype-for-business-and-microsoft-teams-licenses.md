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
ms.openlocfilehash: 41f1788e4c562f3b4cc1f43d7875b64805b19ed8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237496"
---
# <a name="assign-skype-for-business-licenses"></a>Asignar licencias de Skype Empresarial

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios para acceder a características como las Audioconferencias, el Sistema telefónico y los Planes de llamadas. También proporciona scripts para asignar varias licencias a la vez.

> [!IMPORTANT]
> Consulte Skype Empresarial licencias de complementos para obtener información sobre las  licencias que necesita comprar y cómo comprarlas ,según su plan de Microsoft 365 o Office 365, para que los usuarios obtengan audioconferencias, números gratuitos y la capacidad de llamar [a](skype-for-business-and-microsoft-teams-add-on-licensing.md) números de teléfono fuera de su empresa.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias

Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas

- **¿Está usando conectividad RTC local para los usuarios híbridos?** Si es así, solo tiene que asignar una **Sistema telefónico** licencia. NO debe **asignar** un plan de llamadas.

- Latencia después de asignar **licencias:** debido a la latencia entre Microsoft 365 o Office 365 y Skype Empresarial Online, es posible que tarde hasta 24 horas en asignar un plan de llamadas a un usuario después de asignar una licencia. Si después de 24 horas el usuario no tiene asignado un plan de llamadas, póngase en contacto con el soporte técnico para productos [empresariales: Ayuda para administradores.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- **Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto. Si necesita comprar más licencias del Plan de llamadas, elija **Comprar más.**
    
- **Pasos siguientes:** Después de asignar licencias del Plan de llamadas a los usuarios, tendrá que obtener los números de teléfono de su organización y, a continuación, asignar esos números a las personas de su organización. Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Cómo asignar una licencia de Sistema telefónico y plan de llamadas a un usuario

Los pasos son los mismos que asignar una Microsoft 365 o Office 365 licencia. Vea [Asignar o quitar licencias para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva

1. Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**. ¿No tiene instalado el módulo? Consulte [Microsoft Online Services Sign-In asistente para profesionales de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.

2. Instale el **Módulo Microsoft Azure Active Directory**. ¿No tiene instalado el módulo? Consulte [Administrar Azure AD con Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) instrucciones de descarga y sintaxis de cmdlets.

3. Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

   En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.

   El nombre de las licencias o los nombres de producto del script se muestran en texto en cursiva (vea Sistema telefónico y Nombres de producto del plan de llamadas o SKU usados para **scripting,** después del ejemplo).

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Sistema telefónico y planes de llamadas o SKU usados para scripting

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Enterprise E5 (con Sistema telefónico)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Sistema telefónico  <br/> |MCOEV  <br/> |
|Plan de llamadas internacionales  <br/> |MCOPSTN2  <br/> |
|Plan de llamadas nacionales (3000 min ee. UU. / 1200 min planes de la UE)  <br/> |MCOPSTN1  <br/> |
|Plan de llamadas nacionales (plan de llamadas de 120 minutos)  <br/> |MCOPSTN5  <br/> |
|Plan de llamadas nacionales (plan de llamadas de 240 minutos)  <br/> |MCOPSTN6  <br/> |
|Créditos de comunicaciones  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconferencia: Sugerencias y scripts para asignar licencias

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Lo que necesita saber antes de asignar licencias de audioconferencia

- Proveedor de servicios de **audioconferencia** de terceros: si alguien ya está configurado para usar un  proveedor de audioconferencia de terceros, al asignarle una licencia de audioconferencia, se cambiará para usar Microsoft como proveedor de audioconferencias. Puede volver a cambiar al usuario al proveedor de terceros.

- Pasos siguientes: Después de asignar licencias de **conferencias** de audio, debe asignar un proveedor de servicios de audioconferencia. Consulte [Asignar a Microsoft como proveedor de audioconferencias].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Cómo asignar una licencia de audioconferencia a un usuario

Los pasos son los mismos que asignar una Microsoft 365 o Office 365 licencia. Vea [Asignar o quitar licencias para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Cómo asignar licencias de audioconferencia en masa

1. Descargar e instalar [Microsoft Online Services Sign-In asistente para profesionales de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en [Administrar Azure AD mediante Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).

    Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:

    El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva. Vea [Nombres de productos de audioconferencia o SKU](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) usados para scripting para todos los nombres de producto.

    En este ejemplo se asigna una Enterprise de E3 junto con una licencia de audioconferencia.

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nombres de productos de audioconferencia o SKU usados para scripting
<a name="sku"> </a>

|**Nombre del producto**|**Nombre de la parte SKU**|
|:-----|:-----|
|Audioconferencia  <br/> |MCOMEETADV  <br/> |
|Plan independiente 2 de Skype Empresarial Online  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5 (sin Audioconferencia)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (con audioconferencia)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Créditos de comunicaciones

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Lo que necesita saber antes de asignar licencias de créditos de comunicaciones

- **Enterprise clientes de E5:** Incluso si los usuarios están asignados Enterprise licencias de E5, le recomendamos que les asigne licencias de créditos **de** comunicaciones.
    
- **Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta. Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Cómo asignar una licencia de créditos de comunicaciones a un usuario

Los pasos son los mismos que asignar una Microsoft 365 o Office 365 licencia. Vea [Asignar o quitar licencias para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Cómo asignar licencias de créditos de comunicaciones en masa

Echa un vistazo al script de ejemplo para asignar **licencias de audioconferencia.** Actualíctela con la información para asignar licencias **de créditos de** comunicaciones.

## <a name="related-topics"></a>Temas relacionados
  
[Configurar planes de llamadas](/microsoftteams/set-up-calling-plans)
  
[Agregar fondos y administrar los créditos de comunicaciones](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
