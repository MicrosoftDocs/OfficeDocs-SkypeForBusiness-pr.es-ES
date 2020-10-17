---
title: 'Lync Server 2013: configuración de directivas de arranque de cliente'
description: 'Lync Server 2013: configuración de directivas de arranque de cliente.'
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
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545636"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configuración de directivas de arranque de cliente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La consola de administración de directivas de grupo (GPMC) y el editor de objetos de directiva de grupo son herramientas que se usan para administrar la Directiva de grupo. En la plantilla administrativa de la Directiva de grupo de Office se incluyen plantillas administrativas de Lync 2013. ADMX (ADMX) y. ADML (ADML), que contienen las opciones de directiva basadas en el registro que se configuran para los objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos de idioma para archivos ADMX. Cada archivo ADMX y ADML contiene la configuración de directiva para una sola aplicación de Office. Para obtener más información, consulte "Office 2013 Administrative template files (ADMX, ADML)" en la documentación de Office 2013 en <https://go.microsoft.com/fwlink/p/?linkid=267516> .

Para Lync 2013, hay varias directivas de arranque de cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente debe usar hasta que se complete el inicio de sesión. Puede usar la Directiva de grupo para establecer estas opciones en los registros del equipo de los usuarios antes de iniciar sesión y comenzar a recibir la configuración de aprovisionamiento en banda del servidor. En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo que están disponibles para Lync 2013.

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
ConfigurationMode</p></td>
<td><p>Especifica cómo Lync 2013 identifica el transporte y el servidor que se deben usar durante el inicio de sesión. En esta configuración, debe especificar lo siguiente:</p>
<ul>
<li><p>ServerAddressExternal: especifica el nombre del servidor o la dirección IP que usan los clientes y los contactos federados cuando se conectan desde fuera del firewall externo.</p></li>
<li><p>ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se usa cuando los clientes se conectan desde dentro del firewall de la organización.</p></li>
<li><p>Transport: especifica el protocolo de control de transmisión (TCP) o la seguridad de la capa de transporte (TLS).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versiones de servidor adicionales admitidas<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Especifica una lista de nombres de versiones de servidor separados por punto y coma en los que Lync Server 2013 iniciará sesión, además de las versiones de servidor admitidas de forma predeterminada.</p></td>
</tr>
<tr class="odd">
<td><p>Deshabilitar la carga automática de registros de error de inicio de sesión (DisableAutomaticSendTracing)</p></td>
<td><p>Carga automáticamente los registros de error de inicio de sesión en Lync Server para su análisis. Si el inicio de sesión se realiza correctamente, no se cargará automáticamente ningún registro. Si esta Directiva no está configurada, ocurrirá lo siguiente:</p>
<dl>
<dt><span></span></dt>
<dd><p>Para los usuarios de Lync Online: los registros de error de inicio de sesión se cargan automáticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Para los usuarios de Lync local: se muestra un cuadro de diálogo de confirmación al usuario antes de cargarlo.</p>
</dd>
</dl>
<p>Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el servidor Lync para los usuarios de Lync local y Lync Online. Cuando esta configuración está habilitada, los registros de inicio de sesión nunca se cargan automáticamente.</p></td>
</tr>
<tr class="even">
<td><p>Deshabilitar la reserva HTTP para la conexión SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Impide que Lync Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles. De forma predeterminada, Lync intenta primero conectar con el servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte funciona correctamente, Lync intenta conectarse mediante HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.</p></td>
</tr>
<tr class="odd">
<td><p>Requerir credenciales de inicio de sesión<br />
DisableNTCredentials</p></td>
<td><p>Requiere que el usuario proporcione credenciales de inicio de sesión para Lync en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.</p></td>
</tr>
<tr class="even">
<td><p>Deshabilitar la comprobación de la versión del servidor<br />
(DisableServerCheck)</p></td>
<td><p>Si establece esta directiva en 1, impide que Lync Compruebe el nombre del servidor y la versión antes de iniciar sesión. De forma predeterminada, Lync realiza estas comprobaciones antes de iniciar sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el uso de BITS para descargar archivos del servicio de libreta de direcciones<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permite que Lync use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.</p></td>
</tr>
<tr class="even">
<td><p>Configurar el modo de seguridad SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permite a Lync enviar y recibir mensajes instantáneos de forma más segura. Esta directiva no se aplica a los servicios de Windows .NET o Microsoft Exchange Server.</p>
<p>Si no establece esta configuración de Directiva, Lync puede usar cualquier transporte. Pero si no usa TLS y el servidor autentica a los usuarios, Lync debe usar la autenticación NTLM o Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Retraso inicial de descarga de libreta de direcciones global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Especifica el período de tiempo que debe transcurrir antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es de 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período aleatorio comprendido entre 0 y 60 minutos.</p></td>
</tr>
<tr class="even">
<td><p>Impedir que los usuarios ejecuten Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Impide que los usuarios ejecuten Lync. Puede configurar esta opción de directiva en Configuración del equipo y Configuración de usuario, si bien la configuración de directiva establecida en Configuración del equipo tiene prioridad.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir el almacenamiento de contraseñas de usuario<br />
SavePassword</p></td>
<td><p>Permite que Lync almacene contraseñas.</p></td>
</tr>
<tr class="even">
<td><p>Configurar el modo de compresión SIP<br />
(SipCompression)</p></td>
<td><p>Especifica cuándo se debe activar la compresión SIP. De forma predeterminada, la compresión SIP está habilitada en función de la velocidad del adaptador. Tenga en cuenta que al configurar esta directiva podría aumentar el tiempo de inicio de sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Lista de dominios de confianza<br />
TrustModelData</p></td>
<td><p>Enumera los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.</p></td>
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
<th>Precedence</th>
<th>Ubicación o método de configuración</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Aprovisionamiento en banda de Lync Server 2013</p></td>
</tr>
<tr class="even">
<td><p>segundo</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>El cuadro de diálogo Lync-opciones en Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Para definir la configuración de la Directiva de grupo con los archivos de plantilla administrativa de Lync 2013

1.  Cree una carpeta de nivel raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree una carpeta de nivel raíz del almacén central en su controlador de dominio en esta ubicación:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > En este procedimiento se presupone que desea administrar varios equipos en su dominio. En este caso, se almacenan las plantillas en un almacén central en la carpeta Sysvol del controlador de dominio principal. Esto proporciona una ubicación del almacén central replicada para las plantillas administrativas del dominio.

    
    </div>

2.  Cree una subcarpeta para cada idioma que vaya a usar. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para Inglés de Estados Unidos (EN-US) en esta ubicación:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

