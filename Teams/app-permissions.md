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
description: El administrador puede saber qué datos y permisos solicitan las aplicaciones de Microsoft Teams a su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739388"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y permisos de las aplicaciones de Microsoft Teams

Las aplicaciones de Microsoft Teams son una forma de agregar una o varias funcionalidades en un _paquete de aplicaciones_ que se pueden instalar, actualizar y desinstalar. Las funcionalidades incluyen:

- Bots
- Extensiones de mensajería
- Fichas
- Conectores

Los usuarios tienen que dar su consentimiento a las aplicaciones y su administración corre a cargo de los departamentos de TI desde una perspectiva de políticas. Sin embargo, en la mayoría de los casos, los permisos y el perfil de riesgo de una aplicación se definen mediante los permisos y perfiles de riesgo de las capacidades que contiene la aplicación. Por ello, en este artículo nos centramos en los permisos y las consideraciones que hay que tener en cuenta a nivel de funcionalidad.

Los permisos que se indican a continuación en mayúscula (por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE) no aparecen en la [documentación para desarrolladores de Microsoft Teams](https://aka.ms/teamsdevdocs) ni en los [permisos para Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Son simplemente una descripción breve para este artículo.


| Título   | Descripción    |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Use las tablas siguientes como guía para comprender qué permisos solicitan las aplicaciones que está investigando.</li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Investigue sobre la aplicación o el servicio para decidir si desea permitir el acceso a ella dentro de su organización. Por ejemplo, los bots envían y reciben mensajes de usuarios y, excepto los bots personalizados de empresa, están ubicados fuera del límite de cumplimiento. Por lo tanto, cualquier aplicación que incluya un bot requiere esos permisos y tiene ese perfil de riesgo, como mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Consideraciones y permisos de aplicación globales

### <a name="required-permissions"></a>Permisos necesarios

Ninguna

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

- Una aplicación debe revelar los datos que usa y para qué se usan en sus términos de uso y vínculos a la directiva de privacidad.

- [El consentimiento específico de](resource-specific-consent.md) los recursos proporciona un conjunto de permisos que las aplicaciones pueden solicitar, que aparece en la pantalla de instalación de la aplicación. Para obtener más información sobre los permisos de consentimiento específicos de recursos, consulte [Referencia de permisos de Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Es posible que las aplicaciones también necesiten permisos que no son permisos de consentimiento específicos de recursos. Una vez instalada una aplicación, es posible que la aplicación solicite permisos de Graph a través de un aviso de consentimiento. Para obtener más información, consulta [Descripción de las experiencias de consentimiento de aplicaciones](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)de Azure AD. Puedes configurar los permisos de la API y el consentimiento en Azure Portal. Para obtener más información, consulte el marco [de consentimiento de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bots y extensiones de mensajería

### <a name="required-permissions"></a>Permisos necesarios

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. El bot puede recibir mensajes de los usuarios y responderles. <sup>1</sup>

- POST_MESSAGE_USER. Después de que un usuario haya enviado un mensaje a un bot, este puede enviar mensajes directos al usuario (también denominados mensajes proactivos *en* cualquier momento).

- GET_CHANNEL_LIST. Los bots agregados a los equipos pueden obtener una lista de nombres e iDs de los canales de un equipo.

### <a name="optional-permissions"></a>Permisos opcionales

- IDENTITY. Cuando se usa en un canal, los bots de la aplicación pueden acceder a la información básica de identidad de los miembros del equipo (nombre, apellidos, nombre principal de usuario [UPN], dirección de correo electrónico). cuando se usa en un chat personal o grupal, el bot puede acceder a la misma información para esos usuarios.

- POST_MESSAGE_TEAM. Permite a los bots de una aplicación enviar mensajes directos (proactivos) a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha hablado con el bot antes.

- Los siguientes no son permisos explícitos, pero están implícitos por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla si un bot puede enviar y recibir archivos en un chat personal (aún no se admite en chats grupales o canales).

### <a name="considerations"></a>Consideraciones

- Los bots solo tienen acceso a los equipos a los que se han agregado o a los usuarios que los han instalado.

- Los bots solo reciben mensajes en los que los usuarios los mencionan explícitamente. Estos datos dejan de la red corporativa.

- Los bots solo pueden responder a las conversaciones en las que se les menciona.

- Después de que un usuario haya chateado con un bot, si el bot almacena el id. de ese usuario, puede enviarle mensajes directos en cualquier momento.

- Es posible que los mensajes de bot contengan vínculos a sitios de suplantación de identidad o malware, pero el usuario, el administrador de inquilinos o Microsoft puede bloquear los bots de forma global.

- Un bot puede recuperar (y puede almacenar) información de identidad muy básica para los miembros del equipo a los que se ha agregado la aplicación, o para usuarios individuales en chats personales o grupales. Para obtener más información sobre estos usuarios, el bot debe requerir que inicien sesión en Azure Active Directory (Azure AD).

- Los bots pueden recuperar (y podrían almacenar) la lista de canales de un equipo; estos datos dejan de la red corporativa.

- Cuando se envía un archivo a un bot, este abandona la red corporativa. El envío y la recepción de archivos requiere la aprobación del usuario para cada archivo. 

- De forma predeterminada, los bots no pueden actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión. tan pronto como el usuario inicia sesión, el bot tendrá un token de acceso con el que puede realizar otras cosas. Exactamente lo que son esas cosas adicionales depende del bot y de dónde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada y puede tener su propio conjunto https://apps.dev.microsoft.com/ de permisos.

- Los bots se informan siempre que los usuarios se agregan a un equipo o se eliminan de él.

- Los bots no ven las direcciones IP de los usuarios ni otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá las direcciones IP de los usuarios y la información del referenciador).

- Por otro lado, las extensiones de mensajería pueden ver las direcciones IP de los usuarios y la información de referencia.

- Las instrucciones de la aplicación (y nuestro proceso de revisión de AppSource) requieren discreción al publicar mensajes de chat personales a los usuarios (mediante POST_MESSAGE_TEAM permiso) para fines válidos. En caso de abuso, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots de forma centralizada si es necesario.

<sup>1</sup> Algunos bots solo envían mensajes (POST_MESSAGE_USER). Se denominan bots de "solo notificación", pero el término no hace referencia a lo que puede o no hacer un bot, significa que el bot no desea exponer una experiencia de conversación. Teams usa este campo para deshabilitar la funcionalidad en la interfaz de usuario que normalmente se habilitaría; el bot no está restringido en lo que está permitido hacer en comparación con los bots que exponen una experiencia de conversación.

<sup>2</sup> Se rige por la propiedad booleana supportsFiles en el objeto bot de la manifest.jsarchivo de la aplicación.

> [!NOTE]
> Si un bot tiene su propio inicio de sesión, hay una segunda experiencia de consentimiento (diferente) la primera vez que el usuario inicia sesión.
>
>Actualmente, los permisos de Azure AD asociados a cualquiera de las funcionalidades dentro de una aplicación de Teams (bot, pestaña, conector o extensión de mensajería) son completamente independientes de los permisos de Teams que se muestran aquí.

## <a name="tabs"></a>Pestañas

Una pestaña es un sitio web que se ejecuta en Teams.

### <a name="required-permissions"></a>Permisos necesarios

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permisos opcionales

Ninguno (actualmente)

### <a name="considerations"></a>Consideraciones

- El perfil de riesgo para una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador. 

- Una pestaña también obtiene el contexto en el que se está ejecutando, incluido el nombre de inicio de sesión y el UPN del usuario actual, el id. de objeto de Azure AD para el usuario actual, el id. del grupo de Microsoft 365 en el que reside (si es un equipo), el id. de inquilino y la configuración regional actual del usuario. Sin embargo, para asignar estos id. a la información de un usuario, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.

## <a name="connectors"></a>Conectores

Un conector publica mensajes en un canal cuando se producen eventos en un sistema externo.

### <a name="required-permissions"></a>Permisos necesarios

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permisos opcionales

REPLYTO_CONNECTOR_MESSAGE. Determinados conectores admiten mensajes que pueden actuar y que permiten a los usuarios publicar respuestas dirigidas en el mensaje del conector, por ejemplo, agregando una respuesta a un problema de GitHub o agregando una fecha a una tarjeta Trello.

### <a name="considerations"></a>Consideraciones

- El sistema que publica los mensajes del conector no sabe quién publica los mensajes ni quién los recibe: no se revela ninguna información sobre el destinatario. (Microsoft es el destinatario real, no el inquilino; Microsoft realiza la publicación real en el canal).

- No hay datos que abandone la red corporativa cuando los mensajes de los conectores se publican en un canal.

- Los conectores que admiten mensajes que pueden actuar (REPLYTO_CONNECTOR_MESSAGE permiso de referencia) tampoco ven la información de la dirección IP ni del autor de la referencia; esta información se envía a Microsoft y, a continuación, se enruta a los puntos de conexión HTTP previamente registrados con Microsoft en el portal Conectores.

- Cada vez que se configura un conector para un canal, se crea una dirección URL única para esa instancia del conector. Si se elimina la instancia del conector, la dirección URL ya no se puede usar.

- Los mensajes del conector no pueden contener archivos adjuntos.

- La dirección URL de instancia del conector debe tratarse como confidencial o secreta: cualquier persona que tenga esa dirección URL puede publicar en ella, como una dirección de correo electrónico. Por lo tanto, hay cierto riesgo de correo no deseado o vínculos a sitios de suplantación de identidad o malware. Si esto fuera posible, los propietarios del equipo pueden eliminar la instancia del conector.

- Si el servicio que envía los mensajes de los conectores se ve comprometida y empieza a enviar vínculos de correo no deseado/suplantación de identidad (phishing/malware), un administrador de inquilinos puede evitar que se creen nuevas instancias de conectores y Microsoft puede bloquearlas de forma centralizada.

> [!NOTE]
> Actualmente no es posible saber qué conectores admiten mensajes que admiten acciones (REPLYTO_CONNECTOR_MESSAGE permiso).

## <a name="outgoing-webhooks"></a>Webhooks salientes

*Los propietarios* del equipo o los miembros del equipo crean los webhooks salientes sobre la marcha. No son capacidades de las aplicaciones de Teams; esta información se incluye para su integridad.

### <a name="required-permissions"></a>Permisos necesarios

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Puede recibir mensajes de usuarios y responderles.

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

- Los webhooks salientes son similares a los bots, pero tienen menos privilegios. Deben mencionarse explícitamente, igual que los bots.

- Cuando se registra un webhook de salida, se genera un secreto, que permite al webhook saliente comprobar que el remitente es Microsoft Teams en lugar de un atacante malintencionado. Este secreto debe permanecer un secreto; cualquier persona que tenga acceso a él puede hacerse pasar por Microsoft Teams. Si el secreto está en peligro, el webhook saliente se puede eliminar y volver a crear y se generará un nuevo secreto.

- Aunque es posible crear un webhook saliente que no valide el secreto, se recomienda usar esta opción.

- Aparte de recibir y responder a mensajes, los webhooks salientes no pueden hacer mucho: no pueden enviar mensajes de manera proactiva, no pueden enviar o recibir archivos, no pueden hacer nada más que los bots pueden hacer excepto recibir y responder mensajes.
