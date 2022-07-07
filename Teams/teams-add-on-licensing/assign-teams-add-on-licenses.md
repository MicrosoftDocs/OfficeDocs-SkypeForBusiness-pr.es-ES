---
title: Asignar licencias de complementos de Teams a usuarios
author: SerdarSoysal
ms.author: serdars
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
description: Obtenga información sobre cómo asignar licencias de complementos de Teams a los usuarios para funcionalidades como Audioconferencia, Sistema telefónico y Planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fca8eb5acac30210e67068f9a2b1eb8dfdce3cb
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682499"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Asignar licencias de complementos de Teams a usuarios

Las licencias de complementos son licencias para funcionalidades específicas de Teams, como Audioconferencia, Sistema telefónico y Planes de llamadas. En este artículo se describe cómo asignar licencias de complemento a usuarios individuales y grandes conjuntos de usuarios en masa.

> [!NOTE]
> Consulte [Licencias de complementos de Teams](./microsoft-teams-add-on-licensing.md) para las funcionalidades de Teams que están disponibles con licencias de complementos. También encontrará información sobre las licencias que necesita comprar y cómo comprarlas, en función de su plan. Después de decidir qué capacidades desea para sus usuarios, asígneles las licencias.

Puede usar la Centro de administración de Microsoft 365 o PowerShell para asignar licencias a usuarios de su organización. Debe ser administrador global o administrador de administración de usuarios para administrar las licencias.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Lo que debe saber antes de asignar licencias de sistema telefónico, plan de llamadas y créditos de comunicación

Antes de empezar, revise los siguientes requisitos:

- Si usa la conectividad de red telefónica conmutada (RTC) local para los usuarios, solo necesita asignar una licencia de Teléfono Teams Estándar. NO asigne una licencia de Plan de llamadas.

- Después de asignar un plan de llamadas de Microsoft a un usuario, pueden pasar hasta 24 horas antes de que vea el teclado de marcado en su cliente de Teams. Si el teclado de marcado no se muestra en 24 horas, compruebe la [configuración del teclado de marcado](../dial-pad-configuration.md). Si es necesario, también puede [ponerse en contacto con el soporte técnico](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Recibirá un mensaje de error si no ha comprado el número correcto de licencias. Si necesita comprar más licencias de Plan de llamadas, elija la opción para comprar más.

- Incluso si a los usuarios se les asignan licencias Enterprise E5, aún debe conectarlos a la RTC. Tiene varias [opciones de conectividad con RTC](../pstn-connectivity.md), como Planes de Llamada de Microsoft Teams, Enrutamiento directo o Conexión de operadores.

- Después de asignar licencias de planes de llamadas o créditos de comunicación a los usuarios, tendrá que obtener números de teléfono para su organización y asignarlos a los usuarios. Para obtener instrucciones detalladas, consulte [Configurar planes de llamadas](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Usar el Centro de administración de Microsoft 365

Use la Centro de administración de Microsoft 365 para asignar licencias a usuarios individuales o a pequeños conjuntos de usuarios a la vez.

Las licencias se asignan en la página **Licencias** (para un máximo de 20 usuarios a la vez) o en la página **Usuarios activos** (para un máximo de 40 usuarios a la vez). El método que elija dependerá de si desea administrar licencias de producto para usuarios específicos o administrar licencias de usuario de productos específicos.

Para obtener instrucciones detalladas, consulte [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

Si necesita asignar licencias para un gran número de usuarios, como cientos o miles de usuarios, use Powershell o [licencias basadas en grupos en Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>Con PowerShell

Use PowerShell para asignar licencias a usuarios en masa. Para obtener más información, consulte [Asignar licencias a cuentas de usuario con PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Script de ejemplo

Este es un ejemplo de cómo usar un script para asignar licencias a los usuarios.

1. Instale la versión de 64 bits del [Asistente para el inicio de sesión de Microsoft Online Services para profesionales de TI RTW](/collaborate/connect-redirect?DownloadID=59185).
2. Instala el módulo Microsoft Azure Active Directory para Windows PowerShell:
    1. Abra un símbolo del sistema con privilegios elevados Windows PowerShell (ejecute Windows PowerShell como administrador).
    2. Ejecute el siguiente comando:
        ```powershell
        Install-Module MSOnline
        ```
    3. Si se le pide que instale el proveedor de NuGet, escriba **Y** y, después, presione Entrar.
    4. Si se le pide que instale el módulo desde PSGallery, escriba **Y** y, después, presione Entrar.
3. En la Windows PowerShell símbolo del sistema, ejecute el siguiente script para asignar licencias a los usuarios, donde \<CompanyName:License> se encuentra el nombre de la organización y el identificador de la licencia que desea asignar. Por ejemplo, litwareinc:MCOMEETADV.

    El identificador es diferente del nombre descriptivo de la licencia. Por ejemplo, el identificador de Audioconferencia es MCOMEETADV. Para obtener más información, consulte [Nombres de productos e identificadores de SKU para licencias](#product-names-and-sku-identifiers-for-licensing).

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

    Por ejemplo, para asignar licencias de Microsoft 365 Enterprise E1 y Audioconferencia, use la siguiente sintaxis en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Para asignar una licencia de Teams Phone con plan de llamadas, use la siguiente sintaxis en el script:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Nombres de productos e identificadores de SKU para licencias

Esta es una lista parcial de nombres de productos y sus correspondientes nombres de partes SKU a los que puede hacer referencia al usar PowerShell para administrar licencias en Teams.

Para obtener más información, consulte [Ver licencias y servicios con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nombres de productos e identificadores de plan de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) y [Referencia de SKU para educación](../sku-reference-edu.md).

| Nombre del producto| Nombre de la parte SKU |
|--------------|---------------|
| Microsoft Enterprise E5 (con sistema telefónico) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sin Audioconferencia) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (con Audioconferencia) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Empresa Básico | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Empresa Estándar | O365_BUSINESS_PREMIUM|
| Microsoft 365 Empresa | SPB|
| Audioconferencia | MCOMEETADV |
| Audioconferencia, pago por minuto (pagar sobre la marcha) Requiere que los créditos de comunicaciones se configuren y habiliten.* | MCOMEETACPEA |
| Teléfono Teams Estándar | MCOEV |
| Teléfono de Teams con plan de llamadas | MCOTEAMS_ESSENTIALS |
| Plan de llamadas internacionales | MCOPSTN2 |
| Plan de llamadas nacionales (3000 minutos por usuario/mes para EE. UU./PR/CA, 1.200 minutos por usuario y mes para países de la UE) | MCOPSTN1 |
| Plan de llamadas nacionales (120 minutos por usuario/mes para cada país) </br>*Este plan no está disponible en la Estados Unidos.* | MCOPSTN5 |
| Plan de llamadas nacionales (240 minutos por usuario y mes para cada país) </br>*Este plan no está disponible en la Estados Unidos.* | MCOPSTN6 |
| Créditos de comunicaciones | MCOPSTNPP |

## <a name="related-content"></a>Contenido relacionado

- [Licencias complementarias de Microsoft Teams](./microsoft-teams-add-on-licensing.md)
- [Gestionar acceso de los usuarios a Microsoft Teams](../user-access.md)
- [Ver licencias y servicios con PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Referencia de SKU para educación](../sku-reference-edu.md)
