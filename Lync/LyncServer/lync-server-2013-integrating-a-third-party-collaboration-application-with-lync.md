---
title: Integración de una aplicación de colaboración de terceros con Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integración de una aplicación de colaboración de terceros con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede integrar Lync 2013 con cualquier aplicación de colaboración en línea de terceros agregando información sobre la aplicación al registro. Puede usar Lync 2013 para iniciar sesiones de conferencia de datos hospedadas en un servidor interno, un servicio basado en Internet o ambos. Las sesiones de colaboración o de conferencia de datos se pueden iniciar desde la lista de contactos o desde una sesión de mensajería instantánea, voz o vídeo existente. Lync 2013 solo actúa como vehículo para iniciar la aplicación. Las conversaciones existentes de Lync 2013 permanecen activas una vez iniciada la sesión de colaboración en línea.

En las siguientes secciones se describe cómo integrar Lync 2013 con aplicaciones de colaboración basadas en Internet y en servidor.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integración de una aplicación de colaboración basada en Internet con Lync 2013

En general, los pasos necesarios para integrar una aplicación de colaboración de otro fabricante son los siguientes:

1.  La información acerca de la aplicación se agrega al Registro.

2.  El organizador inicia sesión en Lync 2013 y selecciona contactos para uso compartido y colaboración de datos. Es posible también que el organizador ya esté participando en una conversación y decida agregar la conferencia de datos.

3.  Lync 2013 lee el registro, inicia la aplicación de colaboración y, a continuación, envía un mensaje SIP personalizado (un appINVITE) a los participantes seleccionados.

4.  Los participantes aceptan la invitación y la aplicación de colaboración se inicia en el equipo de cada una de las personas. Lync 2013 usa el registro para determinar la aplicación de colaboración que se va a usar y, a continuación, inicia esa aplicación con los parámetros incluidos en el mensaje appINVITE.

En la tabla siguiente se describen las entradas del registro necesarias para integrar una aplicación de colaboración basada en Internet con Lync 2013. Estas entradas se colocan en el registro en la siguiente ubicación:

  - HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\de\\aplicaciones de Lync

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entradas del Registro para una aplicación de colaboración basada en Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Tipo</th>
<th>Datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>REG_SZ</p></td>
<td><p>El nombre de la aplicación para los menús de Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso al icono de 16 x 16 píxeles, BMP o PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso de los participantes para iniciar la aplicación de colaboración en línea.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso del organizador para iniciar la aplicación de colaboración en línea. Esta ruta puede contener uno o varios parámetros personalizados definidos en la subclave Parameters. Por ejemplo: <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = Sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = Sesión entre dos participantes (valor predeterminado). Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación del sistema al otro usuario. El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</p>
<p>2 = Sesión de varios participantes. Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones del sistema a los demás usuarios, solicitándole que inicien la aplicación especificada en su propio equipo.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lista de menús en los que aparecerá este comando, separados con caracteres de punto y coma. Los valores posibles son:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Si no se define ExtensibleMenu, se utilizan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


En la siguiente tabla se describen las entradas del Registro para los parámetros. Estas entradas se colocan\_en\_el\\software\\de\\usuario\\actual\\de\\los\\parámetros\\de las aplicaciones de Lync SessionManager de Microsoft Office 15,0 Lync.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entradas del Registro para una aplicación de colaboración basada en Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Tipo</th>
<th>Datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Parámetro1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Se usa en formato con tokens (<code>%Parm1%</code>) para agregar valores específicos del usuario a la clave del registro OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Parámetro2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Consulte Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Consulte Param1.</p></td>
</tr>
</tbody>
</table>


La siguiente configuración del registro de ejemplo integra el cliente de colaboración Adatum con Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Integración de una aplicación de colaboración basada en servidor con Lync 2013

La configuración para agregar comandos para iniciar una aplicación de colaboración basada en servidor desde dentro de Lync 2013 es similar a la descrita en la sección anterior, lo que integra una aplicación de colaboración basada en Internet con Lync 2013. No obstante, el parámetro OriginatorPath no es necesario y algunos valores varían. Las entradas del registro se colocan en la siguiente ubicación:

  - HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\de\\aplicaciones de Lync

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Entradas del Registro para una aplicación de colaboración basada en servidor

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Tipo</th>
<th>Datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nombre de la aplicación tal como aparece en el menú.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>Valor =1. Establece el tipo de aplicación en protocolo. Los otros valores posibles no se aplican en este caso. Si no está presente, ApplicationType se establece en 0 (ejecutable).</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocolo usado para iniciar la aplicación de colaboración. Para Live Meeting 2007, el valor de path se establece en <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = Sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = Sesión entre dos participantes (valor predeterminado). Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación del sistema al otro usuario. El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</p>
<p>2 = Sesión de varios participantes. Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones del sistema a los demás usuarios, solicitándole que inicien la aplicación especificada en su equipo.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATOS = El tipo de servidor.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Una lista de los menús en los que aparecerá este comando, separados por punto y coma. Los valores posibles son:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Si no se define ExtensibleMenu, se utilizan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


En el siguiente ejemplo, se agregan comandos para iniciar el cliente de colaboración Adatum desde Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

