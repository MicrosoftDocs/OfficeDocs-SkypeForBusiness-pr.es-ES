---
title: "Lync Server 2013: Requisitos IIS para servidores front-end y servs. Standard Edition"
TOCTitle: Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48277035
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para servidores Standard Edition, servidores front-end y directores, el instalador de Lync Server 2013 crea directorios virtuales en Servicios de Internet Information Server (IIS) para:

  - Habilitar a los usuarios para descargar archivos desde el Servicio de libreta de direcciones

  - Habilitar a los clientes para obtener actualizaciones

  - Habilitar las conferencias

  - Permitir que los usuarios descarguen el contenido de las reuniones

  - Habilitar a los usuarios para expandir grupos de distribución

  - Habilitar las conferencias telefónicas

  - Habilitar las características de grupo de respuesta

Además, el instalador de la actualización acumulada de Lync Server 2010: noviembre de 2011 crea directorios virtuales en IIS con los siguientes fines:

  - En Servidores front-end o servidores Standard Edition para admitir la funcionalidad de movilidad, como la mensajería instantánea (MI) y la presencia, en dispositivos móviles

  - En Servidores front-end o servidores Standard Edition y en directores para habilitar dispositivos móviles para detectar automáticamente recursos de movilidad


> [!NOTE]
> Si va a implementar la movilidad, se recomienda usar IIS 7.5. El instalador del servicio de movilidad de Lync Server define algunas marcas de ASP.NET para mejorar el rendimiento. IIS 7.5 se instala de manera predeterminada en Windows Server 2008 R2 y el instalador del servicio de movilidad cambia automáticamente los parámetros de ASP.NET. Si usa IIS 7.0 en Windows Server 2008, cambie manualmente estos parámetros.



Lync Server necesita la instalación de los módulos IIS siguientes:

> [!IMPORTANT]  
> Si la organización exige que localice IIS y todos los servicios web en una unidad que no sea la del sistema, cambie la ruta de acceso a la instalación de los archivos de Lync Server en el cuadro de diálogo Configuración. Si instala los archivos de instalación a esa ruta de acceso, incluido el OCSCore.msi, el resto de los archivos de Lync Server también se implementarán en esta unidad. Si desea información detallada sobre cómo cambiar la ubicación del INETPUB que emplea Windows Server Manager al instalar ISS, vea <a href="http://go.microsoft.com/fwlink/?linkid=216888%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=216888&amp;clcid=0xC0A</a>.



  - Contenido estático

  - Documento predeterminado

  - Errores HTTP

  - ASP.NET

  - Extensibilidad de .NET

  - Extensiones de Internet Server API (ISAPI)

  - Filtros ISAPI

  - Registro HTTP

  - Herramientas de registro

  - Seguimiento

  - Autenticación de Windows

  - Filtro de solicitudes

  - Compresión de contenido estático

  - Compresión de contenido dinámico

  - Consola de administración de IIS

  - Scripts y herramientas de administración de IIS

  - Autenticación anónima (se instala de forma predeterminada al instalar IIS)

  - Autenticación por asignación de certificados de clientes

En la tabla siguiente, se muestran los identificadores URI de los directorios virtuales para el acceso interno y los recursos del sistema de archivos a los que hacen referencia.

### Directorios virtuales para el acceso interno

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Característica</th>
<th>URI de directorio virtual</th>
<th>Hace referencia a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor de libreta de direcciones</p></td>
<td><p>https://<em>&lt;FQDN interno&gt;</em>/ABS/int/Handler</p></td>
<td><p>Ubicación de los archivos de descarga del servidor de libreta de direcciones para los usuarios internos.</p></td>
</tr>
<tr class="even">
<td><p>Servicio Detección automática</p></td>
<td><p>https://<em>&lt;FQDN interno&gt;</em>/Autodiscover</p></td>
<td><p>Ubicación del servicio Detección automática de Lync Server que localiza recursos de movilidad para usuarios de dispositivos móviles internos.</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones del cliente</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/AutoUpdate/Int</p></td>
<td><p>Ubicación de los archivos de actualización para los clientes basados en equipo internos.</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/Conf/Int</p></td>
<td><p>Ubicación de los recursos de conferencia para los usuarios internos.</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones de dispositivos</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/DeviceUpdateFiles_Int</p></td>
<td><p>Ubicación de los archivos de actualización de dispositivos de comunicaciones unificadas (UC) para los dispositivos UC internos.</p></td>
</tr>
<tr class="even">
<td><p>Reunión</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/etc/place/null</p></td>
<td><p>Ubicación del contenido de las reuniones de los usuarios internos.</p></td>
</tr>
<tr class="odd">
<td><p>Servicio de movilidad</p></td>
<td><p>https://<em>&lt;FQDN interno&gt;</em>/Mcx</p></td>
<td><p>Ubicación de los recursos del servicio de movilidad para usuarios de dispositivos móviles internos.</p></td>
</tr>
<tr class="even">
<td><p>Servicio de consulta web de libreta de direcciones y expansión de grupos</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/GroupExpansion/int/service.asmx</p></td>
<td><p>Ubicación del servicio web que habilita la expansión de grupos para los usuarios internos. Además, la ubicación del servicio de consulta web de libreta de direcciones que proporciona información de la lista global de direcciones a los clientes internos de Lync MobileMicrosoft Lync 2010 Mobile.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias telefónicas</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/PhoneConferencing/Int</p></td>
<td><p>Ubicación de los datos de conferencia telefónica para los usuarios internos.</p></td>
</tr>
<tr class="even">
<td><p>Actualizaciones de dispositivos</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/RequestHandler</p></td>
<td><p>Ubicación del controlador de solicitudes del Servicio web de actualización de dispositivos que habilita los dispositivos UC internos para cargar los registros y comprobar las actualizaciones.</p></td>
</tr>
<tr class="odd">
<td><p>Aplicación de grupo de respuesta</p></td>
<td><p>http://<em>&lt;FQDN interno&gt;</em>/RgsConfig</p>
<p>http://<em>&lt;FQDN interno&gt;</em>/RgsClients</p></td>
<td><p>Ubicación de la herramienta de configuración de grupos de respuesta.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> En el caso de los Grupos de servidores front-end en una configuración consolidada, implemente IIS para agregar servidores al grupo de servidores.



<table>
<thead>
<tr class="header">
<th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Seguridad Nota:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se debe usar el complemento administrativo de IIS para asignar el certificado usado por el servidor de componentes web de IIS.</td>
</tr>
</tbody>
</table>

