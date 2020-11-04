---
title: Chat, equipos, canales y aplicaciones en Microsoft Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Contiene instrucciones paso a paso para configurar los ajustes de Teams para el chat, los equipos, las aplicaciones y los canales en Microsoft Teams.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: ac9c1d78c7960ebadfc590b87a6007286bc43209
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878534"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, equipos, canales y aplicaciones en Microsoft Teams

Teams proporciona una experiencia de colaboración excelente para su organización y la configuración predeterminada parece funcionar para la mayoría de organizaciones. Este artículo le ayudará a decidir si cambiar alguna opción de la configuración predeterminada, en función del perfil y los requisitos empresariales de su organización, después, le guiará con cada cambio. Hemos dividido las opciones en dos grupos, comenzando por el conjunto principal de [cambios que es más probable que realice](#core-deployment-decisions). El segundo grupo incluye las [opciones adicionales](#additional-deployment-decisions) que puede que quiera configurar, según las necesidades de su organización.

Para empezar, vea nuestro breve vídeo sobre el chat, los equipos y los canales de Teams (4:30 minutos):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

*Novedades de noviembre de 2019*
 - Ahora puede [Usar el Asesor de Teams (versión preliminar) para ayudar a implementar Microsoft Teams](use-advisor-teams-roll-out.md). El Asesor de Teams (versión preliminar) le guiará a través de la implementación de Teams. Evalúa el entorno de Microsoft 365 u Office 365 e identifica las configuraciones más comunes que puede necesitar actualizar o modificar antes de poder implementar correctamente Teams.
 - [Conceptos básicos de Microsoft Teams para TI](https://aka.ms/MicrosoftTeamsforIT), incluidos vídeos breves (8-10 minutos) que muestran cómo implementar, configurar y administrar Teams.

> [!TIP]
> Le recomendamos que incluya nuestras aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Añada otras [aplicaciones, bots y conectores](deploy-apps-microsoft-teams-landing-page.md) a medida que maneja la adopción de Teams.

 > [!Note]
 > Para obtener más información sobre las características de Teams en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Requisitos previos a la implementación del chat

Antes de implementar Teams en toda la organización, dedique un tiempo para confirmar que el entorno está listo para Teams. Revise [Preparar la red de la organización para Teams](prepare-network.md) y realice los cambios necesarios en el entorno.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Está preparada mi organización para implementar Teams?|Para responder a esta pregunta, consulte: <ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li><li>[Intervalos de direcciones IP y URL](office-365-urls-ip-address-ranges.md)</li><li>[Planear los grupos de Microsoft 365 cuando se crean equipos](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones de chat, equipos y canales que la mayoría de organizaciones quieren cambiar (si la configuración predeterminada no les funciona).

### <a name="teams-administrators"></a>Administradores de Teams

Teams ofrece un conjunto de roles de administrador personalizados que pueden usarse para administrar Teams en su organización. Los roles proporcionan distintas funciones a los administradores.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿A quién se asignará el rol de Administrador de comunicaciones de Teams?|Para obtener más información sobre los roles de administrador de Teams, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).|
|¿A quién se asignará el rol de Ingeniero de soporte en comunicaciones de Teams?|Para asignar roles de administrador, vea [asignar roles de administrador y de no administrador a los usuarios con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|¿A quién se asignará el rol de Especialista de soporte en comunicaciones de Teams?||
|||

### <a name="teams-owners-and-members"></a>Miembros y propietarios de equipos

Además de los roles de administrador, Teams le permite asignar a los propietarios roles de usuarios y miembros, y ofrecerles de forma selectiva las capacidades del moderador (si se ha configurado la moderación) para controlar quién puede realizar determinadas acciones dentro de un canal. La moderación le permite controlar quién puede iniciar nuevas publicaciones en un canal, agregar y quitar miembros del equipo como moderadores y controlar si los miembros del equipo pueden responder a los mensajes de canal existentes.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Quién debe asignarse a cada rol? | Para comparar las características de cada rol, consulte [asignar propietarios del equipo, moderadores y miembros del equipo en Microsoft Teams.](assign-roles-permissions.md)
|¿Cómo asigno un rol de usuario? | Para asignar o cambiar un rol, consulte [Asignar un rol de usuario](assign-roles-permissions.md#assign-a-user-role).
|¿Necesito controlar quién puede publicar y responder en un canal? | Para configurar la moderación [, consulte Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Directivas de mensajería

Las directivas de mensajería controlan qué características de mensajería están disponibles para los usuarios en canales y chats de Teams. Por ejemplo, quién puede editar y eliminar los mensajes enviados, quién puede usar el chat, quién puede usar memes en conversaciones y mucho más. De forma predeterminada, se asigna la directiva de mensajería global a los usuarios y todas las características están **Activadas**. Puede usar la directiva global predeterminada o bien crear una nueva o más directivas de mensajería personalizadas para los miembros de su organización. 

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a personalizar la directiva de mensajería global?|Para obtener información sobre cómo usar el centro de administración de Microsoft Teams para cambiar la directiva global de mensajería o agregar una nueva directiva, vea [Administrar directivas de mensajería de Teams](messaging-policies-in-teams.md).|
|¿Necesito varias directivas de mensajería?|Para crear y asignar una directiva de mensajería en PowerShell, consulte [Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería](scripts/powershell-script-teams-messaging-policy-edu.md).|
|¿Cómo determino qué directiva de mensajería obtiene cada grupo de usuarios?|Para obtener información sobre los cmdlets CsTeamsMessagingPolicy, consulte [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).|
||| 

### <a name="external-access"></a>Acceso externo

El acceso externo (anteriormente conocido como federación) permite que los usuarios de Teams y Skype Empresarial se comuniquen con usuarios de fuera de la organización. Al activarlo y agregar dominios a la lista de permitidos, los usuarios pueden comunicarse con otros usuarios de dominios y organizaciones diferentes. El acceso externo se diferencia del acceso de invitado en que se le da permiso de acceso a un dominio completo, no solo a un usuario individual. El acceso externo está desactivado de forma predeterminada.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|<ul><li>¿Voy a activar el acceso externo para mi organización?</li><li>Si lo habilito, ¿voy a limitar los dominios con los que mi organización puede comunicarse?</li></ul> |<br>Para activar el acceso externo, consulte [Plan para el acceso externo](manage-external-access.md#plan-for-external-access).|
|||

### <a name="guest-access"></a>Acceso de invitado

El acceso de invitado en Teams permite a personas fuera de su organización acceder a los equipos y canales. Puede usar la configuración de acceso de invitado para controlar qué características pueden o no pueden usar los usuarios invitados. El acceso de invitado está desactivado de forma predeterminada. Para obtener más información, consulte [Acceso de invitado a Teams](https://docs.microsoft.com/microsoftteams/guest-access).

> [!NOTE]
> Para obtener más información sobre el acceso externo y el acceso de invitado, consulte: [Comunicación con usuarios de otras organizaciones en Microsoft Teams](communicate-with-users-from-other-organizations.md)


|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a activar el acceso de invitado para mi organización?|Para activar el acceso de invitado, consulte [Activar o desactivar el acceso de invitado en Teams](set-up-guests.md).|
|Si lo habilito, ¿voy a personalizar las funciones disponibles para los invitados de mi organización?|Para personalizar la disponibilidad de características de acceso de invitado, consulte[Autorizar el acceso de invitado en Teams](teams-dependencies.md).|
|||

### <a name="teams-settings"></a>Configuración de Teams

La configuración de Teams le permite configurar los equipos con características como la integración de correo electrónico, opciones de almacenamiento de nube, pestaña de la organización, configuración de dispositivos de salas de reuniones y el ámbito de búsqueda. Cuando realice cambios en esta configuración, se aplicarán a todos los equipos de su organización. Para obtener más información, consulte [Configuración de Teams](enable-features-office-365.md#teams-settings).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a personalizar la configuración de Teams para mi organización? | Para obtener información sobre la configuración de Teams y cómo personalizarla, consulte [Configuración de Teams](enable-features-office-365.md#teams-settings).|
|||

### <a name="teams-clients"></a>Clientes de Teams

Teams es compatible con una serie de clientes web, de escritorio y móviles, y su configuración predeterminada permite a los usuarios elegir entre los clientes que quieran. Para obtener más información, consulte [Obtener clientes para Teams](get-clients.md).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a personalizar la disponibilidad de clientes de Teams para mi organización?|Consulte [Requisitos de hardware de la aplicación de Teams](hardware-requirements-for-the-teams-app.md). |
|¿Voy a personalizar la configuración de clientes de Teams para mi organización?|Obtenga información sobre cómo [Instalar Teams con MSI](msi-deployment.md).|
|||

### <a name="teams-usage-reporting"></a>Informes de uso de Teams

El administrador global, el administrador de servicios de Teams y los lectores de informes pueden ver los informes de uso de Teams. Para obtener más información, consulte los [análisis de uso de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|<br> ¿Quién necesita ver los informes de uso de Teams? ¿Tienen el rol correcto para poder verlos? |<ul><li>Si el usuario no es administrador, [asígnele el rol de Lector de informes](teams-activity-reports.md#reports-reader-role).</li><li>Vea [Roles y permisos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [Ver y asignar roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para obtener información sobre cómo asignar roles de administrador en Azure Active Directory. |
|||

### <a name="teams-default-apps"></a>Aplicaciones predeterminadas de Teams 

Teams ofrece una serie de aplicaciones propias (proporcionadas por Microsoft) y aplicaciones de terceros para interactuar con los usuarios, ayudar en la productividad e integrar los servicios empresariales usados frecuentemente en Teams. Obtener aplicaciones desde la Tienda Teams. Las aplicaciones están activadas de forma predeterminada en Teams. 

Para obtener más información sobre cómo implementar y administrar aplicaciones en Teams, consulte las instrucciones detalladas sobre [aplicaciones, bots y conectores](deploy-apps-microsoft-teams-landing-page.md).

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="teams-licensing"></a>Licencias de Teams

Teams se incluye como parte de muchas licencias de Microsoft 365 u Office 365. Para más información sobre las licencias de Teams, consulte [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Tienen los usuarios las licencias que necesitan para usar todas las características de Teams que quiero implementar? | Para más información sobre los requisitos de licencias, consulte [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilidad de Exchange y SharePoint

Para disfrutar de la experiencia completa de Teams, debe habilitarse a los usuarios en Exchange Online, SharePoint Online y la creación de grupos de Microsoft 365. Los artículos siguientes muestran información relacionada con los buzones de Exchange hospedados en entornos distintos, cómo interactúan Teams y Exchange, y consideraciones similares para SharePoint y OneDrive para la Empresa.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Voy a poder implementar las características de Teams que necesito con las implementaciones actuales de Exchange y SharePoint? |Para obtener más información acerca de Exchange y SharePoint en Teams, consulte:<ul><li> [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)</li><li>[Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Especificaciones y límites de Teams 

Al planear una implementación empresarial de Teams, debe tener en cuenta las limitaciones y especificaciones relevantes, como el número máximo de miembros de un equipo o el número máximo de equipos que puede crear un usuario entre otras.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Con qué limitaciones puedo encontrarme con la implementación de Teams? | Para obtener más información, lea [Especificaciones y límites de Teams](limits-specifications-teams.md). |
|||

### <a name="urls-and-ports"></a>Puertos y direcciones URL

Las organizaciones que mantienen el control específico de su tráfico de internet deberían consultar [Intervalos de direcciones IP y URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) para ver una lista actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben estar configurados correctamente para Teams. Microsoft trata de mejorar constantemente el servicio de Microsoft 365 y Office 365, así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo. Le recomendamos que se suscriba a través de RSS para recibir notificaciones cuando esta información se actualice o se modifique. Como mínimo, asegúrese de que ha abierto los puertos enumerados anteriormente en [Requisitos previos para la implementación de chat](#chat-deployment-prerequisites).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Necesito reglas de acceso a internet para que los usuarios puedan usar Teams o es suficiente con abrir los puertos mínimos necesarios? | Para obtener más información, consulte [direcciones URL e intervalos de direcciones IP](office-365-urls-ip-address-ranges.md).|
|||

### <a name="governance-naming-conventions-who-can-create-teams"></a>Gobierno (convenciones de nomenclatura, quién puede crear equipos)

Su organización puede necesitar la implementación de controles sobre cómo se denominan y clasifican los equipos, quién puede crear equipos, y la expiración, retención y archivado de los equipos. Esto se denomina gobierno. Puede usar Azure Active Directory (Azure AD) para configurar cada una de estas áreas.


| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Necesito implementar controles sobre quién puede crear equipos?| Lea [Planear el gobierno en Teams](plan-teams-governance.md).|
|¿Necesito implementar controles sobre cómo se denominan los equipos?|Lea [Aplicar una directiva de nomenclatura de grupos de Microsoft 365 en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).|
|||

### <a name="teams-application-policy-side-rail-control"></a>Directiva de aplicación de Teams (control de barra lateral)

Una aplicación anclada se muestra en la barra lateral en Teams. Si crea directivas de aplicación de Teams, puede configurar previamente conjuntos de aplicaciones ancladas de Teams y así personalizar Teams para grupos selectos de usuarios. De manera predeterminada, la opción **Permitir aplicaciones externas en Microsoft Teams** está activada.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Debería crear conjuntos predeterminados de aplicaciones ancladas de Teams? | Consulte [Configuración de administrador de aplicaciones en Teams](admin-settings.md)|
|¿Cómo decido qué grupos reciben estas agrupaciones de aplicaciones?|Consulte [Consideraciones y permisos de las aplicaciones de Teams](app-permissions.md)|
|||

### <a name="archiving-and-compliance"></a>Archivado y cumplimiento 

Su organización podría necesitar la implementación de controles sobre cómo se archivan los equipos y los tipos de datos que se conservan en ciertos tipos de equipos. Consulte [Información general de seguridad y cumplimiento en Teams](security-compliance-overview.md) para obtener información sobre qué opciones de configuración están activadas de forma predeterminada.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Necesito configurar la retención de equipos?|Para configurar las directivas de retención, consulte [Configurar directivas de retención en Teams](retention-policies.md).|
|¿Necesito configurar el archivado de equipos?|Para archivar o restaurar un equipo, consulte [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|¿Necesito configurar opciones adicionales de cumplimiento?|Para más información sobre la seguridad y cumplimiento, consulte [Información general de seguridad y cumplimiento en Teams](security-compliance-overview.md).|
|||

### <a name="conditional-access"></a>Acceso condicional 

Teams depende en gran medida de Exchange Online, SharePoint Online y Skype Empresarial Online para las situaciones de productividad principales, como reuniones, calendarios, chats de interoperabilidad y archivos compartidos. Las directivas de acceso condicional que se configuran para estas aplicaciones en la nube se aplican a Teams cuando un usuario inicia sesión directamente en Teams, en cualquier cliente. Las directivas de acceso condicional que se configuran para la aplicación en la nube de Teams controlan aspectos como si los usuarios pueden acceder a los servicios de Teams desde algunas redes.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|<br>¿Necesito configurar acceso condicional para Teams?|<ul><li>Para comprender cómo funcionan las directivas de acceso, consulte [¿Cómo funcionan las directivas de acceso condicional para Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Para configurar la autenticación multifactor (MFA) para Teams, consulte:<ul><li>[Inicio rápido: Requerir MFA para aplicaciones específicas con acceso condicional de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Referencia de configuración de acceso condicional de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a>Educación (EDU.) 

Los profesionales de TI que trabajan en el ámbito educativo pueden beneficiarse de Teams para educación, que cuenta con una variedad de funciones que se ajustan para adaptarse a escenarios específicos de educación para estudiantes, profesores y el sector en general.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Voy a usar plantillas específicas de Teams para educación? |Para obtener más información acerca de Teams para educación, consulte [Preguntas más frecuentes de gobierno de Microsoft Education para administradores](plan-teams-governance-edu.md).|
|¿Voy a implementar ámbito de búsqueda?|Para configurar Teams para el ámbito educativo, consulte [Inicio rápido: Administradores de Teams para el ámbito educativo](teams-quick-start-edu.yml).|
|¿Voy a integrar Teams con el servicio de School Data Sync para aprovisionar cuentas de usuario?|[Recursos de Teams para administradores de educación](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a>Administración pública: consideraciones GCC

El uso de Office 365 para la Administración Pública de Estados Unidos - GCC (Government Community Cloud) es apropiado para cumplir con los requisitos de los profesionales de la tecnología de la información que dirigen los despliegues de Office 365 en las entidades gubernamentales federales, estatales, locales, tribales o territoriales de los EE. UU. o en otras entidades que manejan datos que están sujetos a las regulaciones y requisitos gubernamentales.

| Pregúntese lo siguiente: | Action |
|--------------|--------|
| ¿Voy a necesitar implementar Teams en un entorno de Office 365 para administración pública: GCC? | Para las consideraciones de implementación, vea [Plan para Office 365 Administración Pública - Implementaciones de GCC](plan-for-government-gcc.md).|
|||

## <a name="next-steps"></a>Siguientes pasos
- [Impulsar la adopción](adopt-microsoft-teams-landing-page.md) de chat, equipos, canales y aplicaciones.
- Incluya aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otras [aplicaciones, bots y conectores](deploy-apps-microsoft-teams-landing-page.md) a medida que impulsa la adopción de Teams.
- [Implementar reuniones y conferencias](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar voz en la nube](cloud-voice-landing-page.md)