---
title: Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-19_

Para los servidores Standard Edition y los servidores front-end, y los directores, el instalador de Lync Server 2013 crea directorios virtuales en Internet Information Services (IIS) con los fines siguientes:

  - Habilitar a los usuarios para descargar archivos desde el Servicio de libreta de direcciones

  - Para permitir que los clientes obtengan actualizaciones

  - Habilitar las conferencias

  - Permitir que los usuarios descarguen el contenido de las reuniones

  - Habilitar a los usuarios para expandir grupos de distribución

  - Habilitar las conferencias telefónicas

  - Habilitar las características de grupo de respuesta

Además, la actualización acumulativa de Lync Server 2010: el instalador de noviembre de 2011 crea directorios virtuales en IIS con los siguientes fines:

  - En los servidores front-end o servidores Standard Edition para admitir la funcionalidad de movilidad, como la mensajería instantánea (mi) y la presencia, en dispositivos móviles

  - En servidores front-end o servidores Standard Edition y en directores para permitir que los dispositivos móviles detecten automáticamente recursos de movilidad



> [!NOTE]
> Si va a implementar la movilidad, se recomienda usar IIS 7.5. El instalador del servicio de movilidad de Lync Server establece algunas marcas de ASP.NET para mejorar el rendimiento. IIS 7.5 se instala de manera predeterminada en Windows Server 2008 R2, y el instalador del servicio de movilidad cambia automáticamente la configuración de ASP.NET. Si usa IIS 7.0 en Windows Server 2008, debe cambiar manualmente estos parámetros.



Lync Server requiere que se instalen los siguientes módulos de IIS:


> [!IMPORTANT]
> Si su organización requiere que ubique IIS y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo de configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server también se implementarán en esta unidad. Para obtener información sobre cómo reubicar la INETPUB implementada por el administrador de servidores de Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>al instalar IIS, consulte.


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

En la siguiente tabla se recogen los identificadores URI de los directorios virtuales para el acceso interno y los recursos del sistema de archivos a los que hacen referencia.

### <a name="virtual-directories-for-internal-access"></a>Directorios virtuales para el acceso interno

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
<td><p>https://&lt;FQDN&gt;interno/ABS/int/handler</p></td>
<td><p>Ubicación de los archivos de descarga del servidor de libreta de direcciones para los usuarios internos.</p></td>
</tr>
<tr class="even">
<td><p>Servicio Detección automática</p></td>
<td><p>https://&lt;FQDN&gt;interno/Autodiscover</p></td>
<td><p>Ubicación del servicio Detección automática de Lync Server que localiza recursos de movilidad para usuarios de dispositivos móviles internos.</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones del cliente</p></td>
<td><p>http://&lt;FQDN&gt;interno/AutoUpdate/int</p></td>
<td><p>Ubicación de los archivos de actualización para los clientes basados en equipo internos.</p></td>
</tr>
<tr class="even">
<td><p>Multipunto</p></td>
<td><p>http://&lt;FQDN&gt;interno/conf/int</p></td>
<td><p>Ubicación de los recursos de conferencia para los usuarios internos.</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones de dispositivos</p></td>
<td><p>FQDN&lt;&gt;/DeviceUpdateFiles_Int http://interno</p></td>
<td><p>Ubicación de los archivos de actualización de dispositivos de comunicaciones unificadas (UC) para los dispositivos UC internos.</p></td>
</tr>
<tr class="even">
<td><p>Misma</p></td>
<td><p>http://&lt;FQDN&gt;interno/etc/Place/null</p></td>
<td><p>Ubicación del contenido de las reuniones de los usuarios internos.</p></td>
</tr>
<tr class="odd">
<td><p>Servicio de movilidad</p></td>
<td><p>https://&lt;FQDN&gt;interno/MCX</p></td>
<td><p>Ubicación de los recursos del servicio de movilidad para usuarios de dispositivos móviles internos.</p></td>
</tr>
<tr class="even">
<td><p>Servicio de consulta web de libreta de direcciones y expansión de grupos</p></td>
<td><p>http://&lt;FQDN&gt;interno/GroupExpansion/int/Service.asmx</p></td>
<td><p>Ubicación del servicio web que habilita la expansión de grupos para los usuarios internos. Además, la ubicación del servicio de consulta Web de la libreta de direcciones que proporciona información de la lista global de direcciones a clientes móviles internos de Lync Mobile Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias telefónicas</p></td>
<td><p>http://&lt;FQDN&gt;interno/PhoneConferencing/int</p></td>
<td><p>Ubicación de los datos de conferencia telefónica para los usuarios internos.</p></td>
</tr>
<tr class="even">
<td><p>Actualizaciones de dispositivos</p></td>
<td><p>http://&lt;FQDN&gt;interno/RequestHandler</p></td>
<td><p>Ubicación del controlador de solicitudes del Servicio web de actualización de dispositivos que habilita los dispositivos UC internos para cargar los registros y comprobar las actualizaciones.</p></td>
</tr>
<tr class="odd">
<td><p>Aplicación de grupo de respuesta</p></td>
<td><p>http://&lt;FQDN&gt;interno/RgsConfig</p>
<p>http://&lt;FQDN&gt;interno/RgsClients</p></td>
<td><p>Ubicación de la herramienta de configuración de grupos de respuesta.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Para los grupos de servidores front-end en una configuración consolidada, debe implementar IIS para poder agregar servidores al grupo.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se debe usar el complemento administrativo de IIS para asignar el certificado usado por el servidor de componentes web de IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

