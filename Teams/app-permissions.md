---
title: Consideraciones y permisos de las aplicaciones de Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Administración pueden saber qué datos y permisos Microsoft Teams aplicaciones solicitan a su organización.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 925136660ef6adda6374fab1acccf10a2b9f1722
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190290"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y permisos de las aplicaciones de Microsoft Teams

Microsoft Teams aplicaciones son una forma de agregar una o más funcionalidades en aplicaciones que se pueden instalar, actualizar y desinstalar. Entre las funcionalidades de las aplicaciones se incluyen:

* Bots
* Extensiones de mensajería
* Pestañas
* Conectores

Como administrador, solo puede administrar aplicaciones. Sin embargo, el artículo se centra en los permisos y consideraciones en el nivel de funcionalidad, ya que las capacidades de una aplicación afectan a los permisos necesarios y los perfiles de riesgo de la aplicación. Para el uso, los usuarios aceptan las aplicaciones y las administran los profesionales de TI desde el punto de vista de la directiva.

Los permisos enumerados a continuación en mayúsculas, por ejemplo `RECEIVE_MESSAGE` , `REPLYTO_MESSAGE` son solo para fines ilustrativos y explicativos. Estas cadenas o permisos no aparecen en ninguna parte de la [documentación de Microsoft Teams desarrollador](/microsoftteams/platform/overview) ni de los [permisos de Microsoft Graph](/graph/permissions-reference).

## <a name="global-app-permissions-and-considerations"></a>Permisos y consideraciones de la aplicación global

### <a name="required-permissions"></a>Permisos necesarios

Ninguna

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

* Una aplicación debe revelar qué datos usa y para qué se usan los datos en sus términos de uso y vínculos de directivas de privacidad.

* [El consentimiento específico de](resource-specific-consent.md) recursos proporciona un conjunto de permisos que las aplicaciones pueden solicitar, que aparece en la pantalla de instalación de la aplicación. Para obtener más información sobre los permisos de consentimiento específicos de recursos, consulte [Graph referencia de permisos](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Es posible que las aplicaciones también necesiten permisos que no sean permisos de consentimiento específicos de recursos. Después de instalar una aplicación, es posible que la aplicación solicite permisos de Graph a través de una solicitud de consentimiento. Para obtener más información, consulta [Información sobre las experiencias de consentimiento de aplicaciones de Azure AD](/azure/active-directory/develop/application-consent-experience). Puede configurar los permisos y el consentimiento de la API en el Azure Portal. Para obtener más información, consulta [Azure Active Directory marco de consentimiento](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots y extensiones de mensajería

### <a name="required-permissions"></a>Permisos necesarios

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: el bot puede recibir mensajes de los usuarios y responder a ellos. <sup>1</sup>

* POST_MESSAGE_USER: Después de que un usuario haya enviado un mensaje a un bot, el bot puede enviar al usuario mensajes directos (también *denominados mensajes proactivos* en cualquier momento).

* GET_CHANNEL_LIST: los bots agregados a los equipos pueden obtener una lista de nombres e identificadores de los canales de un equipo.

### <a name="optional-permissions"></a>Permisos opcionales

* IDENTIDAD: Cuando se usa en un canal, los bots de la aplicación pueden acceder a información de identidad básica de los miembros del equipo (nombre, apellidos, nombre principal de usuario [UPN], dirección de correo electrónico). Cuando se usa en un chat personal o grupal, el bot puede acceder a la misma información para esos usuarios.

* POST_MESSAGE_TEAM: permite que los bots de una aplicación envíen mensajes directos (proactivos) al miembro del equipo en cualquier momento, incluso si el usuario nunca ha interactuado con el bot.

* Los siguientes no son permisos explícitos, pero están implícitos por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* Los siguientes no son permisos explícitos, pero están implícitos por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES, RECEIVE_FILES:<sup>2</sup> Controla si un bot puede enviar y recibir archivos en un chat personal (aún no es compatible con chats grupales o canales).

### <a name="considerations"></a>Consideraciones

* Los bots solo tienen acceso a los equipos a los que se han agregado o a los usuarios que los han instalado.

* Los bots solo reciben mensajes en los que los usuarios los mencionan explícitamente. Estos datos abandonan la red corporativa.

* Los bots solo pueden responder a las conversaciones en las que se les menciona.

* Cuando un usuario habla con un bot, si el bot almacena el id. de usuario, puede enviar al usuario mensajes directos en cualquier momento.

* Teóricamente, es posible que los mensajes bot contengan vínculos a sitios de suplantación de identidad (phishing) o malware. Sin embargo, El usuario, el administrador de inquilinos o Microsoft pueden bloquear los bots de forma global. [Las comprobaciones de validación y verificación](overview-of-app-validation.md) de aplicaciones garantizan que las aplicaciones falsas no estén disponibles en Teams store.

* Un bot puede recuperar (y almacenar) información de identidad básica para los miembros del equipo a los que se ha agregado la aplicación, o para usuarios individuales en chats personales o grupales. Para obtener más información sobre estos usuarios, el bot debe pedirles que inicien sesión en Azure Active Directory (Azure AD).

* Los bots pueden recuperar (y almacenar) la lista de canales de un equipo; estos datos abandonan la red corporativa.

* De forma predeterminada, los bots no tienen la capacidad de actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión; tan pronto como el usuario inicie sesión, el bot tendrá un token de acceso con el que puede hacer cosas adicionales. Exactamente lo que esas otras cosas dependen del bot y de dónde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada en https://apps.dev.microsoft.com/ y puede tener su propio conjunto de permisos.

* Cuando se envía un archivo a un bot, el archivo abandona la red corporativa. El envío y la recepción de archivos requiere la aprobación del usuario para cada archivo.

* De forma predeterminada, los bots no tienen la capacidad de actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión; tan pronto como el usuario inicie sesión, el bot tendrá un token de acceso con el que puede hacer cosas adicionales. Exactamente lo que esos elementos adicionales dependen del bot y de dónde el usuario inicie sesión: un bot es una aplicación de Azure AD registrada en el [Portal de registro](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) de aplicaciones y puede tener su propio conjunto de permisos.

* Los bots se informan siempre que se agregan a los usuarios o se eliminan de un equipo.

* Los bots no ven las direcciones IP de los usuarios ni otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá las direcciones IP y la información de referencia de los usuarios).

* Las extensiones de mensajería, por otro lado, sí que pueden ver las direcciones IP y la información de referencia de los usuarios.

* Las directrices de la aplicación (y nuestro proceso de revisión de AppSource) requieren discreción al publicar mensajes de chat personales a los usuarios (a través del permiso de POST_MESSAGE_TEAM) para fines válidos. En caso de abuso, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots de forma centralizada si es necesario.

<sup>1</sup> Algunos bots solo envían mensajes (POST_MESSAGE_USER). Se denominan bots "solo de notificación", pero el término no hace referencia a lo que un bot está permitido o no puede hacer, significa que el bot no quiere exponer una experiencia conversacional. Teams usa este campo para deshabilitar la funcionalidad de la interfaz de usuario que normalmente se habilitaría; el bot no está restringido en lo que puede hacer en comparación con los bots que exponen una experiencia conversacional.

<sup>2</sup> Se rige por la propiedad supportsFiles Boolean en el objeto bot del `manifest.json` archivo de la aplicación.

> [!NOTE]
> Si un bot tiene su propio inicio de sesión, hay una segunda experiencia de consentimiento diferente la primera vez que el usuario inicia sesión.
>
>Actualmente, los permisos de Azure AD asociados a cualquiera de las funcionalidades de una aplicación de Teams (bot, tab, conector o extensión de mensajería) son totalmente independientes de los Teams permisos que se muestran aquí.

## <a name="tabs"></a>Pestañas

Una pestaña es un sitio web que se ejecuta dentro de Teams.

### <a name="required-permissions"></a>Permisos necesarios

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permisos opcionales

Ninguno (actualmente)

### <a name="considerations"></a>Consideraciones

* El perfil de riesgo de una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador.

* Una pestaña también obtiene el contexto en el que se ejecuta, incluidos el nombre de inicio de sesión y el UPN del usuario actual, el id. de objeto de Azure AD para el usuario actual, el identificador del grupo de Microsoft 365 en el que reside (si es un equipo), el id. de espacio empresarial y la configuración regional actual del usuario. Sin embargo, para asignar estos identificadores a la información de un usuario, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.

## <a name="connectors"></a>Conectores

Un conector publica mensajes en un canal cuando se producen eventos en un sistema externo.

### <a name="required-permissions"></a>Permisos necesarios

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permisos opcionales

REPLYTO_CONNECTOR_MESSAGE. Algunos conectores admiten mensajes accionables, que permiten a los usuarios publicar respuestas dirigidas al mensaje del conector, por ejemplo, agregando una respuesta a un problema de GitHub o agregando una fecha a una tarjeta de Trello.

### <a name="considerations"></a>Consideraciones

* El sistema que publica los mensajes del conector no sabe a quién se va a publicar ni quién recibe los mensajes: no se divulga ninguna información sobre el destinatario. (Microsoft es el destinatario real, no el inquilino; Microsoft realiza la publicación real en el canal).

* Ningún dato abandona la red corporativa cuando los mensajes del conector se publican en un canal.

* Los conectores que admiten mensajes accionables (permiso de REPLYTO_CONNECTOR_MESSAGE) tampoco ven la dirección IP ni la información de referencia; esta información se envía a Microsoft y, a continuación, se redirige a los puntos de conexión HTTP previamente registrados con Microsoft en el portal conectores.

* Cada vez que se configura un conector para un canal, se crea una dirección URL única para esa instancia del conector. Si se elimina esa instancia del conector, la dirección URL ya no se puede usar.

* Los mensajes del conector no pueden contener archivos adjuntos.

* La dirección URL de la instancia del conector debe tratarse como secreta/confidencial: cualquier persona que tenga esa dirección URL puede publicar en ella, como una dirección de correo electrónico. Por lo tanto, existe algún riesgo de correo no deseado o vínculos a sitios de suplantación de identidad (phishing) o malware. Si esto ocurre, los propietarios de equipos pueden eliminar la instancia del conector.

* Si el servicio que envía mensajes de conector se ve comprometido y empieza a enviar vínculos de correo no deseado/phishing/malware, una Administrador de inquilinos puede impedir la creación de nuevas instancias de conectores y Microsoft puede bloquearlas de forma centralizada.

> [!NOTE]
> Actualmente no es posible saber qué conectores admiten mensajes accionables (REPLYTO_CONNECTOR_MESSAGE permiso).

## <a name="outgoing-webhooks"></a>Webhooks salientes

_Los webhooks salientes_ los crean los propietarios del equipo o los miembros del equipo. No son funcionalidades de Teams aplicaciones; esta información se incluye para su integridad.

### <a name="required-permissions"></a>Permisos necesarios

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Puede recibir mensajes de usuarios y responder a ellos.

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

* Los webhooks salientes son similares a los bots, pero tienen menos privilegios. Deben mencionarse explícitamente, al igual que los bots.

* Cuando se registra un webhook saliente, se genera un secreto, que permite que el webhook saliente compruebe que el remitente está Microsoft Teams en lugar de un atacante malintencionado. Este secreto debe seguir siendo un secreto; cualquier persona que tenga acceso a ella puede suplantar Microsoft Teams. Si el secreto está en peligro, el webhook saliente se puede eliminar y volver a crear, y se generará un nuevo secreto.

* Aunque es posible crear un webhook saliente que no valide el secreto, le recomendamos que lo haga.

* Aparte de recibir y responder mensajes, los webhooks salientes no pueden hacer mucho: no pueden enviar mensajes de forma proactiva, no pueden enviar o recibir archivos, no pueden hacer nada más que los bots pueden hacer excepto recibir y responder mensajes.
