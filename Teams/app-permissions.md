---
title: Consideraciones y los permisos de aplicaciones de Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Obtenga información sobre lo que están solicitando datos y permisos de aplicaciones de la organización.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.openlocfilehash: 789e1a52b9a195cc353e120a769fa98c26343e88
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251597"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Consideraciones y los permisos de aplicaciones de Microsoft Teams

Aplicaciones de Microsoft Teams son una forma de agregar una o más funciones en un _paquete de la aplicación_ que se pueden instalar, actualizar y desinstalar. Las capacidades incluyen:

-   Bots
-   Extensiones de mensajería
-   Fichas
-   Conectores

Aplicaciones son aceptadas por los usuarios y administradas por TI desde una perspectiva de la directiva. Sin embargo, la mayor parte, permisos y el perfil de riesgo de una aplicación se definen por los permisos y los perfiles de riesgo de las capacidades que lo contiene. Por lo tanto, en este artículo se centra en los permisos y consideraciones en el nivel de capacidad.

Los permisos enumerados a continuación en las letras en mayúscula, por ejemplo, RECEIVE_MESSAGE y REPLYTO_MESSAGE, no aparecen en cualquier lugar en la [documentación para desarrolladores de equipos de Microsoft](https://aka.ms/teamsdevdocs) o los [permisos de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Son simplemente una forma abreviada descriptiva a efectos de este artículo.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Puntos de decisión|<ul><li>Use las tablas siguientes como guía para comprender los permisos que se solicitan las aplicaciones que va a investigar.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Siguiente paso|<ul><li>La aplicación de la investigación o propio para decidir si desea permitir el acceso a ella dentro de la organización de servicio. Por ejemplo, bots enviar y recibir mensajes de usuarios, y, excepto bots de línea de negocio de empresa: se encuentran fuera del límite de cumplimiento. Por lo tanto, cualquier aplicación que incluya un bot requiere los permisos de dichos y tiene ese perfil de riesgo, como mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Consideraciones y permisos de aplicación global

<table>
  <tr>
    <th width="25%">Permisos necesarios</th>
    <th width="25%">Permisos opcionales</th>
    <th width="50%">Consideraciones</th>
  </tr>
  <tr>
    <td valign="top">Ninguna</td>
    <td valign="top">Ninguna</td>
    <td valign="top">Una aplicación debe revelar qué datos que utiliza y qué los datos se usan para en sus términos de vínculos de directiva de uso y privacidad.</td>
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
    <td valign="top"><ul><li>IDENTIDAD. Cuando se usa en un canal, bots de la aplicación puede tener acceso a información básica de identidad de los miembros del equipo (nombre, apellidos, nombre principal de usuario [UPN], dirección de correo electrónico); Cuando se usa en un chat personal o de grupo, el robot puede tener acceso a la misma información para esos usuarios.</li><li> POST_MESSAGE_TEAM. Permite bots de una aplicación enviar mensajes de (proactivos) directos a cualquier miembro del equipo en cualquier momento, incluso si el usuario nunca ha tratado el robot antes.</li><li>El siguiente no es permisos explícitos, pero está implícitas por RECEIVE_MESSAGE y REPLYTO_MESSAGE y los ámbitos en el que se pueden usar los bots, declarado en el manifiesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. Si un componente puede enviar y recibir archivos en conversaciones personales (aún no se admite para conversaciones en grupo o canales) en los controles <sup>3</sup> .</li></ul></td>
    <td valign="top"><ul><li>Bots sólo tienen acceso a los equipos a que ha agregado o a los usuarios que tengan instalado en ellos.</li><li>Bots sólo reciben mensajes en el que está menciona explícitamente por los usuarios. Estos datos dejan la red corporativa.</li><li>    Bots sólo puede responder a las conversaciones en el que está mencionados.</li><li>Después de que un usuario ha conversed con un robot, si el robot almacena ese identificador de usuario, pueden enviar a ese usuario dirigir los mensajes en cualquier momento. </li><li>Es posible en teoría bot mensajes contienen vínculos a sitios de suplantación de identidad o malware, pero se pueden bloquear bots por el usuario, la administración de inquilinos, o de forma global por Microsoft. </li><li>Un robot puede recuperar (y es posible que almacenar) información de identidad muy básica para la aplicación se ha agregado a los miembros del equipo, o para usuarios individuales en chats personales o de grupo. Para obtener más información acerca de estos usuarios, el robot debe requerir que inicien sesión Azure Active Directory (AD Azure). </li><li>Bots puede recuperar (y es posible que almacenar) en la lista de canales en un equipo; estos datos dejan la red corporativa. </li><li>Cuando se envía un archivo a un robot, el archivo sale de la red corporativa. Enviar y recibir archivos requieren la aprobación del usuario para cada archivo. </li><li>De forma predeterminada, bots no tienen la capacidad de actuar en nombre del usuario, pero bots puede pedir a los usuarios para iniciar sesión; tan pronto como el usuario inicia sesión, el robot tendrá un token de acceso con la que pueden realizar acciones adicionales. ¿Cuáles son los aspectos adicionales depende el robot y donde el usuario inicia sesión: un bot es una aplicación de Azure AD registrada en <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> y puede tener su propio conjunto de permisos.</li><li>Bots son informados cada vez que se agregan o se elimina de un equipo de los usuarios.</li><li>Bots no ve las direcciones IP de los usuarios u otra información de referencia. Toda la información proviene de Microsoft. (Hay una excepción: si un bot implementa su propia experiencia de inicio de sesión, el inicio de sesión de la interfaz de usuario verán las direcciones IP de los usuarios y la información de referencia.)</li><li>Extensiones de mensajería, por otro lado, vea las direcciones IP de los usuarios y la información de referencia.</li><li>Instrucciones de la aplicación (y nuestro proceso de revisión AppSource) requieren discreción en mensajes de chat personal de contabilización a los usuarios (mediante el permiso POST_MESSAGE_TEAM) para fines válidos. En caso de infracción, los usuarios pueden bloquear el robot, los administradores de inquilinos pueden bloquear la aplicación y Microsoft puede bloquear bots centralmente si es necesario.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Algunos bots sólo envían mensajes (POST_MESSAGE_USER). Se llaman bots "sólo de notificación", pero el término no hace referencia a un componente de qué está permitido o no permitido hacer, significa que no desea que el robot exponer una experiencia familiar. Los equipos utiliza este campo para deshabilitar la funcionalidad de la interfaz de usuario que normalmente se habilitados; el robot no está restringido en lo que se permite para hacer en comparación con bots que exponen una experiencia familiar.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Actualmente en vista previa para desarrolladores.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Actualmente en vista previa para desarrolladores. Regirá la <code>supportsFiles</code> propiedad booleana en el objeto de componente en el archivo manifest.json para la aplicación.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un componente tiene su propio inicio de sesión, hay un segundo — diferentes: consentimiento experiencia la primera vez que el usuario inicia sesión.</li><li>Actualmente, los permisos de Azure AD asociados con cualquiera de las funciones dentro de una aplicación de los equipos (bot, ficha, conector o extensión de mensajería) son completamente independientes de los permisos de los equipos que se muestran aquí.</li></ul>


## <a name="tabs"></a>Fichas

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
    <td valign="top"><ul><li>El perfil de riesgo de una ficha es casi idéntico al mismo sitio Web que se ejecuta en una ficha de explorador. </li><li>Una ficha también obtiene el contexto en el que se está ejecutando, incluido el nombre de inicio de sesión y UPN del usuario actual, el objeto de AD de Azure el identificador para el usuario actual, el identificador de la de Office 365 grupo (equipo) en el que reside, el identificador de inquilino y la configuración regional actual del usuario. Sin embargo, para asignar estos identificadores a la información de un usuario, puede que la ficha tendría que hacer que el usuario inicie sesión en Azure AD.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Ciertos conectores admiten _los mensajes que se pueden procesar_, que permiten a los usuarios registrar respuestas de destinadas en el mensaje de conector, por ejemplo agregando una respuesta a un problema de depósito o una fecha en una tarjeta de Trello.</td>
    <td valign="top"><ul><li>El sistema que registra los mensajes de conector no sabe quién es registro a o quién recibe los mensajes: no hay información acerca del destinatario se revela. (Microsoft es el destinatario real, no el inquilino; Microsoft lo hace la entrada real en el canal.)</li><li>No hay datos salen de la red corporativa cuando se registran los mensajes de conector en un canal.</li><li>Los conectores que admiten los mensajes que se pueden procesar (permiso REPLYTO_CONNECTOR_MESSAGE) no ven también información de dirección y extraerá IP; Esta información se envía a Microsoft y, a continuación, se enruta a los extremos HTTP que se registraron anteriormente con Microsoft en el portal de conectores.</li><li>Cada vez que un conector está configurado para un canal, se crea una dirección URL única para esa instancia del conector. Si esa instancia del conector se elimina, ya no se puede usar la dirección URL.</li><li>Conector los mensajes no pueden contener datos adjuntos de archivo.</li><li>La instancia del conector dirección URL debe tratarse como secreto/confidencial: cualquier persona que tiene que puede registrar la dirección URL a él, como una dirección de correo electrónico. Por lo tanto, hay algunos riesgos de correo no deseado o vínculos a sitios de suplantación de identidad o malware. Si estaban a que se produzca, los propietarios de equipo pueden eliminar la instancia del conector.</li><li>Si el servicio que envía los mensajes de conector fueron a convertirse en riesgo y empezar a enviar vínculos de correo electrónico no deseado y suplantación de identidad y malware, un administrador de inquilinos puede impedir nuevas instancias de conector que se está creando y puede bloquear Microsoft centralmente.</li></ul></td>
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
    <td valign="top">Ninguna</td>
    <td valign="top"><ul><li>Webhooks salientes son similares a bots pero tiene menos privilegios. Debe ser explícitamente se ha mencionado, al igual que de bots.</li><li>Cuando se registra un webhook saliente, se genera un _secreto_ , lo que permite el webhook saliente comprobar que el remitente es Microsoft Teams en contraposición a un atacante malintencionado. Este secreto debe permanecer un secreto; Microsoft Teams puede suplantar a cualquier persona que tiene acceso a ella. Si el secreto se ve comprometido, puede eliminarse y vuelve a crear la webhook saliente, y se generará un nuevo secreto.</li><li>Aunque es posible crear una webhook saliente que no valida el secreto, se recomienda en él.</li><li>Distinto de recibir y responder a mensajes, outgoing webhooks no puede hacer mucho: no pueden enviar mensajes de forma proactiva, no se pueden enviar o recibir archivos, no pueden hacer nada más que puede hacer es bots recepción y responder a los mensajes.</li></ul></td>
  </tr>
</table>