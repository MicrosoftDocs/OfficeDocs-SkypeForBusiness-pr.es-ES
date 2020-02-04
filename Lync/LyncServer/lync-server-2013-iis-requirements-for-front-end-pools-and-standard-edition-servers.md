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
ms.openlocfilehash: c00ffe97b77f20107fc3351a678c71e28bbc6675
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-19_

Para los servidores Standard Edition y los servidores front-end y directores, el instalador de Lync Server 2013 crea directorios virtuales en servicios de Internet Information Server (IIS) para los siguientes fines:

  - Para permitir que los usuarios descarguen archivos desde el servicio de libreta de direcciones

  - Para permitir que los clientes obtengan actualizaciones

  - Para habilitar la Conferencia

  - Para permitir que los usuarios descarguen contenido de la reunión

  - Para permitir a los usuarios expandir grupos de distribución

  - Para habilitar las conferencias telefónicas

  - Para habilitar las características de grupo de respuesta

Además, la actualización acumulativa para Lync Server 2010: el instalador de 2011 de noviembre crea directorios virtuales en IIS con los siguientes fines:

  - En servidores front-end o servidores Standard Edition para admitir la funcionalidad de movilidad, como la mensajería instantánea (mi) y la presencia, en dispositivos móviles

  - En servidores front-end o servidores Standard Edition y en directores para permitir que los dispositivos móviles descubran automáticamente los recursos de movilidad



> [!NOTE]
> Si va a implementar la movilidad, le recomendamos que use IIS 7,5. El instalador del servicio de movilidad de Lync Server establece algunas marcas ASP.NET para mejorar el rendimiento. IIS 7,5 se instala de forma predeterminada en Windows Server 2008 R2 y el instalador del servicio de movilidad cambia automáticamente la configuración de ASP.NET. Si usa IIS 7,0 en Windows Server 2008, tendrá que cambiar manualmente esta configuración.



Lync Server requiere que se instalen los siguientes módulos de IIS:


> [!IMPORTANT]
> Si su organización requiere que encuentre IIS y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo de configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server también se implementarán en esta unidad. Para más información sobre cómo cambiar la ubicación de INETPUB implementada por el administrador de Windows Server al <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>instalar IIS, consulte.


  - Contenido estático

  - Documento predeterminado

  - Errores HTTP

  - ASP.NET

  - Extensibilidad de .NET

  - Extensiones de API de servidor de Internet (ISAPI)

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

  - Autenticación anónima (se instala de forma predeterminada cuando se instala IIS)

  - Autenticación por asignación de certificados de clientes

En la tabla siguiente se enumeran los URI de los directorios virtuales de acceso interno y los recursos del sistema de archivos a los que hacen referencia.

### <a name="virtual-directories-for-internal-access"></a>Directorios virtuales para acceso interno

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
<th>Se refiere a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor de libreta de direcciones</p></td>
<td><p>https://&lt;FQDN&gt;interno de/ABS/int/handler</p></td>
<td><p>Ubicación del servidor de libretas de direcciones descargar archivos para usuarios internos.</p></td>
</tr>
<tr class="even">
<td><p>Servicio Detección automática</p></td>
<td><p>https://&lt;FQDN&gt;interno de/Autodiscover</p></td>
<td><p>Ubicación del servicio Detección automática de Lync Server que busca recursos de movilidad para usuarios internos de dispositivos móviles.</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones del cliente</p></td>
<td><p>http://&lt;FQDN&gt;interno de/AutoUpdate/int</p></td>
<td><p>Ubicación de los archivos de actualización para clientes internos basados en equipos.</p></td>
</tr>
<tr class="even">
<td><p>Conferencia</p></td>
<td><p>http://&lt;FQDN&gt;interno de/conf/int</p></td>
<td><p>Ubicación de los recursos de conferencia para usuarios internos.</p></td>
</tr>
<tr class="odd">
<td><p>Actualizaciones de dispositivos</p></td>
<td><p>FQDN&lt;&gt;http:///DeviceUpdateFiles_Int interno</p></td>
<td><p>Ubicación de los archivos de actualización de dispositivos de comunicaciones unificadas (UC) para dispositivos internos de UC.</p></td>
</tr>
<tr class="even">
<td><p>Satisfacción</p></td>
<td><p>http://&lt;FQDN&gt;interno de/etc/Place/null</p></td>
<td><p>Ubicación del contenido de la reunión para usuarios internos.</p></td>
</tr>
<tr class="odd">
<td><p>Servicio de movilidad</p></td>
<td><p>https://&lt;FQDN&gt;interno de/MCX</p></td>
<td><p>Ubicación de los recursos del servicio de movilidad para usuarios internos de dispositivos móviles.</p></td>
</tr>
<tr class="even">
<td><p>Servicio de consulta Web de expansión de grupo y libreta de direcciones</p></td>
<td><p>http://&lt;FQDN&gt;interno de/GroupExpansion/int/Service.asmx</p></td>
<td><p>Ubicación del servicio Web que permite la expansión de grupos para usuarios internos. Además, la ubicación del servicio de consultas Web de la libreta de direcciones que proporciona información de la lista global de direcciones a los clientes móviles internos de Lync Mobile Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Conferencias telefónicas</p></td>
<td><p>http://&lt;FQDN&gt;interno de/PhoneConferencing/int</p></td>
<td><p>Ubicación de los datos de la conferencia telefónica para usuarios internos.</p></td>
</tr>
<tr class="even">
<td><p>Actualizaciones de dispositivos</p></td>
<td><p>http://&lt;FQDN&gt;interno de/RequestHandler</p></td>
<td><p>Ubicación del controlador de solicitudes de servicio Web de actualización de dispositivos que permite a los dispositivos de UC internos cargar registros y comprobar si hay actualizaciones.</p></td>
</tr>
<tr class="odd">
<td><p>Aplicación de grupo de respuesta</p></td>
<td><p>http://&lt;FQDN&gt;interno de/RgsConfig</p>
<p>http://&lt;FQDN&gt;interno de/RgsClients</p></td>
<td><p>Ubicación de la herramienta de configuración de grupo de respuesta.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Para los grupos de servidores front-end en una configuración consolidada, debe implementar IIS antes de agregar servidores al grupo.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Debe usar el complemento administrativo de IIS para asignar el certificado utilizado por el servidor de componentes Web de IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

