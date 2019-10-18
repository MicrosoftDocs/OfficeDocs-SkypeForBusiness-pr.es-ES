---
title: Administrar la configuración de Microsoft Teams para su organización
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Obtenga información sobre cómo activar o desactivar la configuración de toda la organización de Microsoft Teams para su organización, incluidas las aplicaciones, el acceso externo, el acceso de invitados, la configuración de Teams y las preferencias de actualización de Teams.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbb05df61a9baec544ad2ff1441a0faf329949e1
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715931"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Administrar la configuración de Microsoft Teams para su organización

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Configuración de las aplicaciones de Teams en el centro de administración de Microsoft Teams.

Puede administrar las aplicaciones de su organización en **Aplicaciones de Teams** en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com). Por ejemplo, puede establecer las directivas para controlar qué aplicaciones están disponibles para toda la organización o para usuarios específicos de Teams, y puede personalizar Teams al anclar las aplicaciones que son más importantes para sus usuarios.

Para obtener más información, consulte [Configurar la administración de aplicaciones en Teams](admin-settings.md).  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Configuración de Teams de toda la organización en el centro de administración de Microsoft Teams.

Puede controlar la configuración de usuario en toda la organización en el Centro de administración de Microsoft Teams. Para editar la configuración de toda la organización, vaya al Centro de administración de Microsoft Teams y, después, seleccione **Configuración de toda la organización**. Puede configurar las opciones siguientes.

### <a name="external-access"></a>Acceso externo

**Acceso externo** permite que los usuarios de Teams y Skype Empresarial se comuniquen con usuarios de fuera de su organización o dominio. Para configurar el acceso externo, vaya a [Permitir que los usuarios de Teams chateen y se comuniquen con usuarios de otra organización de Teams](let-your-teams-users-communicate-with-other-people.md).

Para agregar o bloquear un dominio:

1. Seleccione **Agregar un dominio**.
2. En el panel Agregar un dominio, escriba el nombre del dominio y haga clic en la barra espaciadora para guardar el nombre.
3. Seleccione **Permitido** o **Bloqueado**.
4. Seleccione **Listo** para guardar los cambios. 

### <a name="guest-access"></a>Acceso de invitado

**Acceso de invitado** en Microsoft Teams permite que los equipos de su organización puedan colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales. Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo. Para obtener más información, consulte [Acceso de invitado de Microsoft Teams](guest-access.md).

### <a name="teams-settings"></a>Configuración de Microsoft Teams

En **ajustes de Teams**, puede ajustar características para Teams incluyendo notificaciones y fuentes, integración de email, opciones de almacenamiento en la nube, y dispositivos.

#### <a name="notifications-and-feeds"></a>Notificaciones y fuentes

Aquí, puede controlar si las fuentes sugeridas aparecen en la fuente de actividad de los usuarios en Teams. Para obtener más información sobre la fuente de actividades, consulte [Explore la fuente de actividades en Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).

#### <a name="email-integration"></a>Integración de correo electrónico

Active esta característica para que los usuarios puedan enviar un correo electrónico a un canal en Microsoft Teams mediante la dirección de correo electrónico del canal. Los usuarios pueden hacer esto para cualquier canal que pertenezca a un equipo que sea de su posesión. Los usuarios también pueden enviar correos electrónicos a cualquier canal de un equipo que tenga conectores activados para los miembros del equipo. Para activar la integración del correo electrónico, asegúrese de que **Permitir que los usuarios puedan enviar correos electrónicos a la dirección de correo electrónico de un canal** esté **Activado**.

#### <a name="files"></a>Archivos

Aquí puede activar o desactivar las opciones de uso compartido de archivos y de almacenamiento de archivos en la nube.

Los usuarios pueden cargar y compartir archivos de los servicios de almacenamiento en nube en los canales y chats de Teams. Las opciones de almacenamiento en nube en Microsoft Teams actualmente incluyen ShareFile, Dropbox, Box y Google Drive. Active el conmutador de los proveedores de almacenamiento en nube que quiera usar su organización.

#### <a name="organization"></a>Organización

Aquí puede activar la ficha **Organización**, que muestra el organigrama detallado de la organización del usuario. Si desea más información, consulte [Usar la ficha Organización en Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="devices"></a>Dispositivos

Esta configuración controla el comportamiento de la cuenta del recurso para los dispositivos Surface Hub que asisten a las reuniones de Microsoft Teams. Use estas opciones para configurar los requisito de autenticación, requerir un PIN de contenido y activar las cuentas de recurso de Surface Hub para enviar mensajes.

- **Requerir un método secundario de autenticación para acceder al contenido de la reunión**: Seleccione el nivel de acceso que tienen los usuarios cuando especifican el PIN de contenido.
- **Establecer el PIN de contenido**: Requiera que los usuarios especifiquen este PIN para impedir el acceso no autorizado a los documentos. Con esto se impide que los usuarios no autorizados se unan a reuniones futuras y vean los datos adjuntos.
- **Las cuentas de recursos pueden enviar mensajes**: **Active** esta opción para permitir que se envíen mensajes desde la cuenta del recurso de Surface Hub.

#### <a name="search-by-name"></a>Buscar por nombre

La búsqueda de directorios enfocada de Microsoft Teams usa la directiva de libretas de direcciones (APB) de Exchange para permitir que las organizaciones puedan crear límites virtuales que controlen la forma en que los usuarios pueden encontrar a otros usuarios de la organización y comunicarse con ellos. Sería conveniente usar la búsqueda de directorios enfocada en estas situaciones:

- La organización tiene varias compañías en su inquilino, pero prefiere mantenerlas por separado. 
- Su centro educativo quiere limitar los chats entre el personal académico y los estudiantes. 

**Active** esta opción para activar las búsquedas de directorios enfocadas.

### <a name="teams-upgrade"></a>Actualización de Microsoft Teams

Puede usar esta opción para configurar la forma en que los usuarios actualizan de Skype Empresarial a Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modo de coexistencia
Puede especificar un modo de coexistencia: **Microsoft Teams solo**, **Aplicaciones aisladas** (coexistencia de Teams y Skype Empresarial) o **Skype Empresarial solo**. El modo de coexistencia que elija determina el enrutamiento de las llamadas entrantes y de los chats, así como la aplicación que utiliza el usuario para iniciar los chats y las llamadas, o para programar reuniones. Para obtener más información sobre los modos de coexistencia, vaya a [Descripción de la coexistencia y la interoperabilidad de Skype Empresarial y Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferencias de la aplicación

Aquí puede elegir la aplicación que utilizarán los usuarios para unirse a las reuniones de Skype Empresarial (Skype Empresarial o la [Aplicación Reuniones de Skype](https://support.office.com/es-ES/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Esta opción no depende de la configuración del modo de coexistencia.

## <a name="how-can-i-tell-which-features-are-available"></a>¿Cómo puedo saber qué características están disponibles?

Lea el [Mapa de ruta de Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para ver información sobre las nuevas características de Microsoft Teams. Para obtener más información acerca de las nuevas y las próximas características, vea la página de [Novedades](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) de Teams y el [blog de la comunidad tecnológica de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Más información

Para obtener información sobre qué roles pueden realizar funciones de administración, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).
