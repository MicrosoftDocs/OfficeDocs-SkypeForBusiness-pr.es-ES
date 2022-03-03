---
title: Administrar la configuración de su organización
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: Obtenga información sobre cómo activar o desactivar la configuración de toda la organización de Microsoft Teams, incluidas las aplicaciones, el acceso externo, el acceso de invitados, la configuración de Teams y las preferencias de actualización de Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.teamssettings.targetingintro
- ms.teamsadmincenter.teamssettings.overview
- NewAdminCenter_Update
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3b16b3015771cd136f3e5ee7333619008ada332
ms.sourcegitcommit: 5b1d8d6f811fab0b350a09e5187d982f952d0edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "63047140"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>Administrar la configuración de Microsoft Teams para su organización

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Configuración de las aplicaciones de Teams en el centro de administración de Microsoft Teams.

Puede administrar las aplicaciones de su organización en **Aplicaciones de Teams** en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com). Por ejemplo, puede establecer las directivas para controlar qué aplicaciones están disponibles para toda la organización o para usuarios específicos de Teams, y puede personalizar Teams al anclar las aplicaciones que son más importantes para sus usuarios.

Para obtener más información, consulte [Configurar la administración de aplicaciones en Teams](admin-settings.md).

### <a name="workflows-in-teams"></a>Flujos de trabajo en Teams

Los flujos de trabajo permiten automatizar tareas y procesos repetitivos mediante Power Automate. Puede desactivar los flujos de trabajo de su organización en Teams mediante una **directiva de permisos de aplicación** o a través de la página **Administrar aplicaciones** bloqueando Power Automate. Esta característica está activada de forma predeterminada. Para obtener más información sobre los flujos de trabajo, consulte [Examinar y agregar flujos de trabajo](https://support.microsoft.com/office/browse-and-add-workflows-4998095c-8b72-4b0e-984c-f2ad39e6ba9a).

Para desactivar flujos de trabajo con una directiva de permisos de aplicación, edite la directiva global (predeterminada para toda la organización) para incluir Power Automate en la lista bloqueada o quitarla de la lista permitida.

También puede bloquear Power Automate en la página **Administrar aplicaciones**.

1. Vaya a [**Aplicaciones de Teams** > **Administrar aplicaciones**](https://admin.teams.microsoft.com/policies/manage-apps).
1. Busque **Power Automate.**
1. Seleccione la aplicación.
1. Cambie el **Estado** de **Permitido** a **Bloqueado**.

> [!NOTE]
> Al desactivar los flujos de trabajo, se ocultará la aplicación de la tienda de aplicaciones de Teams, las extensiones de mensaje y el menú Más acciones. Al desactivar los flujos de trabajo, también se desactivan los flujos activos.

## <a name="teams-external-access-and-guest-access-settings-in-the-microsoft-teams-admin-center"></a>Configuración de acceso externo de Teams y acceso de invitado en el Centro de administración de Microsoft Teams

Puede controlar la configuración de acceso externo y de invitado en el Centro de administración de Microsoft Teams. Para editar esta configuración, vaya al centro de Microsoft Teams y, a continuación, seleccione **Usuarios**. Puede configurar las siguientes opciones.

### <a name="external-access"></a>Acceso externo

**Acceso externo** permite que los usuarios de Teams y Skype Empresarial se comuniquen con usuarios de fuera de su organización o dominio. Para configurar el acceso externo, vaya a [Permitir que los usuarios de Teams chateen y se comuniquen con usuarios de otra organización de Teams](./manage-external-access.md).

Para agregar o bloquear un dominio:

1. Seleccione **Agregar un dominio**.
2. En el panel Agregar un dominio, escriba el nombre del dominio y seleccione la barra espaciadora para guardar el nombre.
3. Seleccione **Permitido** o **Bloqueado**.
4. Seleccione **Listo** para guardar los cambios. 

### <a name="guest-access"></a>Acceso de invitado

**Acceso de invitado** en Microsoft Teams permite que los equipos de su organización puedan colaborar con personas que no pertenecen a la organización al concederles acceso a equipos y canales. Todo contacto que tenga una cuenta de correo electrónico empresarial o de consumidor (como Outlook.com o Gmail.com) puede participar como invitado en Teams con acceso total a los chats, las reuniones y los archivos del equipo. Para obtener más información, consulte [Acceso de invitado de Microsoft Teams](guest-access.md).

## <a name="teams-settings-and-teams-upgrade-settings-in-the-microsoft-teams-admin-center"></a>Configuración de Teams y configuración de actualización de Teams en el Centro de administración de Microsoft Teams

Puede controlar la configuración de Teams y la configuración de actualización de Teams en el Centro de administración de Microsoft Teams. Para editar esta configuración, vaya al Centro de administración de Microsoft Teams y, a continuación, seleccione **Teams**. Puede configurar las siguientes opciones.

### <a name="teams-settings"></a>Configuración de Teams

En **ajustes de Teams**, puede ajustar características para Teams incluyendo notificaciones y fuentes, integración de email, opciones de almacenamiento en la nube, y dispositivos.

#### <a name="notifications-and-feeds"></a>Notificaciones y fuentes

Aquí, puede controlar si las fuentes sugeridas aparecen en la fuente de actividad de los usuarios en Teams. Para obtener más información sobre la fuente de actividades, consulte [Explore la fuente de actividades en Teams](https://support.office.com/article/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56).

#### <a name="tagging"></a>Etiquetado

Las etiquetas permiten que los usuarios se comuniquen con un subconjunto de personas en un equipo. Se pueden agregar etiquetas a uno o más miembros del equipo. Cuando se agrega una etiqueta, cualquiera del equipo puede usarla en @menciones en una publicación de canal para comunicarse únicamente con las personas a las que se les ha asignado esa etiqueta. Use estas opciones de configuración para controlar quién puede agregar etiquetas y cómo se usan las etiquetas en la organización. Para obtener más información, consulte [Administración de etiquetas en Teams](manage-tags.md).

#### <a name="email-integration"></a>Integración de correo electrónico

Active esta característica para que los usuarios puedan enviar un correo electrónico a un canal en Microsoft Teams mediante la dirección de correo electrónico del canal. Los usuarios pueden hacer esto para cualquier canal que pertenezca a un equipo que sea de su posesión. Los usuarios también pueden enviar correos electrónicos a cualquier canal de un equipo que tenga conectores activados para los miembros del equipo. Para activar la integración del correo electrónico, asegúrese de que **Permitir que los usuarios envíen correos electrónicos a una dirección de correo electrónico de canal** esté **Activado**. Después, compruebe que el dominio de la dirección de correo electrónico del remitente no esté bloqueado en Centro de administración de Teams > Configuración de toda la organización > Configuración de Microsoft Teams > Integración de correo electrónico > **Aceptar el correo electrónico del canal desde estos dominios SMTP**. Debe estar en blanco o incluir todos los dominios de los que espera recibir correos electrónicos. A continuación, asegúrese de tener las reglas necesarias para garantizar que [el correo electrónico en la dirección de correo del canal de Teams no esté bloqueado](/office365/servicedescriptions/exchange-online-protection-service-description/anti-spam-and-anti-malware-protection-eop#customize-anti-spam-policies).

#### <a name="files"></a>Archivos

Aquí puede activar o desactivar las opciones de uso compartido de archivos y de almacenamiento de archivos en la nube.

Los usuarios pueden cargar y compartir archivos de los servicios de almacenamiento en nube en los canales y chats de Microsoft Teams. Las opciones de almacenamiento en la nube en Teams actualmente incluyen Dropbox, Box, archivos Citrix, Google Drive y Egnyte. Active el conmutador de los proveedores de almacenamiento en nube que quiera usar su organización.

#### <a name="organization"></a>Organización

Aquí puede activar la pestaña **Organización**, que muestra el organigrama detallado de la organización del usuario. Para más información, consulte [Usar la pestaña Organización en Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

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

#### <a name="safety-and-communications"></a>Seguridad y comunicaciones

El chat supervisado permite a las organizaciones y a las escuelas limitar las capacidades del chat con los permisos basados en roles. Estos permisos controlan la cantidad de supervisión que requiere un usuario al chatear con otras personas. Obtenga más información acerca del [chat supervisado](supervise-chats-edu.md).

### <a name="teams-upgrade-settings"></a>Configuración de actualización de Teams

Puede usar esta opción para configurar la forma en que los usuarios actualizan de Skype Empresarial a Microsoft Teams. 

#### <a name="coexistence-mode"></a>Modo de coexistencia
Puede especificar un modo de coexistencia: 

- **Solo Teams**
- **Aplicaciones aisladas** (Teams y Skype empresarial en coexistencia)
- **Solo Skype Empresarial**
- **Skype Empresarial con la colaboración de Teams** (los usuarios reciben chats y llamadas, y conciertan reuniones en Skype empresarial, pero usan Teams para colaborar en grupo).
- **Skype Empresarial con la colaboración de Teams y reuniones** (los usuarios reciben chats y llamadas en Skype Empresarial, pero usan Teams para colaborar en grupo).

El modo de coexistencia que elija determina el enrutamiento de las llamadas entrantes y de los chats, así como la aplicación que utiliza el usuario para iniciar los chats y las llamadas, o para programar reuniones. Para obtener más información sobre los modos de coexistencia, vaya a [Descripción de la coexistencia y la interoperabilidad de Skype Empresarial y Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Preferencias de la aplicación

Aquí puede elegir la aplicación que utilizarán los usuarios para unirse a las reuniones de Skype Empresarial (Skype Empresarial o la [Aplicación Reuniones de Skype](https://support.office.com/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Esta opción no depende de la configuración del modo de coexistencia.

### <a name="planning-settings-in-the-microsoft-teams-admin-center"></a>Configuración de planeación en el Centro de administración de Microsoft Teams

#### <a name="network-planner"></a>Planificador de red

El planificador de red le ayuda a determinar y organizar los requisitos de la red para conectar a los usuarios de Teams dentro de la organización.  Obtenga información acerca de cómo [Usar el Planificador de red para Microsoft Teams](./network-planner.md).

También puede seleccionar la opción "Descargar la aplicación Teams en segundo plano para usuarios de Skype Empresarial".  Esta configuración está seleccionada de forma predeterminada. Con esta configuración habilitada, se descargará la aplicación de Teams en segundo plano para los usuarios que ejecuten la aplicación de Skype empresarial en Windows. Esto sucede si el modo de Coexistencia del usuario es Solo Teams, o si se habilita la notificación de actualización pendiente en la aplicación de Skype Empresarial.

## <a name="other-settings-in-the-microsoft-teams-admin-center"></a>Otras opciones de configuración en el Centro de administración de Microsoft Teams

### <a name="skype-for-business"></a>Skype Empresarial

Utilice esta página para administrar las características de Skype empresarial para los usuarios de Skype empresarial de su organización. Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](skype-for-business-settings.md)

## <a name="how-can-i-tell-which-features-are-available"></a>¿Cómo puedo saber qué características están disponibles?

Lea el [Mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) para ver información sobre las nuevas características de Microsoft Teams. Para obtener más información acerca de las nuevas y las próximas características, vea la página de [Novedades](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) de Teams y el [blog de la comunidad tecnológica de Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531). 

## <a name="more-information"></a>Más información

Para obtener información sobre qué roles pueden realizar funciones de administración, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md).
