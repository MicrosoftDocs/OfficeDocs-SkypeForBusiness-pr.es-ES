---
title: Configuración de administrador para la aplicación Microsoft EDU Parents en Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams artículo de EDU que documenta los requisitos previos y la configuración de la aplicación Padres.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d875c6cd753e4c2e97477b3a3a88e0f071b5cbe
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2021
ms.locfileid: "61322992"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Implementar la aplicación Padres en Microsoft Teams

La aplicación Padres ayuda Teams los profesores a conectarse e interactuar de forma segura con los padres y tutores de los alumnos en sus equipos de clase mediante un chat, que se ampliará en toda la organización del educador. Todos los datos de padres y tutores se aprovisionan con School Data Sync, lo que permite al personal de IT configurar las cosas sin problemas.

## <a name="requirements"></a>Requirements

### <a name="school-data-sync"></a>School Data Sync

- Necesita School Data Sync (SDS) para rellenar la información de contacto relacionada con los padres y tutores **de cada** alumno.
  - [Implementar SDS](/schooldatasync/parent-contact-sync)

- Si necesita ayuda para configurar SDS y rellenar  contactos relacionados con padres y tutores para los alumnos de su inquilino, póngase en contacto con el equipo de éxito del cliente de EDU:
  - Completar el proceso de RFA en [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrir un vale en soporte [técnico.](https://aka.ms/sdssupport)

### <a name="teams-admin-center---policies"></a>Teams de administración: directivas

- Los propietarios de equipos de clase deben tener Teams de chat habilitado.
- Los propietarios de equipos de clase deben tener acceso externo **Teams cuentas no administradas por una organización** habilitada.
  - Esto debe estar habilitado en el nivel de inquilino y en el nivel de usuario. La configuración de nivel de inquilino se puede encontrar en **Usuarios > acceso externo** en el Centro Teams administración. También se puede acceder a esta configuración a través de PowerShell. Solo se puede acceder a las directivas de acceso externo a nivel de usuario a través de PowerShell. Vea los comandos de PowerShell siguientes para obtener más instrucciones.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Habilitar el acceso externo con Teams cuentas no administradas por una organización

1. Instale la versión Microsoft Teams vista previa del módulo de PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Con credenciales que tienen privilegios de administrador, ejecute los siguientes comandos:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

La configuración de directiva que habilita el acceso externo con Teams cuentas no administradas por una organización en el nivel de usuario ( ) está habilitada de forma predeterminada para todas las directivas de acceso externo `EnableTeamsConsumerAccess` de nivel de usuario. Tanto la configuración de nivel de inquilino como la configuración de directiva de nivel de usuario deben estar habilitadas para que un usuario tenga acceso externo con Teams cuentas no administradas por una organización habilitada. Si no desea que todos los usuarios de su espacio empresarial tengan habilitado este acceso, debe asegurarse de que la configuración de nivel de inquilino está deshabilitada, actualizar las directivas de acceso externo a nivel de usuario asignadas a los usuarios y, a continuación, habilitar la configuración de nivel de inquilino.

Para comprobar qué directivas de acceso externo a nivel de usuario existen y a quién están asignadas, puede seguir estos pasos:
    
3. Compruebe qué directivas de acceso externo a nivel de usuario existen.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Para cada directiva que no sea la directiva "Global", compruebe qué usuarios tienen asignada la directiva.

   > [!NOTE]
   > Los usuarios que no tengan asignada una directiva específica volverán a la directiva "Global". Los nuevos usuarios que se agregan al inquilino tendrán asignada la directiva "Global".

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Puesto que todas las directivas de acceso externo a nivel de usuario se han establecido en true de forma predeterminada, si desea ajustar la configuración para usuarios específicos, puede crear o modificar directivas de acceso externo existentes con configuración ajustada y/o reasignar usuarios a directivas nuevas o existentes con los siguientes cmdlets de `EnableTeamsConsumerAccess` `EnableTeamsConsumerAccess` PowerShell:

- Crear una nueva directiva de acceso externo: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar una directiva de acceso externo existente (incluida la directiva "Global"): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Las siguientes directivas predeterminadas de suscripción no se pueden modificar: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". La directiva "FederationAndPICDefault" solía asignarse a todos los usuarios de forma predeterminada, pero ahora se asigna a los nuevos usuarios la directiva "Global" de forma predeterminada. Si necesita cambiar la configuración de directiva para los usuarios que tienen asignadas estas directivas predeterminadas de suscripción, asigne diferentes directivas con la configuración correcta a estos usuarios.

- Asignar una directiva de acceso externo a un solo usuario: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Asignar una directiva a un conjunto de usuarios: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Una vez que las directivas de acceso externo de nivel de usuario se establezcan correctamente para los usuarios de su espacio empresarial, puede habilitar la configuración de nivel de inquilino ( ) para el inquilino con `AllowTeamsConsumer` el siguiente cmdlet:

- Establecer la configuración de federación para el inquilino: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="enabling-the-parents-app"></a>Habilitar la aplicación Padres

La aplicación Padres está deshabilitada de forma predeterminada, por lo que los propietarios de los equipos de clase no verán la aplicación en sus equipos de clase hasta que se permita la aplicación a través del centro de administración Teams clase. La aplicación se puede permitir a través del centro Teams de administración mediante [Permitir aplicaciones bloqueadas por los editores.](manage-apps.md#apps-blocked-by-publishers)

En cualquier momento, la aplicación se puede deshabilitar en el nivel de inquilino con Permitir y bloquear [aplicaciones](manage-apps.md#allow-and-block-apps) en el Teams de administración. Si la aplicación está deshabilitada en el nivel de inquilino, se bloqueará para todos los usuarios, incluso si los permisos de nivel de usuario están habilitados.

La aplicación también se puede deshabilitar en el nivel de usuario mediante Administrar directivas de permisos [de aplicación en Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Más información

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
