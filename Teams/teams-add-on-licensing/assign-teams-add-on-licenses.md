---
title: Asignar licencias de complementos de Teams a los usuarios
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo asignar licencias de complementos de Teams a los usuarios para características como Audioconferencia, Sistema telefónico y Planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196934"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Asignar licencias de complementos de Teams a los usuarios

Las licencias de complementos son licencias para características específicas de Teams, como Audioconferencia, Sistema telefónico y Planes de llamadas. En este artículo se describe cómo asignar licencias de complementos a usuarios individuales y a grandes conjuntos de usuarios de forma masiva.

> [!NOTE]
> Consulte [las licencias de complementos de Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) para las características de Teams que están disponibles con licencias de complementos. También encontrará información sobre qué licencias debe comprar y cómo comprarlas (según su plan), para que los usuarios puedan obtener características como Audioconferencia, números gratuitos y la posibilidad de llamar a números de teléfono fuera de su organización. Después de decidir qué características desea para sus usuarios, asígneles las licencias.

Puede usar el Centro de administración de Microsoft 365 o PowerShell para asignar licencias a los usuarios de su organización. Debe ser administrador global o administrador de administración de usuarios para poder administrar las licencias.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Lo que debe saber antes de asignar licencias de Sistema telefónico, Plan de llamadas y Crédito de comunicación

Antes de empezar, revise los siguientes requisitos:

- Si usa la conectividad local de red telefónica conmutada (RTC) para los usuarios híbridos, solo tiene que asignar una licencia de Sistema telefónico. No asigne una licencia de plan de llamadas.

- Debido a la latencia entre Microsoft 365 y Microsoft Teams, pueden tardar hasta 24 horas en asignar un plan de llamadas a un usuario después de asignar una licencia. Si al usuario no se le asigna un plan de llamadas después de 24 horas, póngase en contacto con el soporte técnico para productos [empresariales: ayuda del administrador.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Verá un mensaje de error si no ha comprado la cantidad correcta de licencias. Si necesitas comprar más licencias de plan de llamadas, elige la opción para comprar más.

- Incluso si los usuarios tienen asignadas licencias De [](../what-are-communications-credits.md) Enterprise E5, tendrá que asignarles licencias de crédito de comunicaciones si desean realizar o recibir llamadas de RTC.

- Después de asignar licencias de planes de llamadas o créditos de comunicación a los usuarios, necesitarás obtener números de teléfono para tu organización y asignarlos a los usuarios. Para obtener instrucciones detalladas, consulte [Configurar planes de llamadas.](../set-up-calling-plans.md)

## <a name="using-the-microsoft-365-admin-center"></a>Uso del Centro de administración de Microsoft 365

Use el Centro de administración de Microsoft 365 para asignar licencias a usuarios individuales o a conjuntos reducidos de usuarios a la vez. Puede asignar licencias en la **página Licencias** (para un máximo de 20 usuarios a la vez) o en la **página Usuarios** activos. El método que elija dependerá de si desea administrar licencias de producto para usuarios específicos o administrar licencias de usuario para productos específicos.

Para obtener instrucciones detalladas, consulte [Asignar licencias a usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

Si necesita asignar licencias para un gran número de usuarios, como cientos o miles de usuarios, use Powershell o licencias basadas en grupos en [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>Con PowerShell

Use PowerShell para asignar licencias a los usuarios en masa.  Para obtener más información, [vea Asignar licencias a cuentas de usuario con PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>Script de ejemplo

Este es un ejemplo de cómo usar un script para asignar licencias a los usuarios.

1. Instale la versión de 64 bits del Microsoft Online Services asistente para el inicio de sesión para profesionales de TI [RTW.](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)
2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell:
    1. Abra un símbolo del Windows PowerShell de sistema con privilegios elevados (ejecute Windows PowerShell como administrador).
    2. Ejecute el siguiente comando:
        ```powershell
        Install-Module MSOnline
        ```
    3. Si se le pide que instale el proveedor de NuGet, escriba **Y** y, después, presione Entrar.
    4. Si se le solicita que instale el módulo desde PSGallery, escriba **Y** y, a continuación, presione Entrar.
3. En el Windows PowerShell símbolo del sistema, ejecute el script siguiente para asignar licencias a los usuarios, donde se encuentra el nombre de la organización y el identificador de la licencia \<CompanyName:License> que desea asignar. Por ejemplo, litwareinc:MCOMEETADV.

    El identificador es diferente al nombre descriptivo de la licencia. Por ejemplo, el identificador de Audioconferencia es MCOMEETADV. Para obtener más información, vea [Nombres de producto e identificadores de SKU para licencias.](#product-names-and-sku-identifiers-for-licensing)

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

    Por ejemplo, para asignar licencias de Microsoft 365 Enterprise 1 y Audioconferencia, use la siguiente sintaxis en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para asignar una licencia de Microsoft Business Voice (sin plan de llamadas), use la siguiente sintaxis del script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nombres de producto e identificadores de SKU para licencias

Esta es una lista parcial de nombres de producto y sus correspondientes nombres de pieza de SKU que puede usar como referencia al usar PowerShell para administrar licencias en Teams.

Para obtener más información, vea Ver licencias y servicios con [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)nombres de productos e identificadores de plan de [servicio](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)para licencias y referencia [de SKU para educación.](../sku-reference-edu.md)

| Nombre del producto| Nombre de la parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con Sistema telefónico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sin Audioconferencia) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con Audioconferencia) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Empresa Básico | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Empresa Estándar | O365_BUSINESS_PREMIUM|
| Microsoft 365 Empresa | SPB|
| Microsoft Business Voice (Canadá)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Reino Unido) | BUSINESS_VOICE  |
| Microsoft Business Voice (Estados Unidos) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (sin plan de llamadas) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (sin plan de llamadas) para Estados Unidos| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconferencia | MCOMEETADV | 
| Pago por minuto de Audioconferencia (pago por minuto)</br>*Requiere que los créditos de comunicaciones se configuren y habiliten.* | MCOMEETACPEA |
| Sistema telefónico | MCOEV |
| Plan de llamadas nacionales e internacionales | MCOPSTN2 |
| Plan de llamadas nacionales (3000 minutos por usuario/mes para EE. UU./PR/CA, 1200 minutos por usuario y mes para los países de la UE) | MCOPSTN1 |
| Plan de llamadas nacionales (120 minutos por usuario y mes para cada país) </br>*Este plan no está disponible en Estados Unidos.* | MCOPSTN5 |
| Plan de llamadas nacionales (240 minutos por usuario y mes para cada país) </br>*Este plan no está disponible en Estados Unidos.* | MCOPSTN6 |
| Créditos de comunicaciones | MCOPSTNPP |

## <a name="related-topics"></a>Temas relacionados

- [Licencias complementarias de Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Gestionar acceso de los usuarios a Microsoft Teams](../user-access.md)
- [Ver licencias y servicios con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referencia de SKU para educación](../sku-reference-edu.md)