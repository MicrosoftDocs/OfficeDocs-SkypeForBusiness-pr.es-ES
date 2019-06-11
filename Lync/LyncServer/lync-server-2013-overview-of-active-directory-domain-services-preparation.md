---
title: 'Lync Server 2013: Información general sobre la preparación de los Servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Información general sobre la preparación de los Servicios de dominio de Active Directory en Lync Server 2013

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
<th>Donde se ejecuta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparación del esquema de Active Directory en Lync Server 2013</a></p></td>
<td><p>Extiende el esquema de Active Directory agregando nuevas clases y atributos usados por Lync Server.</p>
<p>Se ejecuta una vez para cada bosque de su implementación donde se implementará Lync Server.</p></td>
<td><p>Contra el maestro de esquema en el dominio raíz de cada bosque donde se va a implementar Lync Server.</p>
<div>

> [!NOTE]  
> No es necesario ejecutar este paso en el dominio raíz si tiene permisos en el maestro de esquema, pero debe ser miembro del grupo de administradores de esquema en el dominio raíz y miembro del grupo de administradores de empresa en el maestro de esquema. En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de los usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de los usuarios.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparación del bosque para Lync Server 2013</a></p></td>
<td><p>Crea la configuración global y los grupos universales usados por Lync Server.</p>
<p>Se ejecuta una vez para cada bosque de su implementación donde se implementará Lync Server.</p></td>
<td><p>En el dominio raíz de cada bosque donde se va a implementar Lync Server. Para ejecutar este paso, debe ser miembro del grupo administradores de la empresa.</p>
<div>

> [!NOTE]  
> En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de los usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de los usuarios.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparar dominios para Lync Server 2013</a></p></td>
<td><p>Agrega permisos sobre los objetos que usarán los miembros de los grupos universales.</p>
<p>Ejecutar una vez por dominio de usuario o dominio de servidor.</p>
<div>

> [!NOTE]  
> Si va a migrar de Lync Server 2010 a Lync Server 2013, es posible que el Asistente para la implementación indique que ya se ha completado la preparación del dominio. No es necesario volver a ejecutar la preparación del dominio. No se cambiaron los permisos de Lync Server 2010 a Lync Server 2013.


</div></td>
<td><p>En un servidor miembro de cada dominio donde se va a implementar Lync Server. Para ejecutar este paso, debe ser miembro del grupo administradores de dominio.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013, al igual que Lync Server 2010, almacena gran parte de la información de configuración en el almacén central de administración en lugar de en AD DS como sucede en Office Communications Server 2007 R2. Sin embargo, la siguiente información se almacena en AD DS:

  - **Extensiones de esquema**:
    
      - Extensiones de objetos de usuario
    
      - Extensiones para las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores

<!-- end list -->

  - **Datos** (se almacena en el esquema extendido de Lync Server y en las clases de esquema existentes):
    
      - Identificador uniforme de recursos (URI) SIP de usuario y otra configuración de usuario
    
      - Objetos de contacto para aplicaciones como el operador de conferencia y el grupo de respuesta
    
      - Puntero al almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En Lync Server 2013, delega la configuración y la administración al otorgar permisos de configuración al grupo universal de RTCUniversalServerAdmins para que los miembros de ese grupo puedan instalar y activar Lync Server 2013 en un servidor local (después de que se haya agregado el servidor a la topología, publicada y habilitada). Los usuarios delegados deben ser administradores locales en el equipo en el que están instalando y activando Lync Server 2013, pero no es necesario que sean miembros del grupo administradores de dominio. También puede conceder permisos a los objetos de unidades organizativas (OU) especificadas para que los miembros de los grupos universales creados durante la preparación del bosque puedan tener acceso a esos objetos sin ser miembros del grupo administradores del dominio.

Para implementaciones nuevas de Lync Server 2013, la configuración global debe almacenarse en el contenedor de configuración. Si su organización está actualizando desde una versión anterior y aún así tiene una configuración global en el contenedor del sistema, el contenedor del sistema aún es compatible.

</div>

<div>

## <a name="see-also"></a>Vea también


[Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

