---
title: Consideraciones y permisos de las aplicaciones de Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: lehewe
description: Vea qué datos y permisos están solicitando las aplicaciones de su organización.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c7394690cc59ce56e22fcc94076d5a90800c850
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460295"
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
| ![](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>Use las tablas siguientes como una guía para saber qué permisos solicitan las aplicaciones que está investigando.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>Investigue la aplicación o el servicio en sí para decidir si quiere concederle acceso dentro de su organización. Por ejemplo, los bots envían mensajes a los usuarios y los reciben de ellos y, a excepción de los bots de líneas de negocio de la empresa, se encuentran fuera de los límites de cumplimiento normativo. Por lo tanto, la aplicación que incluya un bot requerirá esos permisos y tendrá ese perfil de riesgo, como mínimo. </li></ul>|

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. El bot puede recibir mensajes de los usuarios y responder a ellos.<sup>1</sup></li><li>POST_MESSAGE_USER. Cuando un usuario envía un mensaje a un bot, este puede enviar mensajes directos al usuario (también llamados <em>mensajes proactivos</em>) en cualquier momento.</li><li>GET_CHANNEL_LIST. Los bots que se agregan a los equipos pueden obtener una lista de nombres e identificadores de los canales de un equipo.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY. Cuando it& #39; s utiliza en un canal, el app& #39; bots s puede tener acceso a información básica de identidad de los miembros del equipo (nombre, apellidos, nombre principal de usuario [UPN], dirección de correo electrónico); Cuando it& #39; s utilizado en un personal o conversaciones en grupo, el robot puede tener acceso a la misma información para esos usuarios.</li><li> POST_MESSAGE_TEAM. Permite un app& #39; bots s para enviar mensajes de (proactivos) directos a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha tratado el robot antes.</li><li>Los siguientes no son permisos explícitos, sino que están implícitos en RECEIVE_MESSAGE y REPLYTO_MESSAGE, y en los ámbitos en los que los bots se pueden usar, declarados en el manifiesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Controla si un bot puede enviar y recibir archivos en un chat personal (aún no es compatible con chats grupales ni canales).</li></ul></td>
    <td valign="top"><ul><li>Bots sólo tienen acceso a los equipos a qué they& #39; ve sido agregado o a los usuarios que tengan instalado en ellos.</li><li>Bots sólo reciben mensajes de en qué they& #39; re mencionan explícitamente por los usuarios. Estos datos abandonan la red corporativa.</li><li>    Bots sólo puede responder a las conversaciones de en qué they& #39; re mencionado.</li><li>Después de un usuario ha conversed con un robot, si el robot almacena ese user& #39; s identificador, pueden enviar a ese usuario dirigir los mensajes en cualquier momento. </li><li>Teóricamente es posible que los mensajes de los bots contengan vínculos a sitios de suplantación de identidad o malware, pero el usuario, el administrador de inquilinos o Microsoft en general pueden bloquear los bots. </li><li>Un bot puede recuperar (y podría almacenar) información de identidad muy básica de los miembros del equipo que se hayan agregado a la aplicación o de los usuarios individuales en chats personales o grupales. Para ver más información de estos usuarios, el bot debe pedirles que inicien sesión en Azure Active Directory (Azure AD). </li><li>Los bots pueden recuperar (y podrían almacenar) la lista de canales de un equipo; estos datos abandonan la red corporativa. </li><li>Cuando se envía un archivo a un bot, el archivo abandona la red corporativa. El envío y la recepción de archivos requiere la aprobación del usuario para cada archivo. </li><li>De forma predeterminada, bots don& #39; t tienen la capacidad de actuar en nombre del usuario, pero bots puede pedir a los usuarios para iniciar sesión; tan pronto como el usuario inicia sesión, el robot tendrá un token de acceso con la que pueden realizar acciones adicionales. Qué acciones adicionales se pueden hacer dependerá del bot y de dónde inicia sesión el usuario: un bot es una aplicación de Azure AD registrada en <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> y que puede tener su propio conjunto de permisos.</li><li>A los bots se les informa cuando a los usuarios se les agrega a un equipo o se eliminan de uno.</li><li>Bots don& #39; t vea users& #39; Direcciones IP u otra información de referencia. Toda la información procede de Microsoft. (Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, el inicio de sesión de la interfaz de usuario verán users& #39; Direcciones IP e información de referencia.)</li><li>Extensiones de mensajería, por otro lado, consulte users& #39; Direcciones IP e información de referencia.</li><li>En las directrices de las aplicaciones (y en nuestro proceso de revisión de AppSource) se pide discreción a la hora de publicar mensajes de chat personales para los usuarios (a través del permiso POST_MESSAGE_TEAM), siempre con unos fines válidos. En el caso de abuso, los usuarios pueden bloquear el bot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear los bots centralmente, en caso necesario.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Algunos bots solo envían mensajes (POST_MESSAGE_USER). They& #39; re llamado &quot;sólo de notificación&quot; bots, pero la doesn& términos #39; t hacer referencia a un componente de qué está permitido o no permitido hacer, significa que el doesn& bot #39; t desea exponer una experiencia familiar. Los equipos utiliza este campo para deshabilitar la funcionalidad de la interfaz de usuario que normalmente se habilitados; el isn& de bot #39; t restringidos en qué it& #39; s pueda hacer en comparación con bots que exponen una experiencia familiar.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">En este momento en Developer Preview.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Regirá la <code>supportsFiles</code> propiedad booleana en el objeto de componente en el archivo manifest.json para la aplicación.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un componente tiene su propio inicio de sesión, hay un segundo — diferentes: consentimiento experiencia la primera vez que el usuario inicia sesión.</li><li>Actualmente, los permisos de Azure AD asociados con cualquiera de las funciones dentro de una aplicación de los equipos (bot, ficha, conector o extensión de mensajería) son completamente independientes de los permisos de los equipos que se muestran aquí.</li></ul>


## <a name="tabs"></a>Pestañas

Una pestaña es un sitio Web que se ejecuta dentro de los equipos.

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Ninguno (actualmente).</td>
    <td valign="top"><ul><li>El perfil de riesgo de una ficha es casi idéntico al mismo sitio Web que se ejecuta en una ficha de explorador. </li><li>Una ficha también obtiene el contexto de en qué it& #39; s que se ejecuta, incluidos el nombre de inicio de sesión y el UPN del usuario actual, el objeto de AD de Azure ID para el usuario actual, el identificador de la de Office 365 grupo en el que reside (si se trata de un equipo) , el identificador de inquilino y la configuración regional actual del usuario. Sin embargo asignar estos identificadores a un user& #39; información s, la ficha tendría que hacer que el usuario inicie sesión en Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Conectores

Un conector de entradas de mensajes en un canal cuando se producen eventos en un sistema externo.

  <table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Ciertos conectores admiten <em>los mensajes que se pueden procesar</em>, que permiten a los usuarios registrar respuestas de destinadas en el mensaje de conector, por ejemplo agregando una respuesta a un problema de depósito o una fecha en una tarjeta de Trello.</td>
    <td valign="top"><ul><li>El sistema que entradas de conector mensajes doesn& #39; t saber con quién it& #39; s exponer un elemento en o que recibe los mensajes: no hay información acerca del destinatario se revela. (Microsoft es el destinatario real, no el inquilino; Microsoft lo hace la entrada real en el canal.)</li><li>No hay datos salen de la red corporativa cuando se registran los mensajes de conector en un canal.</li><li>Los conectores que admiten los mensajes que se pueden procesar (permiso REPLYTO_CONNECTOR_MESSAGE) también don& #39; t vea IP dirección y extraerá la información; Esta información se envía a Microsoft y, a continuación, se enruta a los extremos HTTP que se registraron anteriormente con Microsoft en el portal de conectores.</li><li>Cada vez que un conector está configurado para un canal, se crea una dirección URL única para esa instancia del conector. Si esa instancia del conector se elimina, ya no se puede usar la dirección URL.</li><li>Conector mensajes can& #39; t contienen datos adjuntos del archivo.</li><li>La instancia del conector dirección URL debe tratarse como secreto/confidencial: cualquier persona que tiene que puede registrar la dirección URL a él, como una dirección de correo electrónico. Por lo tanto, there& #39; s algunos riesgos de correo no deseado o vínculos a sitios de suplantación de identidad o malware. Si estaban a que se produzca, los propietarios de equipo pueden eliminar la instancia del conector.</li><li>Si el servicio que envía los mensajes de conector fueron a convertirse en riesgo y empezar a enviar vínculos de correo electrónico no deseado y suplantación de identidad y malware, un administrador de inquilinos puede impedir nuevas instancias de conector que se está creando y puede bloquear Microsoft centralmente.</li></ul></td>
  </tr>
</table>

> [!Note]
> No es actualmente posible saber qué conectores admiten los mensajes que se pueden procesar (permiso REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks saliente

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
    <td valign="top"><ul><li>Webhooks salientes son similares a bots pero tiene menos privilegios. Debe ser explícitamente se ha mencionado, al igual que de bots.</li><li>Cuando se registra un webhook saliente, se genera un <em>secreto</em> , lo que permite el webhook saliente comprobar que el remitente es Microsoft Teams en contraposición a un atacante malintencionado. Este secreto debe permanecer un secreto; Microsoft Teams puede suplantar a cualquier persona que tiene acceso a ella. Si el secreto se ve comprometido, puede eliminarse y vuelve a crear la webhook saliente, y se generará un nuevo secreto.</li><li>Aunque it& #39; s posibles crear una webhook saliente que doesn& #39; t validar el secreto, no se recomienda.</li><li>Distinto de recibir y responder a mensajes, outgoing webhooks can& #39; t hacer mucho: se can& #39; t enviar mensajes, de forma proactiva can& #39; t enviar o recibir archivos, can& #39; t hacer nada más que puede hacer es bots recepción y responder a mensajes.</li></ul></td>
  </tr>
</table>
