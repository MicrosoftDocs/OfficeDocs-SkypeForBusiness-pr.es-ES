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
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785153"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Implementar la aplicación padres en Microsoft Teams

La aplicación Padres ayuda Teams los profesores a conectarse e interactuar de forma segura con los padres y tutores de los alumnos en sus clases mediante un chat que se ampliará en toda la organización del profesorado. Todos los datos de padres y tutores se aprovisionan con School Data Sync, lo que permite a los profesores y al personal de IT configurar las cosas sin problemas.

## <a name="requirements"></a>Requirements

### <a name="school-data-sync"></a>School Data Sync

- Necesita School Data Sync (SDS) para rellenar la información de contacto relacionada de **cada** alumno.
  - [Implementar SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Si necesita ayuda para configurar SDS y habilitar contactos primarios en su inquilino, póngase en contacto con el equipo de éxito del cliente de EDU:
  - Completar el proceso de RFA en [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrir un vale en soporte [técnico.](https://aka.ms/sdssupport)

### <a name="teams-admins-center---policies"></a>Teams Centro de administración: directivas

- El propietario de la clase debe tener el chat habilitado
- El propietario de la clase debe tener **habilitado el acceso externo Teams cuentas no administradas por una organización.** 
  - Esta configuración se puede encontrar en Usuarios > acceso externo para el nivel de espacio empresarial, o si desea habilitar para un determinado conjunto de usuarios, vea powershell a continuación.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Habilitar el chat federado por usuario

1. Instale la versión Microsoft Teams vista previa del módulo de PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Con credenciales que tienen privilegios de administrador, ejecute el siguiente comando en una ventana de comandos:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

La configuración de directiva que permite Teams el acceso externo del consumidor en el nivel de usuario (EnableTeamsConsumerAccess) está habilitada de forma predeterminada para todas las directivas de acceso externo de nivel de usuario. Tanto la configuración de nivel de inquilino (AllowTeamsConsumer) como la configuración de directiva de nivel de usuario deben estar habilitadas para que un usuario tenga acceso externo Teams consumidor. Teams Si no desea que todos los usuarios de su espacio empresarial tengan un acceso externo de consumidor habilitado, debe actualizar las directivas de acceso externo a nivel de usuario asignadas a los usuarios antes de habilitar la configuración de nivel de inquilino.

Si necesita comprobar qué directivas de acceso externo a nivel de usuario existen y a quién están asignadas, puede seguir estos pasos:
    
3. Compruebe qué directivas de acceso externo a nivel de usuario existen.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Para cada directiva que no sea la directiva "Global", compruebe qué usuarios tienen asignada la directiva. Nota: los usuarios que no tengan asignada una directiva específica volverán a la directiva "Global".

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Más opciones de PowerShell

Puesto que todas las directivas de acceso externo a nivel de usuario tienen EnableTeamsConsumerAccess establecido en true de forma predeterminada, si desea actualizar cualquiera de estas directivas para ajustar la configuración EnableTeamsConsumerAccess, puede crear nuevas directivas de acceso externo con la configuración ajustada, o reasignar usuarios a directivas nuevas o existentes, a través del siguiente PowerShell:

- Crear una nueva directiva de acceso externo (esto crea una nueva directiva de acceso externo y define la configuración): [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar una directiva de acceso externo existente (modifica la configuración de una directiva de acceso externo existente, incluida la directiva [global):Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Los siguientes valores predeterminados de suscripción no se pueden modificar: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Si necesita cambiar la configuración de directiva para los usuarios que tienen asignadas estas directivas, asigne diferentes directivas con la configuración correcta a estos usuarios.

- Asignar una directiva de acceso externo a un solo usuario: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Asignar una directiva a un conjunto de usuarios: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Una vez que se sienta seguro de que las directivas de acceso externo a nivel de usuario están configuradas correctamente para todos los usuarios Teams, puede habilitar la configuración de nivel de inquilino que controla el acceso externo de un consumidor para el inquilino con el siguiente cmdlet:

- Establecer la configuración de federación para el inquilino (Establecer AllowTeamsConsumer en true): [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Deshabilitar la aplicación Padres

La aplicación Padres está habilitada de forma predeterminada, por lo que todos los propietarios de clase verán la aplicación en su equipo de clase. La aplicación se puede deshabilitar en el nivel de inquilino con [Permitir y](manage-apps.md#allow-and-block-apps) bloquear aplicaciones en el Microsoft Teams de administración. Si está deshabilitado a nivel de inquilino, se bloqueará para todos los usuarios, incluso si el permiso de nivel de usuario está habilitado.

Esto también se puede deshabilitar en el nivel de usuario con [Administrar directivas de permisos de aplicación en Microsoft Teams]. (teams-app-permission-policies.md).

## <a name="more-information"></a>Más información

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Asignar la directiva a un usuario](/powershell/module/skype/grant-csexternalaccesspolicy)
