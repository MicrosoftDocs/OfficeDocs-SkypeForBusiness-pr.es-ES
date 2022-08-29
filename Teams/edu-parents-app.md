---
title: Administración configuración de Padres en Teams para Educación
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Artículo de Microsoft Teams en el que se documenta los requisitos previos y la configuración de padres en Teams para Educación.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37de74db112dcbd5466659b385f1bb94d7c134aa
ms.sourcegitcommit: 0592f9d2696fe8c840a4ed3e7f99e55ca0c9c3e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "67418629"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurar la conexión principal en Microsoft Teams para Educación

La conexión de padres en Teams para Educación ayuda a los profesores a conectarse e interactuar de forma segura con los padres y tutores de los alumnos en sus equipos de clase con Teams.

Este artículo proporciona orientación a profesionales de TI educativos sobre los requisitos y la configuración de la conexión principal.

## <a name="share-guardian-and-educator-resources"></a>Compartir recursos para tutores y formadores

Estos son algunos recursos que los administradores de TI pueden compartir con tutores y educadores sobre cómo pueden empezar a usar la conexión principal.

- Para obtener instrucciones sobre cómo configurar a los tutores, consulte [Conectarse con profesores en Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Para obtener instrucciones sobre cómo configurar a los formadores, consulte [Comunicarse con tutores en Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Ventajas de la conexión principal

La conexión de padres permite a los formadores y tutores chatear, enviar correo electrónico y llamar con Teams.

- Los formadores pueden iniciar chats con tutores.
  - Si el tutor no tiene una cuenta de consumidor de Teams o aún no se ha unido a Teams, recibirá el mensaje del formador junto con una invitación por correo electrónico para ir a Teams. Esto solo se aplica en los casos en los que no se han alcanzado los límites de invitación y el chat es un chat nuevo o un chat existente que se ha vuelto a introducir desde la conexión principal.
- Funciona con el chat supervisado. Para obtener más información, vea [Usar chats supervisados en Microsoft Teams](supervise-chats-edu.md).
  - De forma predeterminada, los tutores tienen permisos restringidos, por lo que no pueden chatear con los alumnos ni quitar usuarios de los chats.
  - El administrador de inquilinos puede cambiar esta configuración.
- Los formadores pueden hacer clic en el correo electrónico de un tutor para enviarles un correo electrónico con su cliente de correo electrónico nativo.
- Los profesores pueden hacer clic en el número de teléfono de un tutor para llamarlos en Teams.

> [!IMPORTANT]
> Para la funcionalidad de hacer clic para llamar en Teams, su inquilino necesita:
>
> - Funcionalidades de la central de centrales públicas (PBX).
> - Conexión a la RTC.
>
> Microsoft 365 A1 y los planes de A3 no incluyen capacidades de PBX ni conexión RTC. Puede comprar [licencias de complementos para cada uno de ellos](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
>
> Microsoft 365 A5 planes solo incluyen funcionalidades PBX con Teams Phone System. Seguirá necesitando [comprar un plan de llamadas de Teams o usar una solución de terceros](pstn-connectivity.md) para conectarse a números externos en la RTC.
>
> Para obtener más información sobre todas las opciones para obtener conectividad con RTC, vea [Opciones de conectividad de RTC](pstn-connectivity.md).
>
> Para obtener más información sobre las licencias de llamadas de Teams, consulte [Opciones de licencias de complementos de Teams](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## <a name="requirements"></a>Requirements

Debe usar Microsoft Graph o School Data Sync (SDS) para rellenar la información de contacto relacionada con los padres y tutores tutores de cada estudiante.

### <a name="graph-api"></a>API de Graph

Si ya usa el [SDK de Microsoft Graph PowerShell](/powershell/microsoftgraph/overview) para crear identidades de estudiantes, puede incluir fácilmente [el tipo de recurso RelatedContact](/graph/api/resources/relatedcontact).

### <a name="school-data-sync"></a>School Data Sync

Los datos de contacto de tutores de Teams se mantienen actualizados con SIS mediante School Data Sync (SDS), cuando SDS está configurado para sincronizarse periódicamente.

Si se quita a un tutor de los registros *de un alumno* , los chats existentes en los que participe con ellos contendrán una pancarta visible para el propietario del chat. Este banner hará que el propietario del chat conozca el cambio, pidiéndole que quite al tutor del chat. Microsoft no actualizará automáticamente la pertenencia al chat para quitar al tutor.

- Necesita School Data Sync (SDS) para rellenar la información de **contacto relacionada con** los padres y tutores tutores de cada estudiante.
  - [Implementar SDS](/schooldatasync/parents-and-guardians-in-sds)

- Si necesita ayuda para configurar SDS y rellenar **los contactos relacionados con** padres y tutores para los estudiantes de su inquilino, póngase en contacto con el equipo de EDU Customer Success mediante:
  - Completando el proceso de RFA en [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Abrir un vale en [Soporte técnico](https://aka.ms/sdssupport).

- Actualmente, SDS solo admite la ingestión de datos basada en CSV para contactos principales; sin embargo, puede usar [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) o [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) para todos los datos de lista y agregar contactos primarios mediante CSV.
  - Cree un segundo perfil de sincronización con el [formato de sincronización CSV de SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Extrae los dos [archivos principales](/schooldatasync/parent-contact-sync-file-format) rellenados con el resto de los archivos v1 vacíos (solo los encabezados).
    - User.csv
    - Guardianrelationship.csv
  - Para ver un conjunto de ejemplo de los archivos CSV v1, consulte los [archivos de GitHub de atributos requeridos mínimos](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Si desea automatizar la extracción de archivos CSV después de la sincronización inicial, lea nuestro [documento CSV File Sync Automation](/schooldatasync/csv-file-sync-automation).
  - Para obtener ayuda con la configuración de la sincronización de datos de SDS, póngase en contacto con [nuestro equipo de éxito del cliente](https://www.microsoft.com/fasttrack?rtc=1) o [abra una incidencia de soporte](https://edusupport.microsoft.com/support?product_id=data_sync) técnico.

### <a name="teams-admin-center-policies"></a>Directivas del centro de administración de Teams

- Los propietarios de equipos de clase deben tener activado el chat de Teams.
- Los propietarios de equipos de clase deben tener acceso externo con **las cuentas de Teams no administradas por una organización** activada.
  - Esto debe activarse en el nivel de inquilino y en el nivel de usuario. La configuración de nivel de inquilino se encuentra en **Usuarios > Acceso externo** en el Centro de administración de Teams. También se puede acceder a esta configuración a través de PowerShell. Solo se puede acceder a las directivas de acceso externo a nivel de usuario a través de PowerShell. Consulte los comandos de PowerShell siguientes para obtener más información.

#### <a name="parent-and-guardian-restrictions"></a>Restricciones para padres y tutores

Los padres y tutores se clasifican como *usuarios externos* en La conexión de padres, lo que significa que no tienen derechos de inquilino completos. Solo tienen acceso al chat o chats de los que forman parte y a los archivos, imágenes y otro contenido compartido en el chat.

Para los chats externos, tanto los usuarios internos como externos pueden agregar usuarios al chat. Para obtener más información sobre la experiencia de chat externo, consulte [Administrar reuniones y chats externos en Microsoft Teams](manage-external-access.md).

Además, los usuarios externos pueden ver la presencia (sin conexión, disponible, ocupado, etc.) de los usuarios de su organización, pero esto se puede desactivar con PowerShell para proteger la privacidad de los usuarios. En PowerShell, use [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) y establezca ``EnablePrivacyMode=true``.

A pesar de que los padres y tutores son usuarios externos, sus contribuciones a los chats son reconocibles. Obtenga información sobre cómo llevar a cabo una investigación de exhibición de documentos electrónicos en Teams en [Conduct an eDiscovery investigation of content in Microsoft Teams (Dirigir una investigación de exhibición de documentos electrónicos del contenido en Microsoft Teams](ediscovery-investigation.md)).

> [!IMPORTANT]
> Los administradores de TI deben educar a todos los propietarios de clase sobre los procedimientos recomendados para compartir información de los alumnos a través del chat, incluidos los riesgos para la privacidad de los alumnos.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Bloquear a un padre o tutor en un chat

Los profesores pueden bloquear a un tutor en el chat iniciado en conexión con los padres.

El propietario de la clase puede:

1. Abre la tarjeta de perfil del tutor, selecciona los puntos suspensivos y **Bloquear usuario**.
2. A continuación, quita al tutor del chat.

El usuario bloqueado no podrá iniciar chats adicionales con el propietario de la clase.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Permitir el acceso externo con cuentas de Teams no administradas por una organización

Para permitir que los profesores se comuniquen con padres y tutores en Teams, el administrador de TI del inquilino educativo debe actualizar las directivas del inquilino para permitir el acceso externo a las cuentas de Teams fuera del inquilino. Para obtener más información sobre la administración del acceso externo, vea [Administrar el acceso externo en Microsoft Teams](manage-external-access.md).

Estos son los pasos para activar el acceso externo para padres y tutores.

1. Instale la última versión preliminar del módulo PowerShell de Microsoft Teams.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Con credenciales que tengan privilegios de administrador, ejecute los siguientes comandos:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    La configuración de directiva que activa el acceso externo con cuentas de Teams no administradas por una organización en el nivel de usuario (`EnableTeamsConsumerAccess`) está activada de forma predeterminada para todas las directivas de acceso externo a nivel de usuario. Tanto la configuración de nivel de inquilino como la configuración de directiva a nivel de usuario deben estar activadas para que un usuario tenga acceso externo con cuentas de Teams no administradas por una organización. Si no quiere que todos los usuarios de su inquilino tengan este acceso activado, debe asegurarse de que la configuración de nivel de inquilino está desactivada, actualizar las directivas de acceso externo a nivel de usuario asignadas a los usuarios y, a continuación, activar la configuración de nivel de inquilino.

    Para comprobar qué directivas de acceso externo a nivel de usuario existen y a quién están asignadas, puede usar los siguientes pasos:

3. Compruebe que existen directivas de acceso externo a nivel de usuario.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Para cada directiva distinta de la directiva "Global", compruebe qué usuarios tienen asignada la directiva.

   > [!NOTE]
   > Todos los usuarios que no tengan asignada una directiva específica volverán a la directiva "Global". Todos los usuarios nuevos que se agreguen al inquilino tendrán asignada la directiva "Global".

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Puesto que todas las directivas de acceso externo a nivel de usuario se han `EnableTeamsConsumerAccess` establecido en true de forma predeterminada, si desea ajustar la `EnableTeamsConsumerAccess` configuración para usuarios específicos, puede crear o modificar directivas de acceso externo existentes con una configuración ajustada y/o reasignar usuarios a directivas nuevas o existentes mediante los siguientes cmdlets de PowerShell:

- Crear una nueva directiva de acceso externo: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizar una directiva de acceso externo existente (incluida la directiva "Global"): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> No se pueden modificar las siguientes directivas predeterminadas de suscripción: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. La directiva 'FederationAndPICDefault' se asignaba de forma predeterminada a todos los usuarios, pero a los nuevos usuarios se les asigna ahora la directiva "Global" de forma predeterminada. Si necesita cambiar la configuración de directiva para los usuarios que tienen asignadas estas directivas predeterminadas de suscripción, asigne diferentes directivas con la configuración correcta a estos usuarios.

- Asignar una directiva de acceso externo a un solo usuario: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Asignar una directiva a un conjunto de usuarios: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Una vez que las directivas de acceso externo a nivel de usuario se establecen correctamente para los usuarios de su espacio empresarial, puede activar la configuración de nivel de inquilino (`AllowTeamsConsumer`) para el inquilino mediante el siguiente cmdlet:

- Establecer las opciones de configuración de federación para su espacio empresarial: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Activar la aplicación Padres en el Centro de administración de Teams

La aplicación Padres está desactivada de forma predeterminada, por lo que los propietarios de equipos de clase no la verán en sus equipos de clase hasta que se permita a través del Centro de administración de Teams. La aplicación Padres está activada en el Centro de administración de Teams con [Permitir aplicaciones bloqueadas por desarrolladores](manage-apps.md#allow-the-apps-that-are-blocked-by-the-developers).

En cualquier momento, la aplicación se puede desactivar en el nivel de inquilino mediante [Permitir y bloquear aplicaciones](manage-apps.md#allow-and-block-apps) en el Centro de administración de Teams. Si está desactivada en el nivel de inquilino, se bloqueará para todos los usuarios, incluso si los permisos a nivel de usuario están activados.

La aplicación Padres también se puede desactivar en el nivel de usuario mediante las [directivas de permisos administrar aplicaciones en Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Más información

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
