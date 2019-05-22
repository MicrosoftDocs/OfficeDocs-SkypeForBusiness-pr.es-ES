---
title: Consideraciones y permisos de las aplicaciones de Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Vea qué datos y permisos están solicitando las aplicaciones de su organización.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: b99507dcb37d86879bd495655da3d6f88a06f64a
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344736"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y permisos de las aplicaciones de Microsoft Teams

Las aplicaciones de Microsoft Teams son una forma de agregar una o varias funcionalidades en un _paquete de aplicaciones_ que se pueden instalar, actualizar y desinstalar. Las funcionalidades incluyen:

-   Bots
-   Extensiones de mensajería
-   Fichas
-   Conectores

Los usuarios tienen que dar su consentimiento a las aplicaciones y su administración corre a cargo de los departamentos de TI desde una perspectiva de políticas. Sin embargo, en la mayoría de los casos, los perfiles de riesgo y los permisos de las funcionalidades que contiene una aplicación definen su perfil de riesgo y sus permisos. Por ello, en este artículo nos centramos en los permisos y las consideraciones que hay que tener en cuenta a nivel de funcionalidad.

Los permisos que se indican a continuación en mayúscula (por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE) no aparecen en la [documentación para desarrolladores de Microsoft Teams](https://aka.ms/teamsdevdocs) ni en los [permisos para Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Son simplemente una descripción breve para este artículo.


|    |     |
|-----------|------------|
| ![Un icono que muestra un punto de decisión](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Use las tablas siguientes como guía para comprender qué permisos solicitan las aplicaciones que está investigando.</li></ul> |
| ![Un icono que muestra el siguiente paso](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>Investigue la aplicación o el servicio para decidir si desea permitir el acceso a él dentro de su organización. Por ejemplo, los bots envían y reciben mensajes de los usuarios y, excepto los bots de línea de negocios empresariales, se encuentran fuera del límite de cumplimiento. Por lo tanto, cualquier aplicación que incluya un bot necesitará esos permisos y tendrá ese perfil de riesgo, como mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Permisos de aplicación global y consideraciones

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">Ninguna</td>
    <td valign="top">Ninguna</td>
    <td valign="top">Una aplicación debe revelar los datos que utiliza y los datos que se usan en las condiciones de uso y los vínculos de la política de privacidad.</td>
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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. El bot puede recibir mensajes de los usuarios y responderlos. <sup>1</sup></li><li>POST_MESSAGE_USER. Después de que un usuario ha enviado un mensaje a un bot, el bot puede enviarle mensajes directos (también llamados <em>mensajes</em>proactivos) en cualquier momento.</li><li>GET_CHANNEL_LIST. Los bots agregados a teams pueden obtener una lista de nombres e identificadores de los canales de un equipo.</li></ul></td>
    <td valign="top"><ul><li>Identificar. Cuando se usa it& # 39; en un canal, los bots de app& # 39; s pueden acceder a la información de identidad básica de los miembros del equipo (nombre, apellido, nombre principal de usuario [UPN], dirección de correo electrónico); Cuando se usa it& # 39; en un chat grupal o personal, el bot puede acceder a la misma información para esos usuarios.</li><li> POST_MESSAGE_TEAM. Permite a los bots de app& # 39; s enviar mensajes directos (proactivos) a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha hablado con el bot.</li><li>Los siguientes son permisos explícitos, pero están implícitos en RECEIVE_MESSAGE y REPLYTO_MESSAGE y en los ámbitos en los que se pueden usar los bots, que se declaran en el manifiesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. <sup>3</sup> controla si un bot puede enviar y recibir archivos en un chat personal (aún no es compatible con el chat o los canales grupales).</li></ul></td>
    <td valign="top"><ul><li>Los bots solo tienen acceso a los equipos a los que se ha agregado they& # 39; o a los usuarios que los han instalado.</li><li>Los bots solo reciben mensajes en los que they& # 39; lo mencionan los usuarios de forma explícita. Estos datos salen de la red corporativa.</li><li>    Los bots solo pueden responder a conversaciones en las que they& # 39; se mencionó.</li><li>Después de que un usuario haya desverso con un bot, si el bot almacena ese user& # 39; s ID, podrá enviarle mensajes directos en cualquier momento. </li><li>Teóricamente es posible que los mensajes de bot contengan vínculos a sitios de suplantación de identidad o malware, pero el usuario puede bloquear los bots, el administrador de inquilinos o globalmente por Microsoft. </li><li>Un bot puede recuperar (y posiblemente almacenar) información de identidad muy básica para los miembros del equipo a los que se ha agregado la aplicación o para usuarios individuales de chats personales o grupales. Para obtener más información sobre estos usuarios, el bot debe pedirles que inicien sesión en Azure Active Directory (Azure AD). </li><li>Los bots pueden recuperar (y posiblemente almacenar) la lista de canales de un equipo; Estos datos salen de la red corporativa. </li><li>Cuando se envía un archivo a un bot, el archivo deja la red corporativa. El envío y la recepción de archivos requiere la aprobación del usuario para cada archivo. </li><li>De forma predeterminada, los bots don& # 39; t tienen la capacidad de actuar en nombre del usuario, pero los bots pueden pedir a los usuarios que inicien sesión; tan pronto como el usuario inicia sesión, Bot tendrá un token de acceso con el que puede hacer cosas adicionales. El significado exacto de estas acciones adicionales depende del bot y del lugar donde el usuario inicia sesión: un bot es una aplicación de Azure <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> ad registrada en y puede tener su propio conjunto de permisos.</li><li>Los bots se comunican siempre que se agregan o eliminan usuarios de un equipo.</li><li>Bots don& # 39; t vea users& # 39; Direcciones IP u otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: Si un bot implementa su propia experiencia de inicio de sesión, la interfaz de usuario de inicio de sesión verá users& # 39; Direcciones IP e información de referencia.)</li><li>Las extensiones de mensajería, por otra parte, hacen ver users& # 39; Direcciones IP e información de referencia.</li><li>Las directrices de la aplicación (y nuestro proceso de revisión de AppSource) requieren la necesidad de publicar mensajes de conversaciones personales a los usuarios (mediante el permiso POST_MESSAGE_TEAM) para propósitos válidos. En caso de abusos, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots de forma centralizada si es necesario.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Algunos Bots solo envían mensajes (POST_MESSAGE_USER). They& # 39; volvió a &quot;llamar bots de&quot; solo notificación, pero el término doesn& # 39; t hace referencia a lo que se permite o no se permite a un bot, esto significa que el bot doesn& # 39; t desea exponer una experiencia de conversación. Teams usa este campo para deshabilitar la funcionalidad en la interfaz de usuario que normalmente se habilitaría; el bot isn& # 39; t restringido en lo que it& ha permitido hacer en comparación con bots que exponen una experiencia de conversación.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Actualmente en Developer Preview.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Regido por la <code>supportsFiles</code> propiedad booleana en el objeto bot en el archivo manifest. JSON de la aplicación.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un bot tiene su propio inicio de sesión, hay una segunda, distinta, experiencia de consentimiento la primera vez que el usuario inicia sesión.</li><li>Por el momento, los permisos de Azure AD asociados con cualquiera de las funciones dentro de una aplicación de Teams (bot, Tab, conector o extensión de mensajería) son totalmente independientes de los permisos de teams que se muestran aquí.</li></ul>


## <a name="tabs"></a>Pestañas

Una pestaña es un sitio web que se ejecuta dentro de Teams.

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Ninguno (actualmente).</td>
    <td valign="top"><ul><li>El perfil de riesgo para una pestaña es casi idéntico al mismo sitio web que se ejecuta en una pestaña del explorador. </li><li>Una pestaña también obtiene el contexto en el que se ejecuta it& # 39; s, incluido el nombre de inicio de sesión y el UPN del usuario actual, el identificador de objeto de Azure AD para el usuario actual, el identificador del grupo de Office 365 en el que reside (si es un equipo) , el identificador de inquilino y la configuración regional actual del usuario. Sin embargo, para asignar estos identificadores a la información de user& # 39;, la pestaña tendría que hacer que el usuario inicie sesión en Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Los

Un conector envía mensajes a un canal cuando se producen eventos en un sistema externo.

  <table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Algunos conectores admiten <em>mensajes accionables</em>, que permiten a los usuarios publicar respuestas dirigidas al mensaje del conector, por ejemplo, agregando una respuesta a un problema de Github o agregando una fecha a una tarjeta de Trello.</td>
    <td valign="top"><ul><li>El sistema que envía los mensajes del conector doesn& # 39; t saber quién it& # 39; en o quién recibe los mensajes: no se revela información sobre el destinatario. (Microsoft es el destinatario real, no el inquilino; Microsoft realiza la entrada de datos en el canal.</li><li>Ningún dato deja la red corporativa cuando los mensajes del conector se envían a un canal.</li><li>Los conectores que admiten mensajes accionables (permiso REPLYTO_CONNECTOR_MESSAGE) también don& # 39; t ver la dirección IP y la información de referencia; Esta información se envía a Microsoft y, a continuación, se enrutan a puntos de conexión HTTP previamente registrados con Microsoft en el portal de conectores.</li><li>Cada vez que se configura un conector para un canal, se crea una dirección URL única para la instancia del conector. Si la instancia del conector se elimina, la dirección URL ya no se puede usar.</li><li>Los mensajes del conector can& # 39; t contienen datos adjuntos.</li><li>La dirección URL de la instancia de conector debe ser tratada como secreto/confidencial: cualquier persona que tenga esa dirección URL puede publicar en ella, como una dirección de correo electrónico. Por lo tanto, there& # 39; es un riesgo de correo no deseado o vínculos a sitios de suplantación de identidad o malware. Si esto ocurriera, los propietarios del equipo pueden eliminar la instancia del conector.</li><li>Si el servicio que envía los mensajes del conector se viera comprometido y comienza a enviar vínculos de correo no deseado/suplantación de identidad, un administrador de inquilinos puede evitar que se creen nuevas instancias del conector y Microsoft puede bloquearlas de forma centralizada.</li></ul></td>
  </tr>
</table>

> [!Note]
> En la actualidad, no es posible saber qué conectores admiten mensajes accionables (permiso REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks salientes

Los encargados de los equipos o los miembros del equipo crean directamente los _enlaces_ a través de la misma si se habilita la transferencia local para un inquilino. No son funciones de las aplicaciones de Teams; Esta información se incluye para completar.

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Permite recibir mensajes de los usuarios y responderlos.</td>
    <td valign="top">Ninguna</td>
    <td valign="top"><ul><li>Los enlaces de correo no deseados son similares a los bots, pero tienen menos privilegios. Deben mencionarse explícitamente, como bots.</li><li>Cuando se registra un webhook saliente, se genera un <em>secreto</em> , lo que permite al enlazór saliente comprobar que el remitente es Microsoft Teams y no un atacante malintencionado. Este secreto debe ser secreto; cualquier persona que tenga acceso a ella puede suplantar a Microsoft Teams. Si el secreto se ve comprometido, el webhook saliente se puede eliminar y volver a crear, y se generará un nuevo secreto.</li><li>Aunque it& # 39; s es posible crear un enlace webhook saliente que doesn& # 39; no validar el secreto, le recomendamos que lo asegúrese.</li><li>Aparte de recibir y responder a los mensajes, los enlaces webhooks salientes can& # 39; t hace mucho: can& # 39; t envía mensajes proactivamente, can& # 39; t envía o recibe archivos, ellos can& # 39; t hacer cualquier otra cosa que los bots puedan hacer excepto recibir y responder mensajes.</li></ul></td>
  </tr>
</table>
