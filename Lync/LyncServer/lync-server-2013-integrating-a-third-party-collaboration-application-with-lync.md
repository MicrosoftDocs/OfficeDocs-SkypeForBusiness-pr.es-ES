---
title: Integrar una aplicación de colaboración de terceros con Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integrar una aplicación de colaboración de terceros con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Puede integrar Lync 2013 con cualquier aplicación de colaboración en línea de terceros agregando información sobre la aplicación al registro. Puede usar Lync 2013 para iniciar sesiones de conferencia de datos hospedadas en un servidor interno, en un servicio basado en Internet o en ambos. La sesión de colaboración o conferencia de datos se puede iniciar desde la lista de contactos o desde una sesión de mensajería instantánea, voz o vídeo existente. Lync 2013 solo actúa como vehículo para iniciar la aplicación. Las conversaciones existentes de Lync 2013 permanecen activas después de que la sesión de colaboración en línea haya comenzado.

En las siguientes secciones se describe cómo integrar Lync 2013 con aplicaciones de colaboración basadas en Internet y en servidor.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integrar una aplicación de colaboración basada en Internet con Lync 2013

Por lo general, los pasos necesarios para integrar una aplicación de colaboración de terceros son los siguientes:

1.  La información sobre la aplicación se agrega al registro.

2.  El organizador inicia sesión en Lync 2013 y selecciona contactos para compartir datos y colaborar. O bien, es posible que el organizador ya esté en una conversación y decida agregar conferencias de datos.

3.  Lync 2013 lee el registro, inicia la aplicación de colaboración y, a continuación, envía un mensaje SIP personalizado (un appINVITE) a los participantes seleccionados.

4.  Los participantes aceptan la invitación y la aplicación de colaboración se inicia en el equipo de cada usuario. Lync 2013 usa el registro para determinar qué aplicación de colaboración se debe usar y, a continuación, inicia esa aplicación con los parámetros incluidos en el mensaje appINVITE.

En la siguiente tabla se describen las entradas del registro necesarias para integrar una aplicación de colaboración basada en Internet con Lync 2013. Estas entradas se colocan en el registro en la siguiente ubicación:

  - HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\,\\parámetros de aplicaciones

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entradas del registro para una aplicación de colaboración basada en Internet

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
<td><p>Vistas</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso a los iconos de 16 píxeles x 16 píxeles, BMP o PNG.</p></td>
</tr>
<tr class="odd">
<td><p> Ruta de acceso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de participante para iniciar la aplicación de colaboración en línea.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta del organizador para iniciar la aplicación de colaboración en línea. Esta ruta de acceso puede contener uno o varios parámetros personalizados, tal y como se define en la subclave Parameters. Por ejemplo,<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = sesión de dos partes (predeterminado). Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación del sistema al otro usuario. El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</p>
<p>2 = sesión de varias partes. Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones del sistema al resto de los usuarios, pidiéndoles que inicien la aplicación especificada en su propio equipo.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Una lista de los menús en los que aparecerá este comando, separados por punto y coma. Los valores posibles son:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Si no se define ExtensibleMenu, se usan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


En la tabla siguiente se describen las entradas del registro para parámetros. Estas entradas se colocan\_en\_el\\software\\del\\usuario\\actual\\de\\Microsoft\\Office\\15,0 Lync SessionManager de las aplicaciones.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entradas del registro para una aplicación de colaboración basada en Internet

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
<td><p>Se usa en formato con símbolo<code>%Parm1%</code>() para agregar valores específicos del usuario a la clave de registro OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Parámetro2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vea Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Vea Param1.</p></td>
</tr>
</tbody>
</table>


El siguiente ejemplo de configuración del registro integra el cliente de colaboración Adatum con Lync 2013:

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Integrar una aplicación de colaboración basada en servidor con Lync 2013

La configuración para agregar comandos para iniciar una aplicación de colaboración basada en servidor desde Lync 2013 es similar a la que se describe en la sección anterior, al integrar una aplicación de colaboración basada en Internet con Lync 2013. Sin embargo, la OriginatorPath no es obligatoria y se modifican algunos valores. Las entradas del registro se colocan en la siguiente ubicación:

  - HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\,\\parámetros de aplicaciones

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Entradas del registro para una aplicación de colaboración basada en servidor

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
<td><p>Nombre de la aplicación tal y como aparece en el menú.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>Valor = 1. Establece el tipo de aplicación en protocolo. Los otros valores posibles no se aplican en este caso. Si no está presente, ApplicationType se establece en 0 (ejecutable).</p></td>
</tr>
<tr class="odd">
<td><p> Ruta de acceso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocolo usado para iniciar la aplicación de colaboración. En Live Meeting 2007, el valor de path se establece en <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = sesión de dos partes (predeterminado). Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación del sistema al otro usuario. El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</p>
<p>2 = sesión de varias partes. Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones del sistema al resto de los usuarios, pidiéndoles que inicien la aplicación especificada en su equipo.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = el tipo de servidor.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Una lista de los menús en los que aparecerá este comando, separados por puntos y comas. Los valores posibles son:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Si no se define ExtensibleMenu, se usan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


En el siguiente ejemplo se agregan comandos para iniciar el cliente de colaboración de Adatum desde Lync 2013:

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

