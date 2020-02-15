---
title: 'Lync Server 2013: información general sobre la preparación de los servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3085caf0b118b20bf52a4ff82a14b399d1ee6594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Información general sobre la preparación de los servicios de dominio de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Para preparar los servicios de dominio de Active Directory para la implementación de Lync Server 2013, debe realizar tres pasos en una secuencia específica.

En la tabla siguiente se describen los pasos necesarios para preparar AD DS para Lync Server.

### <a name="active-directory-preparation-steps"></a>Pasos de preparación de Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Paso</th>
<th>Descripción</th>
<th>Dónde se ejecuta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparar el esquema de Active Directory en Lync Server 2013</a></p></td>
<td><p>Amplía el esquema de Active Directory agregando nuevas clases y atributos que se usan en Lync Server.</p>
<p>Ejecutarse una vez para cada bosque de la implementación donde se implementará Lync Server.</p></td>
<td><p>En el maestro de esquema en el dominio raíz de cada bosque donde se implementará Lync Server.</p>
<div>

> [!NOTE]  
> No es necesario realizar este paso en el dominio raíz si tiene permisos en el maestro de esquema, pero debe ser miembro del grupo Administradores de esquema en el dominio raíz y miembro del grupo Administradores de organización en el maestro de esquema. En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparar el bosque para Lync Server 2013</a></p></td>
<td><p>Crea la configuración global y los grupos universales que se usan en Lync Server.</p>
<p>Ejecutarse una vez para cada bosque de la implementación donde se implementará Lync Server.</p></td>
<td><p>En el dominio raíz de cada bosque donde se implementará Lync Server. Para llevar a cabo este paso, debe ser miembro del grupo Administradores de organización.</p>
<div>

> [!NOTE]  
> En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparar dominios para Lync Server 2013</a></p></td>
<td><p>Agrega permisos a los objetos que van a usar los miembros de grupos universales.</p>
<p>Ejecútelo una vez por dominio de usuario o dominio de servidor.</p>
<div>

> [!NOTE]  
> Si va a migrar de Lync Server 2010 a Lync Server 2013, es posible que el Asistente para la implementación indique que ya se ha completado la preparación del dominio. No necesita volver a ejecutar la preparación del dominio. No se cambiaron los permisos de Lync Server 2010 a Lync Server 2013.


</div></td>
<td><p>En un servidor miembro en cada dominio donde se implementará Lync Server. Para ejecutar este paso, debe ser miembro del grupo administradores del dominio.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013, al igual que Lync Server 2010, almacena gran parte de la información de configuración en el almacén de administración central en lugar de en AD DS como era el caso en Office Communications Server 2007 R2. Sin embargo, la siguiente información se almacena en AD DS:

  - **Extensiones de esquema**:
    
      - Extensiones de objetos de usuario
    
      - Extensiones para las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores

<!-- end list -->

  - **Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):
    
      - Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia
    
      - Una referencia al almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En Lync Server 2013, delegue la configuración y la administración mediante la concesión de permisos de instalación al grupo universal RTCUniversalServerAdmins para que los miembros de ese grupo puedan instalar y activar Lync Server 2013 en un servidor local (después de que el servidor se haya agregado al topología, publicada y habilitada). Los usuarios delegados deben ser administradores locales en el equipo en el que se van a instalar y activar Lync Server 2013, pero no es necesario que sean miembros del grupo administradores del dominio. También puede conceder permisos para objetos en unidades organizativas especificadas para que los miembros de los grupos universales creados durante la preparación del bosque puedan tener acceso a esos objetos sin ser miembros del grupo administradores del dominio.

Para las implementaciones nuevas de Lync Server 2013, la configuración global debe almacenarse en el contenedor de configuración. Si su organización está actualizando desde una versión anterior y todavía tiene una configuración global en el contenedor del sistema, el contenedor del sistema todavía es compatible.

</div>

<div>

## <a name="see-also"></a>Vea también


[Preparar el esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Preparar el bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

