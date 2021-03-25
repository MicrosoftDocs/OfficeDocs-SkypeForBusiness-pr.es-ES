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
description: Obtenga información sobre cómo asignar licencias de complementos de Teams a los usuarios para características como audioconferencias, sistema telefónico y planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116938"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Asignar licencias de complementos de Teams a los usuarios

Las licencias de complementos son licencias para características específicas de Teams, como audioconferencias, sistemas telefónicos y planes de llamadas. En este artículo se describe cómo asignar licencias de complementos a usuarios individuales y a grandes conjuntos de usuarios en masa.

> [!NOTE]
> Consulte [Licencias de complementos de Teams](./microsoft-teams-add-on-licensing.md) para características de Teams que están disponibles con licencias de complementos. También encontrará información sobre qué licencias necesita comprar y cómo comprarlas (según su plan), para que los usuarios puedan obtener características como Audioconferencia, números gratuitos y la capacidad de llamar a números de teléfono fuera de su organización. Después de decidir qué características desea para los usuarios, asígneles las licencias.

Puede usar el Centro de administración de Microsoft 365 o PowerShell para asignar licencias a usuarios de su organización. Debe ser administrador global o administrador de administración de usuarios para administrar licencias.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Lo que necesita saber antes de asignar licencias de Sistema telefónico, Plan de llamadas y Créditos de comunicación

Antes de empezar, revise los siguientes requisitos:

- Si usa la conectividad local de red telefónica conmutada (RTC) para los usuarios híbridos, solo tiene que asignar una licencia del sistema telefónico. No asigne una licencia del plan de llamadas.

- Debido a la latencia entre Microsoft 365 y Microsoft Teams, puede tardar hasta 24 horas en asignar un plan de llamadas a un usuario después de asignar una licencia. Si al usuario no se le asigna un plan de llamadas después de 24 horas, póngase en contacto con el soporte técnico para productos [empresariales: ayuda para administradores.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Recibe un mensaje de error si no ha comprado el número correcto de licencias. Si necesita comprar más licencias del Plan de llamadas, elija la opción para comprar más.

- Incluso si a los usuarios se les asignan licencias [](../what-are-communications-credits.md) de Enterprise E5, aún debe asignarles licencias de créditos de comunicaciones si quieren realizar o recibir llamadas desde la RTC.

- Después de asignar licencias de planes de llamadas o créditos de comunicación a los usuarios, tendrá que obtener números de teléfono para su organización y, a continuación, asignar esos números a los usuarios. Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](../set-up-calling-plans.md)

## <a name="using-the-microsoft-365-admin-center"></a>Usar el Centro de administración de Microsoft 365

Use el Centro de administración de Microsoft 365 para asignar licencias a usuarios individuales o conjuntos pequeños de usuarios a la vez. Asigne licencias en la página **Licencias** (para un máximo de 20 usuarios a la vez) o en la **página Usuarios activos.** El método que elija depende de si desea administrar licencias de productos para usuarios específicos o administrar licencias de usuario para productos específicos.

Para obtener instrucciones paso a paso, vea [Asignar licencias a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)

Si necesita asignar licencias para un gran número de usuarios, como cientos o miles de usuarios, use Powershell o licencias basadas en grupos en [Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>Con PowerShell

Use PowerShell para asignar licencias a usuarios en masa.  Para obtener más información, vea [Asignar licencias a cuentas de usuario con PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>Script de ejemplo

Este es un ejemplo de cómo usar un script para asignar licencias a los usuarios.

1. Instale la versión de 64 bits del asistente Microsoft Online Services inicio de sesión para profesionales de [TI RTW.](/collaborate/connect-redirect?DownloadID=59185)
2. Instale el módulo Microsoft Azure Active Directory para Windows PowerShell:
    1. Abra un símbolo Windows PowerShell símbolo del sistema (ejecute Windows PowerShell como administrador).
    2. Ejecute el siguiente comando:
        ```powershell
        Install-Module MSOnline
        ```
    3. Si se le solicita que instale el proveedor de NuGet, escriba **Y** y, después, presione Entrar.
    4. Si se le solicita que instale el módulo desde PSGallery, escriba **Y** y, después, presione Entrar.
3. En el Windows PowerShell de comandos, ejecute el siguiente script para asignar licencias a los usuarios, donde se encuentra el nombre de su organización y el identificador de la licencia que \<CompanyName:License> desea asignar. Por ejemplo, litwareinc:MCOMEETADV.

    El identificador es diferente del nombre descriptivo de la licencia. Por ejemplo, el identificador de audioconferencia es MCOMEETADV. Para obtener más información, vea [Nombres de producto e identificadores de SKU para licencias.](#product-names-and-sku-identifiers-for-licensing)

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

    Por ejemplo, para asignar licencias de Microsoft 365 Enterprise 1 y audioconferencias, use la sintaxis siguiente en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para asignar una licencia de Microsoft Business Voice (sin plan de llamadas), use la sintaxis siguiente en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nombres de producto e identificadores de SKU para licencias

Esta es una lista parcial de nombres de producto y sus correspondientes nombres de partes de SKU que puede usar como referencia cuando use PowerShell para administrar licencias en Teams.

Para obtener más información, vea Ver licencias y servicios con [PowerShell,](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)Nombres de productos e identificadores de [plan](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)de servicio para licencias y Referencia [de SKU de educación.](../sku-reference-edu.md)

| Nombre del producto| Nombre de la parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con sistema telefónico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sin conferencias de audio) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con audioconferencias) | ENTERPRISEPREMIUM |
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
| Pago por minuto de audioconferencia (pagar a medida que vaya)</br>*Requiere que los créditos de comunicaciones se configuren y habiliten.* | MCOMEETACPEA |
| Sistema telefónico | MCOEV |
| Plan de llamadas nacionales e internacionales | MCOPSTN2 |
| Plan de llamadas nacionales (3000 minutos por usuario/mes para EE.UU./PR/CA, 1.200 minutos por usuario/mes para países de la UE) | MCOPSTN1 |
| Plan de llamadas nacionales (120 minutos por usuario/mes para cada país) </br>*Este plan no está disponible en Estados Unidos.* | MCOPSTN5 |
| Plan de llamadas nacionales (240 minutos por usuario/mes para cada país) </br>*Este plan no está disponible en Estados Unidos.* | MCOPSTN6 |
| Créditos de comunicaciones | MCOPSTNPP |

## <a name="related-topics"></a>Temas relacionados

- [Licencias complementarias de Microsoft Teams](./microsoft-teams-add-on-licensing.md)
- [Gestionar acceso de los usuarios a Microsoft Teams](../user-access.md)
- [Ver licencias y servicios con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referencia de SKU de educación](../sku-reference-edu.md)