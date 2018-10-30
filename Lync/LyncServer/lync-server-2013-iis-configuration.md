---
title: 'Lync Server 2013: Configuración de IIS'
TOCTitle: Configuración de IIS
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48276412
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de IIS en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio.

Antes de configurar e instalar el Servidor front-end para Lync Server 2013, Standard Edition o el primer Servidor front-end de un grupo de servidores, debe instalar y configurar el rol del servidor y los Servicios web para Servicios de Internet Information Server (IIS).

> [!IMPORTANT]  
> Si su organización exige que localice IIS y todos los servicios web en una unidad que no sea la del sistema, puede cambiar la ruta de acceso a la instalación de los archivos de Lync Server 2013 en el cuadro de diálogo de instalación cuando instale por primera vez las herramientas administrativas de Lync Server 2013. Las herramientas administrativas se deben instalar antes que IIS. Si instala los archivos de instalación en esta ruta de acceso, incluido el archivo OCSCore.msi, el resto de los archivos de Lync Server 2013 se implementará también en esta unidad. Para más información, vea <a href="lync-server-2013-install-lync-server-administrative-tools.md">Instalar las herramientas administrativas de Lync Server 2013</a>. Para más información sobre cómo cambiar la ubicación del directorio INETPUB implementado por Windows Server Manager al instalar IIS, vea <a href="http://go.microsoft.com/fwlink/?linkid=216888" class="uri">http://go.microsoft.com/fwlink/?linkid=216888</a>.



En la siguiente tabla se indican los servicios de rol necesarios para IIS 7.5.

### Servicios de rol de IIS 7.5

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
<td><p>Características HTTP comunes instaladas</p></td>
<td><p>Contenido estático</p></td>
</tr>
<tr class="even">
<td><p>Características HTTP comunes instaladas</p></td>
<td><p>Documento predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Características HTTP comunes instaladas</p></td>
<td><p>Errores HTTP</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 también requiere ASP.NET 4.5</p></td>
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


En el sistema operativo Windows Server 2008 R2 SP1 x64, puede usar Windows PowerShell 2.0. Primero debe importar el módulo ServerManager y, después, instalar el rol y los servicios de rol de IIS 7.5.

```
Import-Module ServerManager
```
```
Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
```


> [!NOTE]
> La autenticación anónima se instala de forma predeterminada con el rol del servidor IIS. Puede administrar la autenticación anónima después de instalar IIS. Para más información, vea "Habilitar la autenticación anónima (IIS 7)" en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=203935">http://go.microsoft.com/fwlink/?linkid=203935</A>.



En la siguiente tabla se indican los servicios de rol de IIS 8.0 e IIS 8.5 necesarios para Windows Server 2012 y Windows Server 2012 R2.


> [!NOTE]
> Para Windows Server 2012 y Windows Server 2012 R2, el cmdlet Add-WindowsFeature ha sido sustituido por el cmdlet Install-WindowsFeature. Encontrará más información en <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.



### Servicios de rol de IIS 8.0 e IIS 8.5

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
<td><p>Características HTTP comunes</p></td>
<td><p>Documento predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>Características HTTP comunes</p></td>
<td><p>Examen de directorios</p></td>
</tr>
<tr class="even">
<td><p>Características HTTP comunes</p></td>
<td><p>Errores HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Características HTTP comunes</p></td>
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
<td><p>Monitor de solicitudes</p></td>
</tr>
<tr class="even">
<td><p>Estado y diagnóstico</p></td>
<td><p>Seguimiento</p></td>
</tr>
<tr class="odd">
<td><p>Seguridad</p></td>
<td><p>Filtro de solicitudes</p></td>
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
<td><p>Extensibilidad de .NET 3,5</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>Extensibilidad de .NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.NET 3,5</p></td>
</tr>
<tr class="even">
<td><p>Desarrollo de aplicaciones</p></td>
<td><p>ASP.NET 4.5</p></td>
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
<td><p>Inclusiones del lado servidor</p></td>
</tr>
<tr class="even">
<td><p>Herramientas de administración</p></td>
<td><p>Consola de administración de IIS</p></td>
</tr>
<tr class="odd">
<td><p>Herramientas de administración</p></td>
<td><p>Compatibilidad con la metabase de IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Herramientas de administración</p></td>
<td><p>Scripts y herramientas de administración de IIS</p></td>
</tr>
<tr class="odd">
<td><p>Características de .NET 3,5 Framework</p></td>
<td><p>.NET 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Características de .NET 4.5 Framework</p></td>
<td><p>.NET Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Características de .NET 4.5 Framework</p></td>
<td><p>ASP.NET 4.5</p></td>
</tr>
<tr class="even">
<td><p>Características de .NET 4.5 Framework</p></td>
<td><p>Activación HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Características de .NET 4.5 Framework</p></td>
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
<td><p>Infraestructura y herramientas de administración de gráficos</p></td>
</tr>
<tr class="even">
<td><p>Infraestructura e interfaces de usuario</p></td>
<td><p>Experiencia de escritorio</p></td>
</tr>
<tr class="odd">
<td><p>Infraestructura e interfaces de usuario</p></td>
<td><p>Shell gráfico de servidor</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
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


En Windows Server 2012 y Windows Server 2012 R2, se puede usar Windows PowerShell 3.0 para instalar los requisitos de IIS. Con el módulo ServerManager de Windows PowerShell 3.0, escriba:

```
Import-Module ServerManager
```

```
Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
```


> [!IMPORTANT]  
> Una novedad de Windows Server 2012 es el parámetro –Source que define dónde se encuentran los medios de origen de Windows Server 2012. Los medios se pueden definir como una unidad de DVD (por ejemplo, D:\Sources\Sxs) o como un recurso compartido de red en los que se copiaron los archivos multimedia (por ejemplo, \\fileserver\windows2012\sources\Sxs).



## Vea también

#### Conceptos

[Requisitos de IIS para grupos de servidores front-end y servidores Standard Edition en Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

