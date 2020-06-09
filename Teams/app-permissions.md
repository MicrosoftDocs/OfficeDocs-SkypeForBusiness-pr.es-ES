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
description: Administrador puede saber qué datos y permisos solicitan las aplicaciones de Microsoft Teams de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d2e43c3125421189303d106cfd3bdde66815309
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44611019"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y permisos de las aplicaciones de Microsoft Teams

Las aplicaciones de Microsoft Teams son una forma de agregar una o varias funcionalidades en un _paquete de aplicaciones_ que se pueden instalar, actualizar y desinstalar. Las funcionalidades incluyen:

- Bots
- Extensiones de mensajería
- Fichas
- Conectores

Los usuarios tienen que dar su consentimiento a las aplicaciones y su administración corre a cargo de los departamentos de TI desde una perspectiva de políticas. Sin embargo, en la mayoría de los elementos, los permisos y el perfil de riesgo de una aplicación se definen por los permisos y perfiles de riesgo de las capacidades que contiene la aplicación. Por ello, en este artículo nos centramos en los permisos y las consideraciones que hay que tener en cuenta a nivel de funcionalidad.

Los permisos que se indican a continuación en mayúscula (por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE) no aparecen en la [documentación para desarrolladores de Microsoft Teams](https://aka.ms/teamsdevdocs) ni en los [permisos para Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Son simplemente una descripción breve para este artículo.


|    |     |
|-----------|------------|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Use las tablas siguientes como guía para comprender qué permisos solicitan las aplicaciones que está investigando.</li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Investigue la aplicación o el servicio para decidir si desea permitir el acceso a él dentro de su organización. Por ejemplo, los bots envían y reciben mensajes de los usuarios y, excepto los bots personalizados de empresa, se encuentran fuera del límite de cumplimiento. Por lo tanto, cualquier aplicación que incluya un bot necesitará esos permisos y tendrá ese perfil de riesgo, como mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Permisos de aplicación global y consideraciones

### <a name="required-permissions"></a>Permisos necesarios

Ninguno

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

- Una aplicación debe revelar los datos que utiliza y los datos que se usan en las condiciones de uso y los vínculos de la política de privacidad.

- El [consentimiento específico de recursos](resource-specific-consent.md) proporciona un conjunto de permisos que las aplicaciones pueden solicitar, que aparece en la pantalla de instalación de la aplicación. Para obtener más información sobre los permisos de consentimiento específicos de un recurso, consulte [referencia de permisos de Graph](https://docs.microsoft.com/graph/permissions-reference).

- Las aplicaciones también pueden necesitar permisos distintos de los permisos de consentimiento específicos de recursos. Después de instalar una aplicación, es posible que la aplicación solicite permisos de grafos a través de una solicitud de consentimiento. Para obtener más información, consulta las experiencias de consentimiento de la [aplicación Azure ad](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience). Puede configurar permisos de API y el consentimiento en el portal de Azure. Para obtener más información, consulte [marco de trabajo de consentimiento de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots y extensiones de mensajería

### <a name="required-permissions"></a>Permisos necesarios

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. El bot puede recibir mensajes de los usuarios y responderlos. <sup>1</sup>

- POST_MESSAGE_USER. Después de que un usuario ha enviado un mensaje a un bot, el bot puede enviarle mensajes directos (también denominados *mensajes proactivos* en cualquier momento).

- GET_CHANNEL_LIST. Los bots agregados a teams pueden obtener una lista de nombres e identificadores de los canales de un equipo.

### <a name="optional-permissions"></a>Permisos opcionales

- Identificar. Cuando se usa en un canal, los bots de la aplicación pueden acceder a la información de identidad básica de los miembros del equipo (nombre, apellido, nombre principal de usuario [UPN], dirección de correo electrónico); Cuando se usa en un chat grupal o personal, el bot puede acceder a la misma información para esos usuarios.

- POST_MESSAGE_TEAM. Permite que los bots de una aplicación envíen mensajes directos (proactivos) a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca antes ha hablado con el bot.

- Los siguientes elementos no son permisos explícitos, pero están implícitos en RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en los que se pueden usar los bots, declarados en el manifiesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> controla si un bot puede enviar y recibir archivos en un chat personal (aún no es compatible con las conversaciones grupales o los canales).

### <a name="considerations"></a>Consideraciones

- Los bots solo tienen acceso a los equipos a los que se han agregado o a los usuarios que los han instalado.

- Los bots solo reciben mensajes en los que los usuarios los mencionan explícitamente. Estos datos salen de la red corporativa.

- Los bots solo pueden responder a las conversaciones en las que se mencionan.

- Después de que un usuario haya reverso con un bot, si el bot almacena el identificador de ese usuario, puede enviarle mensajes directos en cualquier momento.

- Teóricamente es posible que los mensajes de bot contengan vínculos a sitios de suplantación de identidad o malware, pero el usuario puede bloquear los bots, el administrador de inquilinos o globalmente por Microsoft.

- Un bot puede recuperar (y posiblemente almacenar) información de identidad muy básica para los miembros del equipo a los que se ha agregado la aplicación o para usuarios individuales de chats personales o grupales. Para obtener más información sobre estos usuarios, el bot debe pedirles que inicien sesión en Azure Active Directory (Azure AD).

- Los bots pueden recuperar (y posiblemente almacenar) la lista de canales de un equipo; Estos datos salen de la red corporativa.

- Cuando se envía un archivo a un bot, el archivo deja la red corporativa. El envío y la recepción de archivos requiere la aprobación del usuario para cada archivo. 

- De forma predeterminada, los bots no tienen la capacidad de actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión; tan pronto como el usuario inicia sesión, Bot tendrá un token de acceso con el que puede hacer cosas adicionales. El significado exacto de estas acciones adicionales depende del bot y del lugar donde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada en https://apps.dev.microsoft.com/ y puede tener su propio conjunto de permisos.

- Los bots se comunican siempre que se agregan o eliminan usuarios de un equipo.

- Los bots no ven las direcciones IP de los usuarios ni otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: Si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá las direcciones IP de los usuarios y la información de referencia.)

- Las extensiones de mensajería, por otra parte, ven las direcciones IP de los usuarios y la información de referencia.

- Las directrices de la aplicación (y nuestro proceso de revisión de AppSource) requieren la necesidad de publicar mensajes de conversaciones personales a los usuarios (a través del permiso de POST_MESSAGE_TEAM) para propósitos válidos. En caso de abusos, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots de forma centralizada si es necesario.

<sup>1</sup> algunos Bots solo envían mensajes (POST_MESSAGE_USER). Se denominan bots "solo de notificación", pero el término no se refiere a lo que se permite o no se permite a un bot, esto significa que bot no quiere exponer una experiencia de conversación. Teams usa este campo para deshabilitar la funcionalidad en la interfaz de usuario que normalmente se habilitaría; el bot no está restringido en lo que se permite hacer en comparación con los bots que exponen una experiencia de conversación.

<sup>2</sup> regido por la propiedad booleana supportsFiles en el objeto bot en el archivo manifest. JSON de la aplicación.

> [!NOTE]
> Si un bot tiene su propio inicio de sesión, hay una segunda, distinta, experiencia de consentimiento la primera vez que el usuario inicia sesión.
>
>Por el momento, los permisos de Azure AD asociados con cualquiera de las funciones dentro de una aplicación de Teams (bot, Tab, conector o extensión de mensajería) son totalmente independientes de los permisos de teams que se muestran aquí.

## <a name="tabs"></a>Pestañas

Una pestaña es un sitio web que se ejecuta dentro de Teams.

### <a name="required-permissions"></a>Permisos necesarios

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permisos opcionales

Ninguno (actualmente)

### <a name="considerations"></a>Consideraciones

- El perfil de riesgo para una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador. 

- Una pestaña también obtiene el contexto en el que se ejecuta, incluido el nombre de inicio de sesión y el UPN del usuario actual, el identificador de objeto de Azure AD para el usuario actual, el identificador del grupo de Microsoft 365 en el que reside (si es un equipo), el identificador de inquilino y la configuración regional actual del usuario. Sin embargo, para asignar estos identificadores a la información de un usuario, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.

## <a name="connectors"></a>Conectores

Un conector envía mensajes a un canal cuando se producen eventos en un sistema externo.

### <a name="required-permissions"></a>Permisos necesarios

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permisos opcionales

REPLYTO_CONNECTOR_MESSAGE. Algunos conectores admiten mensajes accionables, que permiten a los usuarios publicar respuestas dirigidas al mensaje del conector, por ejemplo, agregando una respuesta a un problema de GitHub o agregando una fecha a una tarjeta de Trello.

### <a name="considerations"></a>Consideraciones

- El sistema que incluye los mensajes del conector no sabe con quién se está publicando o quién recibe los mensajes: no se revela información sobre el destinatario. (Microsoft es el destinatario real, no el inquilino; Microsoft realiza la entrada de datos en el canal.

- Ningún dato deja la red corporativa cuando los mensajes del conector se envían a un canal.

- Los conectores que admiten mensajes accionables (REPLYTO_CONNECTOR_MESSAGE permiso) tampoco ven la dirección IP y la información de referencia; Esta información se envía a Microsoft y, a continuación, se enrutan a puntos de conexión HTTP previamente registrados con Microsoft en el portal de conectores.

- Cada vez que se configura un conector para un canal, se crea una dirección URL única para la instancia del conector. Si la instancia del conector se elimina, la dirección URL ya no se puede usar.

- Los mensajes del conector no pueden contener archivos adjuntos.

- La dirección URL de la instancia de conector debe ser tratada como secreto/confidencial: cualquier persona que tenga esa dirección URL puede publicar en ella, como una dirección de correo electrónico. Por lo tanto, existe un riesgo de correo no deseado o vínculos a sitios de suplantación de identidad o malware. Si esto ocurriera, los propietarios del equipo pueden eliminar la instancia del conector.

- Si el servicio que envía los mensajes del conector se viera comprometido y comienza a enviar vínculos de correo no deseado/suplantación de identidad, un administrador de inquilinos puede evitar que se creen nuevas instancias del conector y Microsoft puede bloquearlas de forma centralizada.

> [!NOTE]
> En la actualidad, no es posible saber qué conectores admiten mensajes accionables (REPLYTO_CONNECTOR_MESSAGE permiso).

## <a name="outgoing-webhooks"></a>Webhooks salientes

Los encargados del equipo o los miembros del equipo crean sobre la marcha los *enlaces* . No son funciones de las aplicaciones de Teams; Esta información se incluye para completar.

### <a name="required-permissions"></a>Permisos necesarios

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Permite recibir mensajes de los usuarios y responderlos.

### <a name="optional-permissions"></a>Permisos opcionales

Ninguna

### <a name="considerations"></a>Consideraciones

- Los enlaces de correo no deseados son similares a los bots, pero tienen menos privilegios. Deben mencionarse explícitamente, como bots.

- Cuando se registra un webhook saliente, se genera un secreto, lo que permite al enlazór saliente comprobar que el remitente es Microsoft Teams y no un atacante malintencionado. Este secreto debe ser secreto; cualquier persona que tenga acceso a ella puede suplantar a Microsoft Teams. Si el secreto se ve comprometido, el webhook saliente se puede eliminar y volver a crear, y se generará un nuevo secreto.

- Aunque es posible crear un webhook saliente que no valide el secreto, le recomendamos.

- Aparte de recibir y responder a los mensajes, los webhooks salientes no pueden hacer mucho: no pueden enviar mensajes de manera proactiva, no pueden enviar ni recibir archivos, no pueden hacer nada más que los bots puedan hacer, excepto recibir y responder a los mensajes.
