---
title: Configuración de administrador para la aplicación EDU Microsoft Parents
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams de documentos de artículos edu y configuración de PowerShell para la aplicación Padres.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475917"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Implementar la aplicación padres en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Habilitar la aplicación padres en Microsoft Teams es un proceso sencillo para los administradores, que ofrece un método seguro para que los profesores se comuniquen con los alumnos y sus contactos que permanecen en el espacio empresarial y que se escalarán en toda la organización del profesor.

## <a name="requirements"></a>Requirements

- SDS (School data sync): deberá cargar contactos relacionados asociados con los alumnos en SDS con la opción CSV. Consulte [Configurar CSV para SDS](/schooldatasync/set-up-your-sds-flow) y [Actualizar relatedContacts](/graph/api/relatedcontact-update) para obtener más información.
- En Teams de administración, el propietario de la clase debe tener el **chat** habilitado y el **chat** federado con Teams cuentas no administración **por parte de una organización.**

Si necesita habilitar el chat federado por usuario, los pasos se indican a continuación.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Habilitar el chat federado por usuario

1. Instale la versión Microsoft Teams vista previa del módulo de PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. Ejecutar en una ventana de comandos con credenciales con privilegios de administrador.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. Desactive y active la configuración global de nivel de usuario o grupo o inquilino.

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > Al ejecutar este PowerShell, los cambios pueden tardar una hora o más en completarse.
    
## <a name="more-information"></a>Más información

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Asignar la directiva a un usuario](/powershell/module/skype/grant-csexternalaccesspolicy)
