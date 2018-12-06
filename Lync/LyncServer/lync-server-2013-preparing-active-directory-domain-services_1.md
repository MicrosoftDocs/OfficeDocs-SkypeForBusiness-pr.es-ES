---
title: 'Lync Server 2013: Preparar Servicios de dominio de Active Directory'
TOCTitle: Preparar Servicios de dominio de Active Directory
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48275767
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparar Servicios de dominio de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En Lync Server 2013  Asistente para la implementación de Lync Server, puede usar la Servicios de dominio de Active Directory para preparar Shell de administración de Lync Server, o puede usar los cmdlets del nm-csshell directamente. También puede usar la herramienta de línea de comandos ldifde.exe directamente en sus controladores de dominio, según se describe más adelante en este tema.

La Asistente para la implementación de Lync Server sirve de guía en cada tarea de preparación de Active Directory. El Asistente para la implementación ejecuta cmdlets del Shell de administración de Lync Server. Esta herramienta es útil para los entornos con una topología de dominio único y bosque único u otra topología similar.

> [!IMPORTANT]  
> Puede implementar Lync Server en un bosque o un dominio donde los controladores de dominio ejecuten las versiones de 32 bits de algunos sistemas operativos (para ver los detalles, consulte <a href="lync-server-2013-active-directory-infrastructure-requirements.md">Requisitos de infraestructura de Active Directory para Lync Server 2013</a>). Sin embargo, no puede usar la Asistente para la implementación de Lync Server para ejecutar la preparación de dominios, bosques y esquemas en estos entornos, porque el Asistente para la implementación y los archivos de apoyo son solo de 64 bits. En su lugar, puede usar ldifde.exe y los archivos .ldf asociados en un controlador de dominio de 32 bits para preparar el esquema, el bosque y el dominio. Consulte la sección “Uso de Ldifde.exe”, más adelante en este tema.



Puede usar los cmdlets de Shell de administración de Lync Server para ejecutar las tareas de forma remota o para entornos más complejos.

## Requisitos previos de preparación de Active Directory

Debe ejecutar los pasos de preparación de Active Directory en un equipo que ejecute Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64 bits). La preparación de Active Directory requiere Shell de administración de Lync Server y OCSCore.

Se necesitan los siguientes componentes para ejecutar las tareas de preparación de Active Directory:

  - Componentes principales de Lync Server (OCScore.msi)
    

    > [!NOTE]
    > Si piensa usar Shell de administración de Lync Server para preparar Active Directory, debe ejecutar primero la Asistente para la implementación de Lync Server para instalar los componentes principales.



  - Microsoft .NET Framework 4.5
    

    > [!NOTE]
    > Para Windows Server 2012 y Windows Server 2012 R2, instale y active .NET Framework 4.5 usando el Administrador de servidores. Si desea más información, consulte "Microsoft .NET Framework 4.5" en <A href="lync-server-2013-additional-software-requirements.md">Requisitos adicionales de software para Lync Server 2013</A>. Para Windows Server&nbsp;2008&nbsp;R2, descargue e instale <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> en el sitio web de Microsoft.



  - Herramientas de administración remota del servidor (RSAT)
    

    > [!NOTE]
    > Se necesitan algunas herramientas RSAT para ejecutar los pasos de preparación de Active Directory en un servidor miembro en lugar de en un controlador de dominio. Instale las herramientas de línea de comandos y los complementos de AD DS y el módulo de Active Directory para Windows PowerShell desde el nodo de herramientas de AD DS y AD LDS en el Administrador de servidores.



  - Paquete redistribuible de Microsoft Visual C++ 11
    

    > [!NOTE]
    > El programa de instalación solicita la instalación de este requisito previo si aún no está instalado en el equipo. El paquete se suministra de modo que no tenga que adquirirlo por separado.



  - Windows PowerShell 3.0 (64 bits)
    
    Para Windows Server 2012 y Windows Server 2012 R2, Windows PowerShell 3.0 debería incluirse con la instalación de Lync Server 2013. Para Windows Server 2008 R2, deberá instalar o actualizar a Windows PowerShell 3.0. Para más información, vea [Instalar Windows PowerShell 3.0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

## Roles y derechos administrativos

En la tabla siguiente, se muestran los roles y los derechos administrativos necesarios para cada tarea de preparación de Active Directory.

### Derechos de usuario necesarios para la preparación de Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procedimiento</th>
<th>Derechos o roles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Preparación del esquema</p></td>
<td><p>Miembro del grupo de Administradores de esquema en el dominio de raíz del bosque y derechos de administrador en el maestro de esquema</p></td>
</tr>
<tr class="even">
<td><p>Preparación del bosque</p></td>
<td><p>Miembro del grupo de Administradores Enterprise en el bosque</p></td>
</tr>
<tr class="odd">
<td><p>Preparación del dominio</p></td>
<td><p>Miembro del grupo Administradores Enterprise o Administradores de dominio en el dominio especificado</p></td>
</tr>
</tbody>
</table>


## Cmdlets de preparación de Active Directory

La siguiente tabla compara los cmdlets del Shell de administración de Lync Server que se usan para preparar AD DS con los comandos de LcsCmd que se usan para preparar AD DS en Microsoft Office Communications Server 2007 R2.

### Cmdlets comparados con LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlets</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


## Requisitos de Active Directory bloqueado

Si la herencia de permisos está deshabilitada o si deben deshabilitarse los permisos de usuarios autenticados en su organización, debe realizar pasos adicionales durante la preparación de los dominios. Para ver más detalles, consulte [Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

## Permisos para contenedores personalizados

Si en su organización se usan contenedores personalizados en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura de los contenedores personalizados al grupo Usuarios autenticados. El acceso de lectura de los contenedores se necesita para preparar dominios. Para ver más detalles, consulte [Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md).

## Uso de cmdlets y Ldifde.exe

El paso de **Preparar esquema** en la Asistente para la implementación de Lync Server y el cmdlet **Install-CsAdServerSchema** extienden el esquema de Active Directory en los controladores de dominio que ejecutan un sistema operativo de 64 bits. Si necesita extender el esquema de Active Directory en un controlador de dominio que ejecute un sistema operativo de 32 bits, puede ejecutar el cmdlet **Install-CsAdServerSchema** de forma remota desde un servidor miembro (procedimiento recomendado). Sin embargo, si necesita ejecutar la preparación del esquema directamente en el controlador de dominio, puede usar la herramienta Ldifde.exe para importar los archivos del esquema. La herramienta Ldifde.exe viene incluida en la mayoría de las versiones del sistema operativo Windows.

Si usa Ldifde.exe para importar los archivos del esquema, debe importar los cuatro archivos, ya esté migrando desde una versión anterior o realizando una instalación limpia. Debe importarlos en el siguiente orden:

1.  ExternalSchema.ldf

2.  ServerSchema.ldf

3.  BackCompatSchema.ldf

4.  VersionSchema.ldf


> [!NOTE]
> Los cuatro archivos .ldf se encuentran en el directorio \Support\Schema de la descarga o el medio de instalación.



Si desea usar Ldifde.exe para importar los cuatro archivos del esquema en un controlador de dominio que sea el maestro de esquema, use el siguiente formato:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Por ejemplo:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password


> [!NOTE]
> Use el parámetro b solo si ha iniciado sesión como otro usuario. Para ver más detalles acerca de los derechos de usuario necesarios, consulte la sección "Roles y derechos administrativos", anteriormente en este mismo tema.



Si desea usar Ldifde.exe para importar los cuatro archivos del esquema en un controlador de dominio que no sea el maestro de esquema, use el siguiente formato:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Para obtener información detallada sobre el uso de Ldifde, consulte el artículo 237677 de la Microsoft Knowledge Base, "Uso de LDIFDE para importar y exportar a Active Directory objetos del directorio", en [http://go.microsoft.com/fwlink/?linkid=132204\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=132204%26clcid=0xc0a).

## En esta sección

  - [Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)

