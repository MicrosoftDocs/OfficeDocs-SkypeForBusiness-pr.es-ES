---
title: Configuración de las directivas de arranque del cliente en Lync Server 2013
TOCTitle: Configuración de las directivas de arranque del cliente en Lync Server 2013
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48275088
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de las directivas de arranque del cliente en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directivas de grupo son herramientas que puede utilizar para administrar directivas de grupo. En la Plantilla administrativa de directivas de grupo de Office se incluyen las plantillas administrativas Lync 2013.admx (ADMX) y .adml (ADML), que contienen la configuración de directiva basada en registro con la que puede configurar objetos de directivas de grupo en el dominio. Los archivos ADML son complementos específicos del idioma de los archivos ADMX. Todos los archivos ADMX y ADML contienen la configuración de directiva de una única aplicación de Office.

En Lync 2013, existen varias directivas de arranque de clientes que deberán configurarse antes de que los usuarios inicien sesión por primera vez en el servidor. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente debe utilizar hasta que se haya completado el inicio de sesión. Puede utilizar esta directiva de grupo para establecer estas configuraciones en los registros de los equipos de los usuarios antes de que inicien sesión y reciban configuraciones de aprovisionamiento en banda del servidor. En la siguiente tabla se enumeran las configuraciones de directivas de grupo que están disponibles para Lync 2013.

### Configuración de directiva de grupo para Lync 2013

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
<td><p>Especifica cómo Lync 2013 identifica el transporte y el servidor que se utilizarán durante el inicio de sesión. En esta opción puede especificar lo siguiente:</p>
<ul>
<li><p>ServerAddressExternal: especifica el nombre del servidor o la dirección IP que utilizan los clientes y los contactos federados al conectarse desde fuera del firewall externo.</p></li>
<li><p>ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se utilizan cuando los clientes se conectan desde dentro del firewall de la organización.</p></li>
<li><p>Transporte: especifica el Protocolo de control de transmisión (TCP) o Seguridad de la capa de transporte (TLS).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Otras versiones del servidor compatibles<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Especifica una lista de nombres de versiones del servidor separados por punto y coma en los que Lync Server 2013 iniciará sesión, además de las versiones del servidor compatibles de forma predeterminada.</p></td>
</tr>
<tr class="odd">
<td><p>Deshabilitar la carga automática de los registros de errores de inicio de sesión (DisableAutomaticSendTracing)</p></td>
<td><p>Carga automáticamente los registros de errores de inicio de sesión en Lync Server para su análisis. No se cargan automáticamente registros si el inicio de sesión es correcto. Si esta directiva no está configurada, ocurre lo siguiente:</p>
<dl>
<dt><span></span></dt>
<dd><p>Para usuarios de Lync Online: los registros de errores de inicio de sesión se cargan automáticamente.</p>
</dd>
<dt><span></span></dt>
<dd><p>Para usuarios de Lync locales: se muestra un cuadro de diálogo de confirmación al usuario antes de cargar.</p>
</dd>
</dl>
<p>Cuando esta opción está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el Lync Server para los usuarios de Lync locales y los usuarios de Lync Online. Cuando este parámetro está habilitado, los registros de inicio de sesión nunca se cargan automáticamente.</p></td>
</tr>
<tr class="even">
<td><p>Deshabilitar reserva HTTP para la conexión SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Evita que Lync Server intente conectarse al servidor utilizando HTTP, si TLS o TCP no están disponibles. De forma predeterminada, Lync intenta en primer lugar conectarse al servidor utilizando TLS o TCP y, si ninguno de estos métodos de transporte está disponible, Lync intenta conectarse utilizando HTTP. Utilice esta directiva para deshabilitar el intento de conexión HTTP de reserva.</p></td>
</tr>
<tr class="odd">
<td><p>Requerir credenciales de inicio de sesión<br />
(DisableNTCredentials)</p></td>
<td><p>Requiere que el usuario proporcione las credenciales de inicio de sesión para Lync en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.</p></td>
</tr>
<tr class="even">
<td><p>Deshabilitar comprobación de versión del servidor<br />
(DisableServerCheck)</p></td>
<td><p>Si establece esta directiva en 1, evita que Lync compruebe el nombre del servidor y la versión antes de iniciar sesión. De forma predeterminada, Lync realiza estas comprobaciones antes de iniciar sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir el uso de BITS para descargar archivos del Servicio de libreta de direcciones<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permite que Lync utilice el Servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos del Servicio de libreta de direcciones.</p></td>
</tr>
<tr class="even">
<td><p>Configurar modo de seguridad SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permite que Lync envíe y reciba mensajes instantáneos de una forma más segura. Esta directiva no afecta a los servicios de Microsoft Exchange Server ni Windows .NET.</p>
<p>Si no configura esta configuración de directiva, Lync puede utilizar cualquier transporte. Sin embargo, si no utiliza TLS y si el servidor autentica a los usuarios, Lync debe usar la autenticación NTLM o Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Retraso inicial de descarga de la libreta de direcciones global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Especifica el período de tiempo que transcurrirá antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período de tiempo aleatorio comprendido entre 0 y 60 minutos.</p></td>
</tr>
<tr class="even">
<td><p>Evitar que los usuarios ejecuten Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Evita que los usuarios ejecuten Lync. Puede configurar esta configuración de directiva tanto en Configuración del equipo como en Configuración de usuario, pero la configuración de directiva de Configuración del equipo tiene prioridad.</p></td>
</tr>
<tr class="odd">
<td><p>Permitir el almacenamiento de las contraseñas de los usuarios<br />
(SavePassword)</p></td>
<td><p>Permite a Lync guardar las contraseñas.</p></td>
</tr>
<tr class="even">
<td><p>Configurar modo de compresión SIP<br />
(SipCompression)</p></td>
<td><p>Especifica cuándo debe activarse la compresión SIP. De forma predeterminada, la compresión SIP se habilita en función de la velocidad del adaptador. Tenga en cuenta que la configuración de esta directiva puede provocar un aumento en el tiempo de inicio de sesión.</p></td>
</tr>
<tr class="odd">
<td><p>Lista de dominios de confianza<br />
(TrustModelData)</p></td>
<td><p>Muestra los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.</p></td>
</tr>
</tbody>
</table>


Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.

### Prioridad de las directivas de grupo

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
<td><p>Aprovisionamiento dentro de banda de Lync Server 2013</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>El cuadro de diálogo Lync: opciones de Lync 2013</p></td>
</tr>
</tbody>
</table>


## Para definir la configuración de directivas de grupo mediante el archivo de plantilla administrativa de Lync 2013

1.  Cree una carpeta de nivel de raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree la carpeta raíz del almacén central en el controlador del dominio en esta ubicación:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    

    > [!NOTE]
    > Este procedimiento presupone que desea administrar varios equipos en su dominio. En este caso, almacena las plantillas de un almacén central en la carpeta Sysvol del controlador del dominio principal. Así obtendrá una ubicación de almacenamiento central replicada para las plantillas administrativas del dominio.



2.  Cree una subcarpeta para cada idioma que vaya a utilizar. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

Para más información sobre los archivos ADMX, vea la Guía paso por paso para administrar archivos ADMX de directiva de grupo en [http://go.microsoft.com/fwlink/?linkid=75124\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=75124%26clcid=0xc0a).

