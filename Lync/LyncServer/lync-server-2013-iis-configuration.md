---
title: 'Lync Server 2013: configuración de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d284fa2082c886a583baf116893f792535a096b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Configuración de IIS en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-17_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio.

Antes de configurar e instalar el servidor front-end para Lync Server 2013, Standard Edition o el primer servidor front-end en un grupo de servidores, instale y configure el rol de servidor y los servicios web para Internet Information Services (IIS).

<div class=" ">


> [!IMPORTANT]  
> Si su organización requiere que ubique IIS y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server 2013 en el cuadro de diálogo de configuración cuando instala inicialmente Lync Server 2013 Herramientas administrativas. Las herramientas administrativas se deben instalar antes que IIS. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 también se implementarán en esta unidad. Para Dtails, consulte <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 Administrative Tools</A>. Para obtener información sobre cómo reubicar la INETPUB implementada por el administrador de servidores de Windows <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>al instalar IIS, consulte.



</div>

En la tabla siguiente se indican los servicios de rol IIS 7,5 necesarios.

### <a name="iis-75-role-services"></a>Servicios de rol de IIS 7,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Encabezado de rol</th>
<th>Servicio de rol</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Características HTTP comunas instaladas</p></td>
<td><p>Contenido estático</p></td>
</tr>
<tr class="even">
<td><p>Características HTTP comunas instaladas</p></td>
<td><p>Documento predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Características HTTP comunas instaladas</p></td>
<td><p>Errores HTTP</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 también necesita ASP. NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensibilidad de .NET</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensiones de Internet Server API (ISAPI)</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Filtros ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Estado y diagnóstico</p></td>
<td><p>Registro HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Estado y diagnóstico</p></td>
<td><p>Herramientas de registro</p></td>
</tr>
<tr class="even">
<td><p>Estado y diagnóstico</p></td>
<td><p>Seguimiento</p></td>
</tr>
<tr class="odd">
<td><p>Seguridad</p></td>
<td><p>Autenticación anónima (instalada y habilitada de forma predeterminada)</p></td>
</tr>
<tr class="even">
<td><p>Seguridad</p></td>
<td><p>Autenticación de Windows</p></td>
</tr>
<tr class="odd">
<td><p>Seguridad</p></td>
<td><p>Autenticación por asignación de certificados de clientes</p></td>
</tr>
<tr class="even">
<td><p>Seguridad</p></td>
<td><p>Filtrado de solicitudes</p></td>
</tr>
<tr class="odd">
<td><p>Rendimiento</p></td>
<td><p>Compresión de contenido estático</p>
<p>Compresión de contenido dinámico</p></td>
</tr>
<tr class="even">
<td><p>Herramientas de administración</p></td>
<td><p>Consola de administración de IIS</p></td>
</tr>
<tr class="odd">
<td><p>Herramientas de administración</p></td>
<td><p>Scripts y herramientas de administración de IIS</p></td>
</tr>
</tbody>
</table>


En el sistema operativo Windows Server 2008 R2 SP1 x64, puede usar Windows PowerShell 2,0. Primero debe importar el módulo ServerManager y, a continuación, instalar el rol y los servicios de rol de IIS 7.5.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> La autenticación anónima está instalada de forma predeterminada con el rol del servidor IIS. Puede administrar la autenticación anónima después de instalar el IIS. Para obtener más información, consulte "habilitar la autenticación anónima (IIS 7 <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>)" en.



</div>

En la tabla siguiente se indican los servicios de rol IIS 8,0 e IIS 8,5 necesarios para Windows Server 2012 y Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Para Windows Server 2012 y Windows Server 2012 R2, el cmdlet Add-WindowsFeature se ha reemplazado por el cmdlet install-WindowsFeature. Para obtener más información, vea <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Servicios de rol IIS 8,0 e IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Encabezado de rol</th>
<th>Servicio de rol</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor web (IIS)</p></td>
<td><p>Servidor web</p></td>
</tr>
<tr class="even">
<td><p>Características comunes de HTTP</p></td>
<td><p>Documento predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Características comunes de HTTP</p></td>
<td><p>Examen de directorios</p></td>
</tr>
<tr class="even">
<td><p>Características comunes de HTTP</p></td>
<td><p>Errores HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Características comunes de HTTP</p></td>
<td><p>Contenido estático</p></td>
</tr>
<tr class="even">
<td><p>Características HTTP comunes</p></td>
<td><p>Redirección HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Estado y diagnóstico</p></td>
<td><p>Registro HTTP</p></td>
</tr>
<tr class="even">
<td><p>Estado y diagnóstico</p></td>
<td><p>Herramientas de registro</p></td>
</tr>
<tr class="odd">
<td><p>Estado y diagnóstico</p></td>
<td><p>Supervisor de solicitud</p></td>
</tr>
<tr class="even">
<td><p>Estado y diagnóstico</p></td>
<td><p>Seguimiento</p></td>
</tr>
<tr class="odd">
<td><p>Seguridad</p></td>
<td><p>Filtrado de solicitudes</p></td>
</tr>
<tr class="even">
<td><p>Seguridad</p></td>
<td><p>Autenticación básica</p></td>
</tr>
<tr class="odd">
<td><p>Seguridad</p></td>
<td><p>Autenticación por asignación de certificados de clientes</p></td>
</tr>
<tr class="even">
<td><p>Seguridad</p></td>
<td><p>Autenticación de Windows</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensibilidad de .net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensibilidad de .net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensiones ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Filtros ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Inclusiones del servidor</p></td>
</tr>
<tr class="even">
<td><p>Herramientas de administración</p></td>
<td><p>Consola de administración de IIS</p></td>
</tr>
<tr class="odd">
<td><p>Herramientas de administración</p></td>
<td><p>Compatibilidad con la metabase de IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Herramientas de administración</p></td>
<td><p>Scripts y herramientas de administración de IIS</p></td>
</tr>
<tr class="odd">
<td><p>Características de .net 3,5 Framework</p></td>
<td><p>.Net 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Características de .net 4,5 Framework</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Características de .net 4,5 Framework</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="even">
<td><p>Características de .net 4,5 Framework</p></td>
<td><p>Activación HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Características de .net 4,5 Framework</p></td>
<td><p>Uso compartido de puertos TCP</p></td>
</tr>
<tr class="even">
<td><p>Servicio de transferencia inteligente en segundo plano</p></td>
<td><p>Extensiones de servidor IIS</p></td>
</tr>
<tr class="odd">
<td><p>Servicios de Escritura con lápiz y Escritura a mano</p></td>
<td><p>Servicios de Escritura con lápiz y Escritura a mano</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Infraestructura e interfaces de usuario</p></td>
<td><p>Infraestructura y herramientas de administración gráficas</p></td>
</tr>
<tr class="even">
<td><p>Infraestructura e interfaces de usuario</p></td>
<td><p>Experiencia de escritorio</p></td>
</tr>
<tr class="odd">
<td><p>Infraestructura e interfaces de usuario</p></td>
<td><p>Shell gráfico del servidor</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3,5</p></td>
<td><p>Windows Identity Foundation 3,5</p></td>
</tr>
<tr class="odd">
<td><p>Servicio de activación de procesos de Windows</p></td>
<td><p>Modelo de proceso</p></td>
</tr>
<tr class="even">
<td><p>Servicio de activación de procesos de Windows</p></td>
<td><p>API de configuración</p></td>
</tr>
</tbody>
</table>


En Windows Server 2012 y Windows Server 2012 R2, puede usar Windows PowerShell 3,0 para instalar los requisitos de IIS. Usar el módulo ServerManager en Windows PowerShell 3,0, escriba:

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> New with Windows Server 2012 es el parámetro – Source que define dónde se puede encontrar el medio de origen de Windows Server 2012. El medio puede definirse como una unidad de DVD (por ejemplo, D:\Sources\Sxs) o en un recurso compartido de red en el que se han copiado los archivos \\multimedia (por ejemplo, fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

