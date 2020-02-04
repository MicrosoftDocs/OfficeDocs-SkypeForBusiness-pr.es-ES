---
title: 'Lync Server 2013: Preparar Servicios de dominio de Active Directory'
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
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Preparar Servicios de dominio de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-19_

En Lync Server 2013, puede usar el Asistente para la implementación de Lync Server para preparar los servicios de dominio de Active Directory, o bien puede usar los cmdlets del shell de administración de Lync Server directamente. También puede usar la herramienta de línea de comandos LDIFDE. exe directamente en los controladores de dominio, tal y como se describe más adelante en este tema.

El Asistente para la implementación de Lync Server le guiará a través de cada tarea de preparación de Active Directory. El Asistente para la implementación ejecuta los cmdlets del shell de administración de Lync Server. Esta herramienta es útil para entornos con un único dominio y topología de bosque, u otra topología similar.

<div>


> [!IMPORTANT]  
> Puede implementar Lync Server en un bosque o dominio donde los controladores de dominio ejecuten versiones de 32 bits de algunos sistemas operativos (para obtener información detallada, consulte <A href="lync-server-2013-active-directory-infrastructure-requirements.md">requisitos de la infraestructura de Active Directory para Lync Server 2013</A>). Sin embargo, no puede usar el Asistente para la implementación de Lync Server para ejecutar la preparación del esquema, el bosque y el dominio en estos entornos porque el Asistente para la implementación y los archivos auxiliares son solo de 64 bits. En su lugar, puede usar Ldifde. exe y los archivos. ldf asociados en un controlador de dominio de 32 bits para preparar el esquema, el bosque y el dominio. Consulte la sección "usar cmdlets y Ldifde. exe" más adelante en este tema.



</div>

Puede usar los cmdlets del shell de administración de Lync Server para ejecutar tareas de forma remota o para entornos más complejos.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Requisitos previos para la preparación de Active Directory

Debe ejecutar los pasos de preparación de Active Directory en un equipo con Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64-bit). La preparación de Active Directory requiere el shell de administración de Lync Server y OCSCore.

Los siguientes componentes son necesarios para ejecutar las tareas de preparación de Active Directory:

  - Componentes principales de Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Si planea usar el shell de administración de Lync Server para la preparación de Active Directory, debe ejecutar el Asistente para la implementación de Lync Server en primer lugar para instalar los componentes básicos.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Para Windows Server 2012 y Windows Server 2012 R2, debe instalar y activar .NET Framework 4,5 mediante el administrador del servidor. Para obtener más información, vea "Microsoft .NET Framework 4,5" en <A href="lync-server-2013-additional-software-requirements.md">requisitos de software adicionales para Lync Server 2013</A>. Para Windows Server&nbsp;2008&nbsp;R2, descargue e instale <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> desde el sitio web de Microsoft.

    
    </div>

  - Herramientas de administración de servidor remoto (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Algunas herramientas de RSAT son necesarias si ejecuta pasos de preparación de Active Directory en un servidor miembro, en lugar de hacerlo en un controlador de dominio. Instale los complementos y las herramientas de línea de comandos de AD DS y el módulo de Active Directory para Windows PowerShell desde el nodo de herramientas de AD DS y AD LDS en el administrador del servidor.

    
    </div>

  - Paquete redistribuible de Microsoft Visual C++ 11
    
    <div>
    

    > [!NOTE]  
    > El programa de instalación le pedirá que instale este requisito previo si aún no está instalado en el equipo. El paquete se proporciona por ti y no tendrá que adquirirlo por separado.

    
    </div>

  - Windows PowerShell 3,0 (64 bits)
    
    Para Windows Server 2012 y Windows Server 2012 R2, Windows PowerShell 3,0 debe estar incluido con la instalación de Lync Server 2013. Para Windows Server 2008 R2, debe instalar o actualizar a Windows PowerShell 3,0. Para obtener más información, consulte [instalar Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Derechos y roles de administrador

En la tabla siguiente se muestran los derechos de administración y los roles necesarios para cada tarea de preparación de Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Derechos de usuario necesarios para la preparación de Active Directory

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
<td><p>Miembro del grupo de administradores de esquema para el dominio raíz del bosque y derechos de administrador en el maestro de esquema</p></td>
</tr>
<tr class="even">
<td><p>Preparación del bosque</p></td>
<td><p>Miembro del grupo administradores de la organización del bosque</p></td>
</tr>
<tr class="odd">
<td><p>Preparación del dominio</p></td>
<td><p>Miembro de administradores de empresa o de administradores de dominio para el dominio especificado</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets de preparación de Active Directory

En la siguiente tabla se comparan los cmdlets del shell de administración de Lync Server que se usan para preparar AD DS para los comandos de LcsCmd que se usan para preparar AD DS en Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Comparación de los cmdlets con LcsCmd

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
<td><p>LcsCmd/Forest/Action: SchemaPrep/SchemaType: Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>LcsCmd/Forest/Action: CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Requisitos de Active Directory bloqueados

Si la herencia de permisos está deshabilitada o los permisos de usuario autenticados deben estar deshabilitados en su organización, debe seguir pasos adicionales durante la preparación del dominio. Para obtener más información, consulte [preparar servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Permisos de contenedor personalizados

Si su organización usa contenedores personalizados en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura a los contenedores personalizados para el grupo usuarios autenticados. El acceso de lectura a los contenedores es necesario para la preparación del dominio. Para obtener más información, consulte [preparación de dominios para Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Usar cmdlets y Ldifde. exe

El paso **preparar el esquema** del Asistente para la implementación de Lync Server y el cmdlet **install-CsAdServerSchema** amplían el esquema de Active Directory en controladores de dominio que ejecutan un sistema operativo de 64 bits. Si necesita ampliar el esquema de Active Directory en un controlador de dominio que ejecuta un sistema operativo de 32 bits, puede ejecutar el cmdlet **install-CsAdServerSchema** de forma remota desde un servidor miembro (método recomendado). Sin embargo, si necesita ejecutar la preparación del esquema directamente en el controlador de dominio, puede usar la herramienta Ldifde. exe para importar los archivos de esquema. La herramienta Ldifde. exe viene con la mayoría de las versiones del sistema operativo Windows.

Si usa Ldifde. exe para importar los archivos de esquema, debe importar los cuatro archivos, independientemente de si va a migrar desde una versión anterior o realizar una instalación limpia. Debe importarlas en la siguiente secuencia:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Los cuatro archivos. ldf se encuentran en \Support\Schema directorio de los medios de instalación o descargar.



</div>

Para usar Ldifde. exe para importar los cuatro archivos de esquema en un controlador de dominio que sea el maestro de esquema, use el siguiente formato:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Por ejemplo:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Use el parámetro b solo si ha iniciado sesión como un usuario diferente. Para obtener más información sobre los derechos de usuario necesarios, vea la sección "derechos y roles de administrador" anteriormente en este tema.



</div>

Para usar Ldifde. exe para importar los cuatro archivos de esquema en un controlador de dominio que no sea el maestro de esquema, use el siguiente formato:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Para obtener detalles sobre el uso de Ldifde, consulte el artículo 237677 de Microsoft Knowledge base, "uso de LDIFDE para importar y exportar objetos de [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)directorio a Active Directory", en.

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

