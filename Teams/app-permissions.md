---
title: Consideraciones y permisos de las aplicaciones de Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_PracticalGuidance
search.appverid: MET150
ms.reviewer: lehewe
description: Vea qué datos y permisos están solicitando las aplicaciones de su organización.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 960f54f27b7019d15d287c637c7c58f73dfdef0f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014190"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y permisos de las aplicaciones de Microsoft Teams

Aplicaciones de Microsoft Teams son una forma de agregar una o más funciones en un _paquete de la aplicación_ que se pueden instalar, actualizar y desinstalar. Las capacidades incluyen:

-   Bots
-   Extensiones de mensajería
-   Fichas
-   Conectores

Aplicaciones son aceptadas por los usuarios y administradas por TI desde una perspectiva de la directiva. Sin embargo, la mayor parte, permisos y el perfil de riesgo de una aplicación se definen por los permisos y los perfiles de riesgo de las capacidades que lo contiene. Por lo tanto, en este artículo se centra en los permisos y consideraciones en el nivel de capacidad.

Los permisos enumerados a continuación en las letras en mayúscula, por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE, no aparecen en cualquier lugar en la [documentación para desarrolladores de equipos de Microsoft](https://aka.ms/teamsdevdocs) o los [permisos de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Son simplemente una forma abreviada descriptiva a efectos de este artículo.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Use las tablas siguientes como una guía para saber qué permisos solicitan las aplicaciones que está investigando.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>La aplicación de la investigación o propio para decidir si desea permitir el acceso a ella dentro de la organización de servicio. Por ejemplo, bots enviar y recibir mensajes de usuarios, y, excepto bots de línea de negocio de empresa: se encuentran fuera del límite de cumplimiento. Por lo tanto, cualquier aplicación que incluya un bot requiere los permisos de dichos y tiene ese perfil de riesgo, como mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Consideraciones y permisos globales de aplicaciones

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">Ninguno</td>
    <td valign="top">Ninguno</td>
    <td valign="top">Una aplicación debe revelar qué datos utiliza y qué datos se usan para incluirlos en los vínculos de las condiciones de uso y la política de privacidad.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots y extensiones de mensajería

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. El robot puede recibir mensajes de los usuarios y responder a ellos. <sup>1</sup></li><li>POST_MESSAGE_USER. Después de que un usuario envía un mensaje a un robot, el robot puede enviar al usuario mensajes directos (también denominados _mensajes proactivos_) en cualquier momento.</li><li>GET_CHANNEL_LIST. Bots agregados a los equipos pueden obtener una lista de nombres e identificadores de los canales en un equipo.</li></ul></td>
    <td valign="top"><ul><li>IDENTIDAD. Cuando se usa en un canal, bots de la aplicación puede tener acceso a información básica de identidad de los miembros del equipo (nombre, apellidos, nombre principal de usuario [UPN], dirección de correo electrónico); Cuando se usa en un chat personal o de grupo, el robot puede tener acceso a la misma información para esos usuarios.</li><li> POST_MESSAGE_TEAM. Permite bots de una aplicación enviar mensajes de (proactivos) directos a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha tratado el robot antes.</li><li>Los siguientes no son permisos explícitos, sino que están implícitos en RECEIVE_MESSAGE y REPLYTO_MESSAGE, y en los ámbitos en los que los bots se pueden usar, declarados en el manifiesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Controla si un bot puede enviar y recibir archivos en un chat personal (aún no es compatible con chats grupales ni canales).</li></ul></td>
    <td valign="top"><ul><li>Los bots solo tienen acceso a los equipos en los que se han agregado o a los usuarios que los han agregado.</li><li>Bots sólo reciben mensajes en el que está menciona explícitamente por los usuarios. Estos datos dejan la red corporativa.</li><li>    Los bots solo pueden responder a conversaciones en las que se les mencione.</li><li>Cuando un usuario termina la conversación con un bot, si el bot almacena el Id. de ese usuario, puede enviar mensajes directos a ese usuario en cualquier momento. </li><li>Teóricamente es posible que los mensajes de los bots contengan vínculos a sitios de suplantación de identidad o malware, pero el usuario, el administrador de inquilinos o Microsoft en general pueden bloquear los bots. </li><li>Un robot puede recuperar (y es posible que almacenar) información de identidad muy básica para la aplicación se ha agregado a los miembros del equipo, o para usuarios individuales en chats personales o de grupo. Para obtener más información acerca de estos usuarios, el robot debe requerir que inicien sesión Azure Active Directory (AD Azure). </li><li>Los bots pueden recuperar (y podrían almacenar) la lista de canales de un equipo; estos datos abandonan la red corporativa. </li><li>Cuando se envía un archivo a un robot, el archivo sale de la red corporativa. Enviar y recibir archivos requieren la aprobación del usuario para cada archivo. </li><li>De forma predeterminada, bots no tienen la capacidad de actuar en nombre del usuario, pero bots puede pedir a los usuarios para iniciar sesión; tan pronto como el usuario inicia sesión, el robot tendrá un token de acceso con la que pueden realizar acciones adicionales. ¿Cuáles son los aspectos adicionales depende el robot y donde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada en <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> y puede tener su propio conjunto de permisos.</li><li>A los bots se les informa cuando a los usuarios se les agrega a un equipo o se eliminan de uno.</li><li>Bots no ve las direcciones IP de los usuarios u otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, el inicio de sesión de la interfaz de usuario verán las direcciones IP de los usuarios y la información de referencia.)</li><li>Por otro lado, las extensiones de mensajería ven las direcciones IP de los usuarios y la información del origen de referencia.</li><li>Instrucciones de la aplicación (y nuestro proceso de revisión AppSource) requieren discreción en mensajes de chat personal de contabilización a los usuarios (mediante el permiso POST_MESSAGE_TEAM) para fines válidos. En caso de infracción, los usuarios pueden bloquear el robot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots centralmente si es necesario.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Algunos bots sólo envían mensajes (POST_MESSAGE_USER). Se llaman bots "sólo de notificación", pero el término no hace referencia a un componente de qué está permitido o no permitido hacer, significa que no desea que el robot exponer una experiencia familiar. Los equipos utiliza este campo para deshabilitar la funcionalidad de la interfaz de usuario que normalmente se habilitados; el robot no está restringido en lo que se permite para hacer en comparación con bots que exponen una experiencia familiar.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">En este momento en Developer Preview.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Actualmente en vista previa para desarrolladores. Regirá la <code>supportsFiles</code> propiedad booleana en el objeto de componente en el archivo manifest.json para la aplicación.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un bot tiene su propio inicio de sesión, existe una segunda experiencia de consentimiento (distinta) la primera vez que el usuario inicia sesión.</li><li>En este momento, los permisos de Azure AD asociados con algunas de las funcionalidades dentro de la aplicación de Teams (bot, ficha, conector o extensión de mensajería) son completamente independientes de los permisos de Teams que se enumeran aquí.</li></ul>


## <a name="tabs"></a>Fichas

Una ficha es un sitio web que se ejecuta dentro de Teams.

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Ninguno (por ahora).</td>
    <td valign="top"><ul><li>El perfil de riesgo de una ficha es prácticamente el mismo que el de ese mismo sitio web cuando se ejecuta en una ficha de navegador. </li><li>Una ficha también obtiene el contexto en el que se está ejecutando, incluido el nombre de inicio de sesión y UPN del usuario actual, el objeto de AD de Azure el identificador para el usuario actual, el identificador de la de Office 365 grupo (equipo) en el que reside, el identificador de inquilino y la configuración regional actual del usuario. Sin embargo, para asignar estos identificadores a la información de un usuario, puede que la ficha tendría que hacer que el usuario inicie sesión en Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Conectores

Un conector publica mensajes en un canal cuando se producen eventos en un sistema externo.

  <table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Ciertos conectores admiten _los mensajes que se pueden procesar_, que permiten a los usuarios registrar respuestas de destinadas en el mensaje de conector, por ejemplo agregando una respuesta a un problema de depósito o una fecha en una tarjeta de Trello.</td>
    <td valign="top"><ul><li>El sistema que registra los mensajes de conector no sabe quién es registro a o quién recibe los mensajes: no hay información acerca del destinatario se revela. (Microsoft es el destinatario real, no el inquilino; Microsoft lo hace la entrada real en el canal.)</li><li>Ningún dato abandona la red corporativa cuando los mensajes del conector se publican en un canal.</li><li>Los conectores que admiten mensajes que permiten ejecutar acciones (permiso REPLYTO_CONNECTOR_MESSAGE) tampoco ven la dirección IP ni la información del origen de referencia; esta información se envía a Microsoft y después se enruta a los puntos de conexión HTTP que se habían registrado anteriormente con Microsoft en el portal de conectores.</li><li>Cada vez que un conector está configurado para un canal, se crea una dirección URL única para esa instancia del conector. Si esa instancia del conector se elimina, ya no se puede usar la dirección URL.</li><li>Los mensajes del conector no pueden contener adjuntos de archivo.</li><li>La instancia del conector dirección URL debe tratarse como secreto/confidencial: cualquier persona que tiene que puede registrar la dirección URL a él, como una dirección de correo electrónico. Por lo tanto, hay algunos riesgos de correo no deseado o vínculos a sitios de suplantación de identidad o malware. Si estaban a que se produzca, los propietarios de equipo pueden eliminar la instancia del conector.</li><li>Si el servicio que envía los mensajes del conector estuviera en peligro y comenzara a enviar vínculos a spam/suplantación de identidad/malware, un administrador de inquilino podría evitar que se crearan nuevas instancias del conector y que Microsoft lo bloqueara de forma central.</li></ul></td>
  </tr>
</table>

> [!Note]
> Por ahora, no es posible saber qué conectores admiten mensajes que permiten realizar acciones (permiso REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks salientes

_Webhooks saliente_ se crean sobre la marcha por los propietarios del equipo o los miembros del equipo si sideloading está habilitada para un inquilino. No son las capacidades de las aplicaciones de los equipos; Esta información se incluye para más precisión.

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Puede recibir mensajes de los usuarios y responder a ellos.</td>
    <td valign="top">Ninguno</td>
    <td valign="top"><ul><li>Webhooks salientes son similares a bots pero tiene menos privilegios. Debe ser explícitamente se ha mencionado, al igual que de bots.</li><li>Cuando se registra un webhook saliente, se genera un _secreto_ , lo que permite el webhook saliente comprobar que el remitente es Microsoft Teams en contraposición a un atacante malintencionado. Este secreto debe permanecer un secreto; Microsoft Teams puede suplantar a cualquier persona que tiene acceso a ella. Si el secreto se ve comprometido, puede eliminarse y vuelve a crear la webhook saliente, y se generará un nuevo secreto.</li><li>Si bien es posible crear un webhook saliente que no valide el secreto, no lo recomendamos.</li><li>Aparte de recibir y responder mensajes, los webhooks salientes no pueden hacer mucho más: no pueden enviar mensajes de forma proactiva, no pueden enviar ni recibir archivos, no pueden hacer nada que los bots no puedan, a excepción de recibir y responder mensajes.</li></ul></td>
  </tr>
</table>