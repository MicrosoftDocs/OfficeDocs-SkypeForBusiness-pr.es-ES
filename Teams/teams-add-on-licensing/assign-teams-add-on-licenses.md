---
title: Asignar licencias de complementos de Teams a los usuarios
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Obtenga información sobre cómo asignar licencias de complementos de Teams a los usuarios para características como audioconferencia, teléfonos telefónicos y planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788744"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Asignar licencias de complementos de Teams a los usuarios

Las licencias de complemento son licencias para características específicas de Teams, como la audioconferencia, el sistema telefónico y los planes de llamadas. En este artículo se describe cómo asignar licencias de complemento a usuarios individuales y a grandes conjuntos de usuarios de forma masiva.

> [!NOTE]
> Vea [licencias de complementos de Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) para las características de teams que están disponibles con las licencias de complemento. También encontrará información sobre las licencias que necesita comprar y sobre cómo hacerlas (según su plan), de modo que los usuarios puedan obtener características como audioconferencias, números gratuitos y la posibilidad de llamar a números de teléfono fuera de su organización. Después de decidir qué características quiere para los usuarios, asígneles las licencias.

Puede usar el centro de administración de Microsoft 365 o PowerShell para asignar licencias a los usuarios de su organización. Para administrar las licencias, debe ser administrador global o administrador de administración de usuarios.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Lo que debe saber antes de asignar licencias de sistema telefónico, plan de llamadas y crédito de comunicaciones

Antes de empezar, revise lo siguiente:

- Si usa conectividad de red telefónica conmutada (RTC) local para usuarios híbridos, solo tiene que asignar una licencia de sistema telefónico. NO asigne una licencia de plan de llamadas.

- Debido a la latencia entre Microsoft 365 y Microsoft Teams, un usuario puede tardar hasta 24 horas en asignar un plan de llamadas después de asignar una licencia. Si al usuario no se le ha asignado un plan de llamadas después de 24 horas, [póngase en contacto con el soporte técnico para productos para empresas: ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Recibirá un mensaje de error si no ha comprado el número correcto de licencias. Si necesita comprar más licencias del plan de llamadas, elija la opción para comprar más.

- Incluso si los usuarios tienen asignadas licencias de Enterprise E5, seguirá necesitando asignar licencias de [crédito de comunicaciones](../what-are-communications-credits.md) a ellas si desean realizar o recibir llamadas de la RTC.

- Después de asignar licencias de planes o comunicaciones de crédito de llamadas a los usuarios, tendrá que obtener números de teléfono de la organización y, a continuación, asignar esos números a los usuarios. Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Usar el centro de administración de Microsoft 365

Use el centro de administración de Microsoft 365 para asignar licencias a usuarios individuales o a conjuntos de usuarios pequeños a la vez. Puede asignar licencias en la página **licencias** (para un máximo de 20 usuarios a la vez) o la página **usuarios activos** . El método que elija dependerá de si desea administrar las licencias de producto para usuarios específicos o administrar licencias de usuario para productos específicos.

Para obtener instrucciones paso a paso, vea [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Si necesita asignar licencias para un gran número de usuarios, como cientos o miles de usuarios, use PowerShell o [licencias basadas en grupos en Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Con PowerShell

Use PowerShell para asignar licencias a usuarios de forma masiva.  Para obtener más información, vea [asignar licencias a cuentas de usuario con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script de ejemplo

Este es un ejemplo de cómo usar un script para asignar licencias a los usuarios.

1. Instale la versión de 64 del [Asistente para inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
2. Instale el módulo Microsoft Azure Active Directory para Windows PowerShell:
    1. Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).
    2. Ejecute el siguiente comando:
        ```powershell
        Install-Module MSOnline
        ```
    3. Si se le pide que instale el proveedor de NuGet, escriba **y**y, a continuación, presione Entrar.
    4. Si se le pide que instale el módulo desde PSGallery, escriba **y**y, a continuación, presione Entrar.
3. En el símbolo del sistema de Windows PowerShell, ejecute el siguiente script para asignar licencias a los usuarios, donde \<CompanyName:License> es el nombre de la organización y el identificador de la licencia que desea asignar. Por ejemplo, litwareinc: MCOMEETADV.

    El identificador es diferente al nombre descriptivo de la licencia. Por ejemplo, el identificador de audioconferencia es MCOMEETADV. Para obtener más información, consulte [nombres de productos y identificadores de SKU para licencias](#product-names-and-sku-identifiers-for-licensing).

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    Por ejemplo, para asignar licencias de Microsoft 365 Enterprise 1 y audioconferencias, use la siguiente sintaxis en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para asignar una licencia de Microsoft Business Voice (sin plan de llamadas), use la siguiente sintaxis en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nombres de producto y identificadores de SKU para licencias

Esta es una lista parcial de nombres de producto y sus nombres de elementos SKU correspondientes que puede usar como referencia al usar PowerShell para administrar licencias en Teams.

Para obtener más información, vea [ver licencias y servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nombres de producto y identificadores de plan de servicio para licencias](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)y referencia de [SKU de educación](../sku-reference-edu.md).

| Nombre del producto| Nombre de la parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con sistema telefónico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sin audioconferencias) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con conferencias de audio) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Empresa Básico | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Empresa Estándar | O365_BUSINESS_PREMIUM|
| Microsoft 365 Empresa | B|
| Microsoft Business Voice (Canadá)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Reino Unido) | BUSINESS_VOICE  |
| Microsoft Business Voice (Estados Unidos) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (sin plan de llamadas) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (sin plan de llamadas) para los Estados Unidos| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconferencia | MCOMEETADV | 
| Pago de audioconferencias por minuto (pagar a medida que hablas)</br>*Requiere la configuración y la habilitación de créditos de comunicaciones.* | MCOMEETACPEA |
| Sistema telefónico | MCOEV |
| Plan de llamadas nacionales e internacionales | MCOPSTN2 |
| Plan de llamadas nacionales (3000 minutos por usuario y mes para Estados Unidos/PR/CA, 1200 minutos por usuario y mes para países de la UE) | MCOPSTN1 |
| Plan de llamadas nacionales (120 minutos por usuario/mes por país) </br>*Este plan no está disponible en los Estados Unidos.* | MCOPSTN5 |
| Plan de llamadas nacionales (240 minutos por usuario/mes por país) </br>*Este plan no está disponible en los Estados Unidos.* | MCOPSTN6 |
| Créditos de comunicaciones | MCOPSTNPP |

## <a name="related-topics"></a>Temas relacionados

- [Licencias complementarias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Gestionar acceso de los usuarios a Microsoft Teams](../user-access.md)
- [Ver licencias y servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referencia de SKU de educación](../sku-reference-edu.md)