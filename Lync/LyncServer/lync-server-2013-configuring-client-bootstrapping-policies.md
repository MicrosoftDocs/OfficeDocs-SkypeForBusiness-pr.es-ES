---
title: 'Lync Server 2013: configuración de directivas de inicio de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8258063645267fb12801548ddfdeae1b4ef7c795
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configuración de directivas de inicio de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directiva de grupo son herramientas que puede usar para administrar directivas de grupo. En la plantilla administrativa de la Directiva de grupo de Office se incluyen las plantillas administrativas de Lync 2013. ADMX (ADMX) y. ADML (ADML), que contienen la configuración de directiva basada en el registro que se configura para los objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos del idioma de los archivos ADMX. Todos los archivos ADMX y ADML contienen la configuración de directiva de una única aplicación de Office. Para obtener más información, consulte "archivos de plantilla administrativa (ADMX, ADML) de Office 2013" en la documentación <http://go.microsoft.com/fwlink/p/?linkid=267516>de Office 2013 en.

Para Lync 2013, hay varias directivas de inicio del cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente tiene que usar hasta que se complete el inicio de sesión. Puede usar esta directiva de grupo para establecer estas configuraciones en los registros de los equipos de los usuarios antes de que inicien sesión y reciban configuraciones de aprovisionamiento dentro de banda del servidor. En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo disponibles para Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Configuración de directiva de grupo para Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración de directiva de grupo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Especificar servidor<br />
(ConfigurationMode)</p></td>
<td><p>Especifica cómo Lync 2013 identifica el transporte y el servidor que se van a usar durante el inicio de sesión. En esta opción puede especificar lo siguiente:</p>
<ul>
<li><p>ServerAddressExternal: especifica el nombre del servidor o la dirección IP que utilizan los clientes y los contactos federados al conectarse desde fuera del firewall externo.</p></li>
<li><p>ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se utilizan cuando los clientes se conectan desde dentro del firewall de la organización.</p></li>
<li><p>Transporte: especifica el Protocolo de control de transmisión (TCP) o Seguridad de la capa de transporte (TLS).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versiones de servidor adicionales admitidas<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Especifica una lista de nombres de versión de servidor separados por puntos y comas donde Lync Server 2013 iniciará sesión, además de las versiones de servidor que son compatibles de forma predeterminada.</p></td>
</tr>
<tr class="odd">
<td><p>Deshabilitar la carga automática de los registros de errores de inicio de sesión (DisableAutomaticSendTracing)</p></td>
<td><p>Carga automáticamente registros de errores de inicio de sesión en Lync Server para su análisis. No se cargan automáticamente registros si el inicio de sesión es correcto. Si esta directiva no está configurada, ocurre lo siguiente:</p>
<dl>
<dt><span></span></dt>
<dd><p>Para usuarios de Lync Online: los registros de errores de inicio de sesión se cargan automáticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Para los usuarios de Lync local: se muestra un cuadro de diálogo de confirmación para el usuario antes de cargarlo.</p>
</dd>
</dl>
<p>Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el servidor de Lync para los usuarios de Lync local y Lync Online. Cuando este parámetro está habilitado, los registros de inicio de sesión nunca se cargan automáticamente.</p></td>
</tr>
<tr class="even">
<td><p>Deshabilitar la reserva HTTP para conexión SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Impide que Lync Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles. De forma predeterminada, Lync primero intenta conectarse al servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte se realiza correctamente, Lync intenta conectarse mediante HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.</p></td>
</tr>
<tr class="odd">
<td><p>Requerir credenciales de inicio de sesión<br />
(DisableNTCredentials)</p></td>
<td><p>Requiere que el usuario proporcione las credenciales de inicio de sesión de Lync en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.</p></td>
</tr>
<tr class="even">
<td><p>Deshabilitar comprobación de la versión del servidor<br />
(DisableServerCheck)</p></td>
<td><p>Si establece esta directiva en 1, evitará que Lync Compruebe el nombre del servidor y la versión antes de iniciar sesión. De forma predeterminada, Lync realiza estas comprobaciones antes de iniciar sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el uso de BITS para descargar los archivos del servicio de libreta de direcciones<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permite que Lync use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.</p></td>
</tr>
<tr class="even">
<td><p>Configurar el modo de seguridad SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permite a Lync enviar y recibir mensajes instantáneos de forma más segura. Esta directiva no afecta a los servicios de Microsoft Exchange Server ni Windows .NET.</p>
<p>Si no establece esta configuración de Directiva, Lync puede usar cualquier transporte. Pero si no usa TLS y el servidor autentica a los usuarios, Lync debe usar la autenticación NTLM o Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Descarga inicial de la libreta de direcciones global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Especifica el período de tiempo que transcurrirá antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período de tiempo aleatorio comprendido entre 0 y 60 minutos.</p></td>
</tr>
<tr class="even">
<td><p>Impedir que los usuarios ejecuten Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Impide que los usuarios ejecuten Lync. Puede establecer esta configuración de directiva en Configuración del equipo o en Configuración de usuario, pero la configuración de directiva de Configuración del equipo tiene prioridad.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir el almacenamiento de contraseñas de usuario<br />
(SavePassword)</p></td>
<td><p>Permite a Lync almacenar contraseñas.</p></td>
</tr>
<tr class="even">
<td><p>Configurar el modo de compresión SIP<br />
(SipCompression)</p></td>
<td><p>Especifica cuándo debe activarse la compresión SIP. De forma predeterminada, la compresión SIP se habilita en función de la velocidad del adaptador. Tenga en cuenta que la configuración de esta directiva puede provocar un aumento en el tiempo de inicio de sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Lista de dominios de confianza<br />
TrustModelData</p></td>
<td><p>Muestra los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.</p></td>
</tr>
</tbody>
</table>


Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.

### <a name="group-policy-precedence"></a>Prioridad de las directivas de grupo

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prioridad</th>
<th>Ubicación o método de configuración</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Aprovisionamiento en banda de Lync Server 2013</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>El cuadro de diálogo Lync-opciones en Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Para definir la configuración de directiva de grupo mediante los archivos de plantilla administrativa de Lync 2013

1.  Cree una carpeta de nivel de raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree la carpeta raíz del almacén central en el controlador del dominio en esta ubicación:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Este procedimiento presupone que desea administrar varios equipos en su dominio. En este caso, almacena las plantillas de un almacén central en la carpeta Sysvol del controlador del dominio principal. Así obtendrá una ubicación de almacenamiento central replicada para las plantillas administrativas del dominio.

    
    </div>

2.  Cree una subcarpeta para cada idioma que vaya a utilizar. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

