---
title: Configuración de administrador de Padres en Teams para Educación
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams artículo que documenta los requisitos previos y la configuración de Padres en Teams para Educación.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d1b84fc78558fcbb1945cbc56b311b5e06234a5
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062534"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurar la conexión principal en Microsoft Teams para Educación

La conexión de padres en Teams para Educación ayuda a los profesores a conectarse e interactuar de forma segura con los padres y tutores de los alumnos en sus equipos de clase Teams mediante un chat, que se ampliará en toda la organización del educador. Todos los datos de padres y tutores se aprovisionan con School Data Sync, lo que permite al personal de IT configurar las cosas sin problemas.

Una vez que los educadores y tutores estén configurados, pueden chatear entre ellos Teams chat. 

Para obtener instrucciones sobre cómo conectar a los padres y tutores con los educadores, [consulte Conectar con los educadores en Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

Para obtener instrucciones sobre cómo configurar a los educadores para comunicarse con padres y tutores, vea Comunicarse con [tutores en Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

Los padres también funcionan con el chat supervisado. Los padres y tutores no tendrán permisos completos de Teams, lo que significa que no pueden iniciar conversaciones con los alumnos ni quitar los usuarios con permisos completos (como los profesores) de los chats. Para obtener más información sobre el chat supervisado, vea [Usar chats supervisados en Microsoft Teams](supervise-chats-edu.md).

## <a name="requirements"></a>Requirements

### <a name="school-data-sync"></a>School Data Sync

- Necesita School Data Sync (SDS) para rellenar la información de contacto relacionada con los padres y tutores **de cada** alumno.
  - [Implementar SDS](/schooldatasync/parents-and-guardians-in-sds)

- Si necesita ayuda para configurar SDS y rellenar contactos relacionados con padres y tutores  para los alumnos de su inquilino, póngase en contacto con el equipo de éxito del cliente de EDU:
  - Completar el proceso de RFA en [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrir un vale en soporte [técnico](https://aka.ms/sdssupport).

- Actualmente, SDS solo admite la ingestión de datos basados en CSV para contactos primarios; sin embargo, puede usar [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) o [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) para todos los datos de lista, y simplemente agregar contactos primarios con CSV.
  - Cree un segundo perfil de sincronización con el formato [de sincronización CSV de SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Extraiga los dos archivos primarios [rellenados](/schooldatasync/parent-contact-sync-file-format) con el resto de los archivos v1 vacíos (solo los encabezados).
    - User.csv
    - Guardianrelationship.csv
  - Para ver un conjunto de ejemplo de los archivos CSV v1, vea Los atributos mínimos [obligatorios GitHub archivos](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Si desea automatizar la extracción de los archivos CSV después de la sincronización inicial, lea nuestro documento [Automatización de sincronización de archivos CSV](/schooldatasync/csv-file-sync-automation).
  - Para obtener ayuda con la configuración de la sincronización de datos de SDS, consulte a nuestro equipo de éxito de [clientes](https://www.microsoft.com/fasttrack?rtc=1) o [abra un vale de soporte técnico](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams de administración : directivas

- Los propietarios de equipos de clase deben tener Teams de chat activado.
- Los propietarios de equipos de clase deben tener **acceso externo Teams cuentas no administradas por una organización** activada.
  - Esto debe estar activado en el nivel de inquilino y en el nivel de usuario. La configuración de nivel de inquilino se puede encontrar en **Usuarios > acceso externo** en el Centro Teams administración. También se puede acceder a esta configuración a través de PowerShell. Solo se puede acceder a las directivas de acceso externo a nivel de usuario a través de PowerShell. Vea los comandos de PowerShell siguientes para obtener más instrucciones.

> [!NOTE]
>Los padres y tutores se clasifican como usuarios externos en la característica Padres, lo que significa que no tienen derechos de inquilino completos. Solo tienen acceso al chat o chats a los que se agregan, así como a archivos, imágenes y otros contenidos compartidos en el chat.
>
>Además, los usuarios externos pueden ver la presencia (sin conexión, disponible, ocupado, etc.) de los usuarios de su organización, pero esto se puede desactivar con PowerShell para proteger la privacidad de los usuarios. En PowerShell, use [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) y set ``EnablePrivacyMode=true``.
>
>Aunque los padres y tutores son usuarios externos, sus contribuciones a los chats son reconocibles. Obtenga información sobre cómo realizar una Teams de exhibición de documentos electrónicos mediante la lectura Llevar a cabo una investigación de exhibición de documentos electrónicos de contenido [en Microsoft Teams](ediscovery-investigation.md).

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Permitir el acceso externo con Teams cuentas no administradas por una organización

Para permitir que los educadores se comuniquen con los padres y tutores en Teams, el administrador de TI del inquilino educativo debe actualizar las directivas del inquilino para permitir el acceso externo Teams cuentas fuera del inquilino. Para obtener más información sobre cómo administrar el acceso externo, vea [Administrar el acceso externo en Microsoft Teams](manage-external-access.md).

Estos son los pasos para activar el acceso externo para padres y tutores.

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

    La configuración de directiva que activa el acceso externo con Teams cuentas no administradas por una organización en el nivel de usuario (`EnableTeamsConsumerAccess`) está activada de forma predeterminada para todas las directivas de acceso externo de nivel de usuario. Tanto la configuración de nivel de inquilino como la configuración de directiva de nivel de usuario deben estar activadas para que un usuario tenga acceso externo con Teams cuentas no administradas por una organización. Si no desea que todos los usuarios de su inquilino tengan activado este acceso, asegúrese de que la configuración de nivel de inquilino está desactivada, actualice las directivas de acceso externo a nivel de usuario asignadas a los usuarios y, después, active la configuración de nivel de inquilino.

    Para comprobar qué directivas de acceso externo a nivel de usuario existen y a quién están asignadas, puede seguir estos pasos:

3. Compruebe que existen directivas de acceso externo a nivel de usuario.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Para cada directiva que no sea la directiva "Global", compruebe qué usuarios tienen asignada la directiva.

   > [!NOTE]
   > Los usuarios que no tengan asignada una directiva específica volverán a la directiva "Global". Los nuevos usuarios que se agregan al inquilino tendrán asignada la directiva "Global".

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess` Puesto que todas las directivas de acceso externo a nivel de usuario se han establecido en true de forma predeterminada, `EnableTeamsConsumerAccess` si desea ajustar la configuración para usuarios específicos, puede crear o modificar directivas de acceso externo existentes con configuración ajustada y/o reasignar usuarios a directivas nuevas o existentes con los siguientes cmdlets de PowerShell:

- Crear una nueva directiva de acceso externo: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar una directiva de acceso externo existente (incluida la directiva "Global"): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Las siguientes directivas predeterminadas de suscripción no se pueden modificar: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". La directiva "FederationAndPICDefault" solía asignarse a todos los usuarios de forma predeterminada, pero ahora se asigna a los nuevos usuarios la directiva "Global" de forma predeterminada. Si necesita cambiar la configuración de directiva para los usuarios que tienen asignadas estas directivas predeterminadas de suscripción, asigne diferentes directivas con la configuración correcta a estos usuarios.

- Asignar una directiva de acceso externo a un solo usuario: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Asignar una directiva a un conjunto de usuarios: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Una vez que las directivas de acceso externo de nivel de usuario se establezcan correctamente para los usuarios de su espacio empresarial, puede activar la configuración de nivel de inquilino (`AllowTeamsConsumer`) para el inquilino con el siguiente cmdlet:

- Establecer la configuración de federación para el inquilino: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Activar la aplicación Padres en el Centro Teams administración

La aplicación Padres está desactivada de forma predeterminada, por lo que los propietarios de equipos de clase no la verán en sus equipos de clase hasta que se permita a través del centro de administración Teams clase. La aplicación Padres está activada en el centro Teams de administración mediante [Permitir aplicaciones bloqueadas por los editores](manage-apps.md#apps-blocked-by-publishers).

En cualquier momento, la aplicación se puede desactivar en el nivel de inquilino mediante Permitir y bloquear [aplicaciones](manage-apps.md#allow-and-block-apps) en el Teams de administración. Si está desactivada en el nivel de inquilino, se bloqueará para todos los usuarios, incluso si los permisos de nivel de usuario están activados.

La aplicación Padres también se puede desactivar en el nivel de usuario mediante Administrar directivas de permisos [de aplicación en Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Más información

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
