---
title: Chat, equipos, canales y aplicaciones en Microsoft Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Contiene instrucciones paso a paso para configurar los ajustes de Teams para el chat, los equipos, las aplicaciones y los canales en Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: 04863f6dd914b935b68120fd5c2df6105770c634
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576456"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, equipos, canales y aplicaciones en Microsoft Teams

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

Para empezar, vea nuestro breve vídeo sobre el chat, los equipos y los canales de Teams (4:30 minutos):

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> Le recomendamos que incluya nuestras aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otras [aplicaciones de Teams](deploy-apps-microsoft-teams-landing-page.md) a medida que impulsa la adopción de Teams.

 > [!Note]
 > Para obtener más información sobre las características de Teams en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Requisitos previos a la implementación del chat

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Está preparada mi organización para implementar Teams?|Para responder a esta pregunta, consulte: <ul><li>[Preparar la red de la organización para Microsoft Teams](prepare-network.md)</li><li>[Intervalos de direcciones IP y URL](office-365-urls-ip-address-ranges.md)</li><li>[Planear los grupos de Microsoft 365 cuando se crean equipos](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Decisiones de implementación principales

Estas son las opciones de chat, equipos y canales que la mayoría de organizaciones quieren cambiar (si la configuración predeterminada no les funciona).

### <a name="teams-administrators"></a>Administradores de Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿A quién se asignará el rol de Administrador de comunicaciones de Teams?|Para obtener más información sobre los roles de administrador de Teams, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).|
|¿A quién se asignará el rol de Ingeniero de soporte en comunicaciones de Teams?|Para asignar roles de administrador, vea [asignar roles de administrador y de no administrador a los usuarios con Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|¿A quién se asignará el rol de Especialista de soporte en comunicaciones de Teams?||

### <a name="teams-owners-and-members"></a>Miembros y propietarios de equipos

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Quién debe asignarse a cada rol? | Para comparar las características de cada rol, consulte [asignar propietarios del equipo, moderadores y miembros del equipo en Microsoft Teams.](assign-roles-permissions.md)
|¿Cómo asigno un rol de usuario? | Para asignar o cambiar un rol, consulte [Asignar un rol de usuario](assign-roles-permissions.md#assign-a-user-role).
|¿Necesito controlar quién puede publicar y responder en un canal? | Para configurar la moderación [, consulte Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Directivas de mensajería

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization. 

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a personalizar la directiva de mensajería global?|Para obtener información sobre cómo usar el centro de administración de Microsoft Teams para cambiar la directiva global de mensajería o agregar una nueva directiva, vea [Administrar directivas de mensajería de Teams](messaging-policies-in-teams.md).|
|¿Necesito varias directivas de mensajería?|Para crear y asignar una directiva de mensajería en PowerShell, consulte [Ejemplo de script de PowerShell: Crear un equipo y asignar una directiva de mensajería](scripts/powershell-script-teams-messaging-policy-edu.md).|
|¿Cómo determino qué directiva de mensajería obtiene cada grupo de usuarios?|Para obtener información sobre los cmdlets CsTeamsMessagingPolicy, consulte [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Acceso externo

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|<ul><li>¿Desactivaré las reuniones externas y el chat de mi organización?</li><li>Si lo habilito, ¿voy a limitar los dominios con los que mi organización puede comunicarse?</li></ul> |<br>Para activar o desactivar la reunión externa y chatear, consulte [Administrar reuniones externas y chatear](manage-external-access.md).|

### <a name="guest-access"></a>Acceso de invitado

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> Para obtener más información sobre el acceso externo y el acceso de invitado, consulte: [Comunicación con usuarios de otras organizaciones en Microsoft Teams](communicate-with-users-from-other-organizations.md)


|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Activo el acceso de invitado para mi organización?|Para activar o desactivar el acceso de invitado, consulte [Activar o desactivar el acceso de invitado en Teams](set-up-guests.md).|
|Si lo habilito, ¿voy a personalizar las funciones disponibles para los invitados de mi organización?|Para personalizar la disponibilidad de características de acceso de invitado, consulte[Autorizar el acceso de invitado en Teams](teams-dependencies.md).|

### <a name="private-channels"></a>Canales privados

Los canales privados permiten a un subconjunto de miembros del equipo colaborar en un espacio privado al que otros miembros del equipo no pueden acceder ni pueden ver. Cualquier persona, incluidos los invitados, puede agregarse como miembro de un canal privado siempre y cuando ya sean miembros del equipo.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|Voy a permitir que los propietarios y miembros del equipo creen canales privados?|Para establecer la directiva de canales privados para la organización, vea [Administrar directivas de canal en Microsoft Teams](teams-policies.md)|

### <a name="shared-channels"></a>Canales compartidos

Los canales compartidos permiten agregar a un canal a usuarios que no son miembros de un equipo. Esto incluye a usuarios que están fuera de la organización. Los canales compartidos ofrecen ventajas con respecto al acceso de invitado: los usuarios ajenos a la organización no requieren una cuenta de invitado en el directorio.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Cuándo hacer uso de los canales compartidos y cuándo del acceso de invitado?|Consulte [Canales compartidos en Microsoft Teams](shared-channels.md).|
|<ul><li>¿Voy a permitir que los propietarios de equipos creen canales compartidos?</li><li>¿Voy a permitir que los propietarios de equipos compartan canales con usuarios ajenos a la organización?</li><li>¿Voy a permitir que los usuarios participen en canales compartidos que se encuentran fuera de la organización?</li></ul> |<br>Para establecer la directiva de canales compartidos para la organización, vea [Administrar directivas de canal en Microsoft Teams](teams-policies.md).|

### <a name="teams-settings"></a>Configuración de Teams

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a personalizar la configuración de Teams para mi organización? | Para obtener información sobre la configuración de Teams y cómo personalizarla, consulte [Configuración de Teams](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Clientes de Teams

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Voy a personalizar la disponibilidad de clientes de Teams para mi organización?|Consulte [Requisitos de hardware de la aplicación de Teams](hardware-requirements-for-the-teams-app.md). |
|¿Voy a personalizar la configuración de clientes de Teams para mi organización?|Obtenga información sobre cómo [Instalar Teams con MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Informes de uso de Teams

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|<br> ¿Quién necesita ver los informes de uso de Teams? ¿Tienen el rol correcto para poder verlos? |<ul><li>Si el usuario no es administrador, [asígnele el rol de Lector de informes](teams-activity-reports.md#reports-reader-role).</li><li>Vea [Roles y permisos](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [Ver y asignar roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para obtener información sobre cómo asignar roles de administrador en Azure Active Directory.|

### <a name="teams-default-apps"></a>Aplicaciones predeterminadas de Teams 

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams. 

Para obtener más información sobre cómo implementar y administrar aplicaciones en Teams, consulte nuestras instrucciones detalladas de [administración de](deploy-apps-microsoft-teams-landing-page.md) aplicaciones.

## <a name="additional-deployment-decisions"></a>Decisiones de implementación adicionales

Puede que le interese cambiar esta configuración en función de las necesidades y la configuración de su organización.

### <a name="teams-licensing"></a>Licencias de Teams

Teams se incluye como parte de varias licencias de Microsoft 365.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
|¿Tienen los usuarios las licencias que necesitan para usar todas las características de Teams que quiero implementar? | Para más información sobre los requisitos de licencias, consulte [Descripción del servicio de Microsoft Teams](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilidad de Exchange y SharePoint

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Voy a poder implementar las características de Teams que necesito con las implementaciones actuales de Exchange y SharePoint? |Para obtener más información acerca de Exchange y SharePoint en Teams, consulte:<ul><li> [Interacción entre Exchange y Microsoft Teams](exchange-teams-interact.md)</li><li>[Interacción de SharePoint Online y OneDrive con Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Especificaciones y límites de Teams 

Al planear una implementación empresarial de Teams, debe tener en cuenta las limitaciones y especificaciones relevantes, como el número máximo de miembros de un equipo o el número máximo de equipos que puede crear un usuario entre otras.

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Con qué limitaciones puedo encontrarme con la implementación de Teams? | Para obtener más información, lea [Especificaciones y límites de Teams](limits-specifications-teams.md). |

### <a name="urls-and-ports"></a>Puertos y direcciones URL

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|Pregúntese lo siguiente:|Acción |
|------------|-------|
| ¿Necesito reglas de acceso a internet para que los usuarios puedan usar Teams o es suficiente con abrir los puertos mínimos necesarios? | Para obtener más información, consulte [direcciones URL e intervalos de direcciones IP](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Gobierno (convenciones de nomenclatura, quién puede crear equipos)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.


| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Necesito implementar controles sobre quién puede crear equipos?| Lea [Planear el gobierno en Teams](plan-teams-governance.md).|
|¿Necesito implementar controles sobre cómo se denominan los equipos?|Lea [Aplicar una directiva de nomenclatura de grupos de Microsoft 365 en Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Directiva de aplicación de Teams (control de barra lateral)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Debería crear conjuntos predeterminados de aplicaciones ancladas de Teams? | Consulte [Configuración de administrador de aplicaciones en Teams](admin-settings.md)|
|¿Cómo decido qué grupos reciben estas agrupaciones de aplicaciones?|Consulte [Consideraciones y permisos de las aplicaciones de Teams](app-permissions.md)|

### <a name="archiving-and-compliance"></a>Archivado y cumplimiento 

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Necesito configurar la retención de equipos?|Para configurar las directivas de retención, consulte [Configurar directivas de retención en Teams](retention-policies.md).|
|¿Necesito configurar el archivado de equipos?|Para archivar o restaurar un equipo, consulte [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|¿Necesito configurar opciones adicionales de cumplimiento?|Para más información sobre la seguridad y cumplimiento, consulte [Información general de seguridad y cumplimiento en Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Acceso condicional 

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|<br>¿Necesito configurar acceso condicional para Teams?|<ul><li>Para comprender cómo funcionan las directivas de acceso, consulte [¿Cómo funcionan las directivas de acceso condicional para Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Para configurar la autenticación multifactor (MFA) para Teams, consulte:<ul><li>[Inicio rápido: Requerir MFA para aplicaciones específicas con acceso condicional de Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Referencia de configuración de acceso condicional de Azure Active Directory](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>Educación (EDU.) 

Los profesionales de TI que trabajan en el ámbito educativo pueden beneficiarse de Teams para educación, que cuenta con una variedad de funciones que se ajustan para adaptarse a escenarios específicos de educación para estudiantes, profesores y el sector en general.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
|¿Voy a usar plantillas específicas de Teams para educación? |Para obtener más información acerca de Teams para educación, consulte [Preguntas más frecuentes de gobierno de Microsoft Education para administradores](plan-teams-governance-edu.md).|
|¿Voy a implementar ámbito de búsqueda?|Para configurar Teams para el ámbito educativo, consulte [Inicio rápido: Administradores de Teams para el ámbito educativo](teams-quick-start-edu.yml).|
|¿Voy a integrar Teams con el servicio de School Data Sync para aprovisionar cuentas de usuario?|[Recursos de Teams para administradores de educación](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>Administración pública: consideraciones GCC

El uso de Office 365 para la Administración Pública de Estados Unidos - GCC (Government Community Cloud) es apropiado para cumplir con los requisitos de los profesionales de la tecnología de la información que dirigen los despliegues de Office 365 en las entidades gubernamentales federales, estatales, locales, tribales o territoriales de los EE. UU. o en otras entidades que manejan datos que están sujetos a las regulaciones y requisitos gubernamentales.

| Pregúntese lo siguiente: | Acción |
|--------------|--------|
| ¿Voy a necesitar implementar Teams en un entorno de Office 365 para administración pública: GCC? | Para las consideraciones de implementación, vea [Plan para Office 365 Administración Pública - Implementaciones de GCC](plan-for-government-gcc.md).|

## <a name="next-steps"></a>Siguientes pasos
- [Impulsar la adopción](adopt-microsoft-teams-landing-page.md) de chat, equipos, canales y aplicaciones.
- Incluya aplicaciones destacadas, como Planner, en la implementación inicial de Teams. Agregue otra [aplicación de Teams](deploy-apps-microsoft-teams-landing-page.md) mientras impulsa la adopción de Teams.
- [Implementar reuniones y conferencias](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar voz en la nube](cloud-voice-landing-page.md)
