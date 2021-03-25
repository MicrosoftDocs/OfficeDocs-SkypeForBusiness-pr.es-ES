---
title: Consideraciones y permisos de las aplicaciones de Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: El administrador puede obtener información sobre los datos y permisos que las aplicaciones de Microsoft Teams solicitan a su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120862"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y permisos de las aplicaciones de Microsoft Teams

Las aplicaciones de Microsoft Teams son una forma de agregar una o más capacidades _a_ un paquete de aplicaciones que se puede instalar, actualizar y desinstalar. Las funcionalidades incluyen:

- Bots
- Extensiones de mensajería
- Pestañas
- Conectores

Los usuarios consienten las aplicaciones y las administran desde una perspectiva de directiva. Sin embargo, en su mayoría, los permisos y el perfil de riesgo de una aplicación se definen por los permisos y perfiles de riesgo de las capacidades que contiene la aplicación. Por lo tanto, este artículo se centra en los permisos y consideraciones en el nivel de capacidad.

Los permisos enumerados a continuación en [mayúsculas,](/graph/permissions-reference)por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE, no aparecen en ninguna parte de la documentación para desarrolladores de [Microsoft Teams](/microsoftteams/platform/overview) ni en los permisos de Microsoft Graph. Son simplemente una abreviada descriptiva para el propósito de este artículo.


| Título   | Descripción    |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Use las tablas siguientes como guía para comprender qué permisos solicitan las aplicaciones que está investigando.</li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Investigue la aplicación o el servicio en sí para decidir si desea permitir el acceso a ella dentro de su organización. Por ejemplo, los bots envían y reciben mensajes de los usuarios y, excepto los bots personalizados empresariales, se encuentran fuera del límite de cumplimiento. Por lo tanto, cualquier aplicación que incluya un bot requiere esos permisos y tiene ese perfil de riesgo, como mínimo. </li></ul>|

Vea también [Solicitar permisos de dispositivo para la pestaña Microsoft Teams.](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)

## <a name="global-app-permissions-and-considerations"></a>Consideraciones y permisos globales de la aplicación

### <a name="required-permissions"></a>Permisos necesarios

Ninguna

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

- Una aplicación debe revelar qué datos usa y para qué se usan los datos en sus términos de uso y vínculos a la directiva de privacidad.

- [El consentimiento específico de los](resource-specific-consent.md) recursos proporciona un conjunto de permisos que las aplicaciones pueden solicitar, que aparece en la pantalla de instalación de la aplicación. Para obtener más información sobre los permisos de consentimiento específicos de los recursos, vea [Referencia de permisos de Graph.](/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Las aplicaciones también pueden necesitar permisos distintos de los permisos de consentimiento específicos de los recursos. Después de instalar una aplicación, es posible que la aplicación solicite permisos de Graph a través de un aviso de consentimiento. Para obtener más información, vea [Descripción de las experiencias de consentimiento de aplicaciones de Azure AD.](/azure/active-directory/develop/application-consent-experience) Puede configurar los permisos y el consentimiento de la API en Azure Portal. Para obtener más información, vea [Marco de consentimiento de Azure Active Directory.](/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bots y extensiones de mensajería

### <a name="required-permissions"></a>Permisos necesarios

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. El bot puede recibir mensajes de los usuarios y responderles. <sup>1</sup>

- POST_MESSAGE_USER. Después de que un usuario haya enviado un mensaje a un bot, el bot puede enviar al usuario mensajes directos (también denominados *mensajes proactivos* en cualquier momento.

- GET_CHANNEL_LIST. Los bots agregados a los equipos pueden obtener una lista de nombres e IDs de los canales de un equipo.

### <a name="optional-permissions"></a>Permisos opcionales

- IDENTIDAD. Cuando se usa en un canal, los bots de la aplicación pueden acceder a la información básica de identidad de los miembros del equipo (nombre, apellido, nombre principal de usuario [UPN], dirección de correo electrónico); cuando se usa en un chat personal o grupal, el bot puede acceder a la misma información para esos usuarios.

- POST_MESSAGE_TEAM. Permite a los bots de una aplicación enviar mensajes directos (proactivos) a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha hablado con el bot antes.

- Los siguientes no son permisos explícitos, pero están implícitos por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla si un bot puede enviar y recibir archivos en chat personal (aún no es compatible con chats grupales o canales).

### <a name="considerations"></a>Consideraciones

- Los bots solo tienen acceso a los equipos a los que se han agregado o a los usuarios que los han instalado.

- Los bots solo reciben mensajes en los que los usuarios los mencionan explícitamente. Estos datos abandonan la red corporativa.

- Los bots solo pueden responder a las conversaciones en las que se les menciona.

- Después de que un usuario haya conversado con un bot, si el bot almacena el id. de ese usuario, puede enviar mensajes directos a ese usuario en cualquier momento.

- En teoría, es posible que los mensajes de bot contengan vínculos a sitios de suplantación de identidad (phishing) o malware, pero Microsoft puede bloquear los bots por el usuario, el administrador de inquilinos o de forma global.

- Un bot puede recuperar (y puede almacenar) información de identidad muy básica para los miembros del equipo a los que se ha agregado la aplicación, o para usuarios individuales en chats personales o grupales. Para obtener más información sobre estos usuarios, el bot debe requerir que inicien sesión en Azure Active Directory (Azure AD).

- Los bots pueden recuperar (y pueden almacenar) la lista de canales de un equipo; estos datos abandonan la red corporativa.

- Cuando se envía un archivo a un bot, el archivo abandona la red corporativa. Enviar y recibir archivos requiere la aprobación del usuario para cada archivo. 

- De forma predeterminada, los bots no tienen la capacidad de actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión; tan pronto como el usuario inicia sesión, el bot tendrá un token de acceso con el que puede hacer cosas adicionales. Exactamente cuáles son esas cosas adicionales depende del bot y de dónde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada en y puede tener su propio https://apps.dev.microsoft.com/ conjunto de permisos.

- Los bots se informan siempre que se agregan o eliminan usuarios de un equipo.

- Los bots no ven las direcciones IP de los usuarios ni otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá las direcciones IP de los usuarios e información referente).

- Las extensiones de mensajería, por otro lado, sí ven las direcciones IP de los usuarios y la información de referencia.

- Las directrices de la aplicación (y nuestro proceso de revisión de AppSource) requieren discreción en la publicación de mensajes de chat personales a los usuarios (mediante POST_MESSAGE_TEAM permiso) para fines válidos. En caso de abuso, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear los bots de forma centralizada si es necesario.

<sup>1</sup> Algunos bots solo envían mensajes (POST_MESSAGE_USER). Se denominan bots "solo notificación", pero el término no hace referencia a lo que se permite o no permite que un bot haga, significa que el bot no quiere exponer una experiencia conversacional. Teams usa este campo para deshabilitar la funcionalidad de la interfaz de usuario que normalmente se habilitaría; el bot no está restringido en lo que se permite hacer en comparación con los bots que exponen una experiencia conversacional.

<sup>2</sup> Regido por la propiedad supportsFiles Boolean en el objeto bot del manifest.jsarchivo de la aplicación.

> [!NOTE]
> Si un bot tiene su propio inicio de sesión, hay una segunda experiencia de consentimiento diferente la primera vez que el usuario inicia sesión.
>
>Actualmente, los permisos de Azure AD asociados a cualquiera de las capacidades de una aplicación de Teams (bot, pestaña, conector o extensión de mensajería) son completamente independientes de los permisos de Teams que se muestran aquí.

## <a name="tabs"></a>Pestañas

Una pestaña es un sitio web que se ejecuta dentro de Teams.

### <a name="required-permissions"></a>Permisos necesarios

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permisos opcionales

Ninguno (actualmente)

### <a name="considerations"></a>Consideraciones

- El perfil de riesgo de una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador. 

- Una pestaña también obtiene el contexto en el que se está ejecutando, incluido el nombre de inicio de sesión y upn del usuario actual, el id. de objeto de Azure AD para el usuario actual, el id. del grupo de Microsoft 365 en el que reside (si es un equipo), el id. de inquilino y la configuración regional actual del usuario. Sin embargo, para asignar estos id. a la información de un usuario, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.

## <a name="connectors"></a>Conectores

Un conector publica mensajes en un canal cuando se producen eventos en un sistema externo.

### <a name="required-permissions"></a>Permisos necesarios

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permisos opcionales

REPLYTO_CONNECTOR_MESSAGE. Algunos conectores admiten mensajes que se pueden usar, lo que permite a los usuarios publicar respuestas dirigidas al mensaje del conector, por ejemplo agregando una respuesta a un problema de GitHub o agregando una fecha a una tarjeta de Trello.

### <a name="considerations"></a>Consideraciones

- El sistema que publica los mensajes del conector no sabe a quién se publica o quién recibe los mensajes: no se revela información sobre el destinatario. (Microsoft es el destinatario real, no el inquilino; Microsoft realiza la publicación real en el canal).

- No hay datos que abandone la red corporativa cuando los mensajes del conector se publican en un canal.

- Los conectores que admiten mensajes que se pueden usar (REPLYTO_CONNECTOR_MESSAGE permiso) tampoco ven la información de la dirección IP y del remitente; esta información se envía a Microsoft y, a continuación, se enruta a puntos de conexión HTTP que se registraron previamente con Microsoft en el portal conectores.

- Cada vez que se configura un conector para un canal, se crea una dirección URL única para esa instancia del conector. Si se elimina esa instancia del conector, la dirección URL ya no se puede usar.

- Los mensajes del conector no pueden contener datos adjuntos de archivo.

- La dirección URL de la instancia del conector debe tratarse como secreta/confidencial: cualquier persona que tenga esa dirección URL puede publicarla, como una dirección de correo electrónico. Por lo tanto, existe algún riesgo de correo no deseado o vínculos a sitios de suplantación de identidad (phishing) o malware. Si esto sucediera, los propietarios de los equipos pueden eliminar la instancia del conector.

- Si el servicio que envía los mensajes del conector se pone en peligro y empieza a enviar vínculos de correo no deseado,phishing/malware, un administrador de inquilinos puede impedir que se creen nuevas instancias de conector y Microsoft puede bloquearlas de forma centralizada.

> [!NOTE]
> Actualmente no es posible saber qué conectores admiten mensajes de acción (REPLYTO_CONNECTOR_MESSAGE permisos).

## <a name="outgoing-webhooks"></a>Webhooks salientes

*Los webhooks salientes* se crean sobre la marcha por los propietarios del equipo o los miembros del equipo. No son capacidades de las aplicaciones de Teams; esta información se incluye para su integridad.

### <a name="required-permissions"></a>Permisos necesarios

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Puede recibir mensajes de los usuarios y responderles.

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

- Los webhooks salientes son similares a los bots, pero tienen menos privilegios. Deben mencionarse explícitamente, igual que los bots.

- Cuando se registra un webhook saliente, se genera un secreto, que permite al webhook saliente comprobar que el remitente es Microsoft Teams en lugar de un atacante malintencionado. Este secreto debe seguir siendo un secreto; cualquier persona que tenga acceso a él puede suplantar Microsoft Teams. Si el secreto está en peligro, el webhook saliente se puede eliminar y volver a crear, y se generará un nuevo secreto.

- Aunque es posible crear un webhook saliente que no valide el secreto, se recomienda no hacerlo.

- Además de recibir y responder a mensajes, los webhooks salientes no pueden hacer mucho: no pueden enviar mensajes de forma proactiva, no pueden enviar ni recibir archivos, no pueden hacer nada más que los bots puedan hacer excepto recibir y responder a mensajes.