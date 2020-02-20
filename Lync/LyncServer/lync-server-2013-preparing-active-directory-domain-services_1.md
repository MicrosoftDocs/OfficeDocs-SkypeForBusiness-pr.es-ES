---
title: 'Lync Server 2013: preparar los servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b6e0e44367af86ea42099241ef3d9bbfa750133
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Preparación de los servicios de dominio de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-19_

En Lync Server 2013, puede usar el Asistente para la implementación de Lync Server para preparar los servicios de dominio de Active Directory o puede usar los cmdlets del shell de administración de Lync Server directamente. También puede usar la herramienta de línea de comandos ldifde.exe directamente en sus controladores de dominio, según se describe más adelante en este tema.

El Asistente para la implementación de Lync Server le guía por todas las tareas de preparación de Active Directory. El Asistente para la implementación ejecuta los cmdlets del shell de administración de Lync Server. Esta herramienta es útil para los entornos con una topología de dominio único y bosque único u otra topología similar.

<div>


> [!IMPORTANT]  
> Puede implementar Lync Server en un bosque o dominio donde los controladores de dominio ejecutan versiones de 32 bits de algunos sistemas operativos (para obtener más información, consulte <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure Requirements for Lync Server 2013</A>). Sin embargo, no puede usar el Asistente para la implementación de Lync Server para ejecutar el esquema, el bosque y la preparación del dominio en estos entornos porque el Asistente para la implementación y los archivos auxiliares son solo de 64 bits. En su lugar, puede usar ldifde.exe y los archivos .ldf asociados en un controlador de dominio de 32 bits para preparar el esquema, el bosque y el dominio. Consulte la sección “Uso de Ldifde.exe”, más adelante en este tema.



</div>

Puede usar los cmdlets del shell de administración de Lync Server para ejecutar tareas de forma remota o para entornos más complejos.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Requisitos previos de preparación de Active Directory

Debe ejecutar los pasos de preparación de Active Directory en un equipo que ejecute Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64 bits). La preparación de Active Directory requiere Shell de administración de Lync Server y OCSCore.

Se necesitan los siguientes componentes para ejecutar las tareas de preparación de Active Directory:

  - Componentes principales de Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Si tiene previsto usar el shell de administración de Lync Server para la preparación de Active Directory, primero debe ejecutar el Asistente para la implementación de Lync Server para instalar los componentes principales.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Para Windows Server 2012 y Windows Server 2012 R2, debe instalar y activar .NET Framework 4,5 mediante el administrador del servidor. Para obtener más información, consulte "Microsoft .NET Framework 4,5" en <A href="lync-server-2013-additional-software-requirements.md">requisitos de software adicionales para Lync Server 2013</A>. Para Windows Server&nbsp;2008&nbsp;R2, descargue e instale <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> desde el sitio web de Microsoft.

    
    </div>

  - Herramientas de administración remota del servidor (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Se necesitan algunas herramientas RSAT para ejecutar los pasos de preparación de Active Directory en un servidor miembro en lugar de en un controlador de dominio. Instale los complementos y las herramientas de línea de comandos de AD DS y el módulo de Active Directory para Windows PowerShell desde el nodo herramientas de AD DS y AD LDS del administrador del servidor.

    
    </div>

  - Paquete redistribuible de Microsoft Visual C++ 11
    
    <div>
    

    > [!NOTE]  
    > El programa de instalación solicita la instalación de este requisito previo si aún no está instalado en el equipo. El paquete se suministra de modo que no tenga que adquirirlo por separado.

    
    </div>

  - Windows PowerShell 3,0 (64 bits)
    
    Para Windows Server 2012 y Windows Server 2012 R2, Windows PowerShell 3,0 debe incluirse con la instalación de Lync Server 2013. Para Windows Server 2008 R2, debe instalar o actualizar a Windows PowerShell 3,0. Para obtener más información, consulte [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Roles y derechos administrativos

En la tabla siguiente, se muestran los roles y los derechos administrativos necesarios para cada tarea de preparación de Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Derechos de usuario necesarios para la preparación de Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procedure</th>
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


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets de preparación de Active Directory

En la siguiente tabla se comparan los cmdlets del shell de administración de Lync Server que se usan para preparar AD DS para los comandos de LcsCmd que se usan para preparar AD DS en Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlets comparados con LcsCmd

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


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Requisitos de Active Directory bloqueado

Si la herencia de permisos está deshabilitada o si deben deshabilitarse los permisos de usuarios autenticados en su organización, debe realizar pasos adicionales durante la preparación de los dominios. Para obtener más información, consulte [preparar los servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Permisos para contenedores personalizados

Si en su organización se usan contenedores personalizados en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura de los contenedores personalizados al grupo Usuarios autenticados. El acceso de lectura de los contenedores se necesita para preparar dominios. Para obtener más información, consulte [preparación de dominios para Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Uso de cmdlets y Ldifde.exe

El paso **preparar el esquema** en el Asistente para la implementación de Lync Server y el cmdlet **install-CsAdServerSchema** amplían el esquema de Active Directory en controladores de dominio que ejecutan un sistema operativo de 64 bits. Si necesita extender el esquema de Active Directory en un controlador de dominio que ejecute un sistema operativo de 32 bits, puede ejecutar el cmdlet **Install-CsAdServerSchema** de forma remota desde un servidor miembro (procedimiento recomendado). Sin embargo, si necesita ejecutar la preparación del esquema directamente en el controlador de dominio, puede usar la herramienta Ldifde.exe para importar los archivos del esquema. La herramienta Ldifde.exe viene incluida en la mayoría de las versiones del sistema operativo Windows.

Si usa Ldifde.exe para importar los archivos del esquema, debe importar los cuatro archivos, ya esté migrando desde una versión anterior o realizando una instalación limpia. Debe importarlos en el siguiente orden:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Los cuatro archivos .ldf se encuentran en el directorio \Support\Schema de la descarga o el medio de instalación.



</div>

Si desea usar Ldifde.exe para importar los cuatro archivos del esquema en un controlador de dominio que sea el maestro de esquema, use el siguiente formato:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Por ejemplo:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Use el parámetro b solo si ha iniciado sesión como otro usuario. Para ver más detalles acerca de los derechos de usuario necesarios, consulte la sección "Roles y derechos administrativos", anteriormente en este mismo tema.



</div>

Si desea usar Ldifde.exe para importar los cuatro archivos del esquema en un controlador de dominio que no sea el maestro de esquema, use el siguiente formato:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Para obtener más información sobre el uso de Ldifde, consulte el artículo 237677 de Microsoft Knowledge base, "Using LDIFDE to Import and Export Directory Objects to Active Directory" en [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204).

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Preparar el esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparar el bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

