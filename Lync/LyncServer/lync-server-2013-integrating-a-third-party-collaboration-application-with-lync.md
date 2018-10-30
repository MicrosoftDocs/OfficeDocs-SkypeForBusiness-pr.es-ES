---
title: Integración de una aplicación de colaboración externa con Lync
TOCTitle: Integración de una aplicación de colaboración externa con Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398068(v=OCS.15)
ms:contentKeyID: 52061581
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Integración de una aplicación de colaboración externa con Lync

 

_**Última modificación del tema:** 2015-03-09_

Puede integrar Lync 2013 con cualquier aplicación de colaboración en línea de terceros si agrega información sobre la aplicación en el Registro. Puede usar Lync 2013 para iniciar sesiones de conferencia de datos hospedadas en un servidor interno, en un servidor en Internet o en ambos servidores. Las sesiones de colaboración o de conferencia de datos se pueden iniciar desde la lista de contactos o desde una sesión de mensajería instantánea, voz o vídeo existente. Lync 2013 actúa únicamente como vehículo para iniciar la aplicación. Todas las conversaciones de Lync 2013 existentes siguen activas una vez iniciada la sesión de colaboración en línea.

En las secciones siguientes se describe el modo en que Lync 2013 se integra con aplicaciones de colaboración basadas en Internet y en el servidor.

## Integración de una aplicación de colaboración basada en Internet con Lync 2013

En general, los pasos necesarios para integrar una aplicación de colaboración de otro fabricante son los siguientes:

1.  La información acerca de la aplicación se agrega al Registro.

2.  El organizador inicia sesión en Lync 2013 y selecciona los contactos para el uso compartido de datos y la colaboración. También es posible que el organizador ya esté participando en una conversación y decida agregar la conferencia de datos.

3.  Lync 2013 lee el Registro, inicia la aplicación de colaboración y envía un mensaje SIP personalizado (un mensaje appINVITE) a los participantes seleccionados.

4.  Los participantes aceptan la invitación y la aplicación de colaboración se inicia en el equipo de cada una de las personas. Lync 2013 usa el Registro para determinar qué aplicación de colaboración usar e inicia dicha aplicación usando los parámetros que se incluyen en el mensaje appINVITE.

En la tabla siguiente se describen las entradas del Registro necesarias para integrar una aplicación de colaboración basada en Internet con Lync 2013. Estas entradas se encuentran en la siguiente ubicación del Registro:

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Entradas del Registro para una aplicación de colaboración basada en Internet

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
<td><p>Ruta</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso de los participantes para iniciar la aplicación de colaboración en línea.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso del organizador para iniciar la aplicación de colaboración en línea. Esta ruta puede contener uno o varios parámetros personalizados definidos en la subclave Parameters. Por ejemplo, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = Sesión entre dos participantes (valor predeterminado). Lync 2013 inicia la aplicación localmente y envía una notificación de sistema al otro usuario. El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</p>
<p>2 = Sesión con varios participantes. Lync 2013 inicia la aplicación localmente y envía notificaciones de sistema a los demás usuarios en las que se les pide que inicien la aplicación especificada en sus propios equipos.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
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


En la siguiente tabla se describen las entradas del Registro para los parámetros. Estas entradas se encuentran en HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.

### Entradas del Registro para una aplicación de colaboración basada en Internet

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
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Se usa en un formato acortado (<code>%Parm1%</code>) para agregar valores específicos de usuario a la clave del Registro OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
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


Los siguientes valores del Registro de ejemplo integran el cliente de colaboración ADatum con Lync 2013:

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

## Integración de una aplicación de colaboración basada en el servidor con Lync 2013

La configuración para agregar comandos que inicien una aplicación de colaboración basada en el servidor en Lync 2013 es similar a la que se ha descrito en la sección anterior (Integración de una aplicación de colaboración basada en Internet con Lync 2013). No obstante, el parámetro OriginatorPath no es necesario y algunos valores varían. Las entradas del Registro se encuentran en la siguiente ubicación:

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Entradas del Registro para una aplicación de colaboración basada en servidor

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
<td><p>DWORD</p></td>
<td><p>Valor =1. Establece el tipo de aplicación en protocolo. Los otros valores posibles no se aplican en este caso. Si no se especifica, ApplicationType se establece en 0 (ejecutable).</p></td>
</tr>
<tr class="odd">
<td><p>Ruta</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocolo usado para iniciar la aplicación de colaboración. Para Live Meeting 2007, el valor de Path se establece en <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = Sesión entre dos participantes (valor predeterminado). Lync 2013 inicia la aplicación localmente y envía una notificación de sistema al otro usuario. El otro usuario hace clic en la notificación e inicia la aplicación especificada en su equipo.</p>
<p>2 = Sesión de varios participantes. Lync 2013 inicia la aplicación localmente y envía notificaciones de sistema a los demás usuarios en las que se les pide que inicien la aplicación especificada en sus propios equipos.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATOS = El tipo de servidor.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lista de menús en los que aparecerá este comando, separados por punto y coma. Los valores posibles son los siguientes:</p>
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


En el siguiente ejemplo se agregan comandos para iniciar el cliente de colaboración ADatum desde Lync 2013:

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

