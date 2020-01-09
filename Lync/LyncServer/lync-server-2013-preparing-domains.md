---
title: 'Lync Server 2013: Preparar dominios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Preparar dominios para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

La preparación del dominio es el último paso en la preparación de los servicios de dominio de Active Directory para Lync Server 2013. El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.

Puede ejecutar la preparación del dominio en cualquier equipo del dominio donde vaya a implementar Lync Server. Debe preparar todos los dominios que van a hospedar Lync Server o los usuarios.

Si la herencia de permisos está deshabilitada o los permisos de usuario autenticados están deshabilitados en su organización, debe seguir pasos adicionales durante la preparación del dominio. Para obtener más información, consulte [preparar servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Si su organización usa unidades organizativas (OU) en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura a las unidades organizativas para el grupo usuarios autenticados. El acceso de lectura a los contenedores es necesario para la preparación del dominio. Si el grupo usuarios autenticados no tiene acceso de lectura a la unidad organizativa, ejecute el cmdlet **Grant-CsOuPermission** como se muestra en los siguientes ejemplos de código para conceder permisos de lectura para cada unidad organizativa.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Para obtener más información sobre el cmdlet **Grant-CsOuPermission** , consulte la documentación del shell de administración de Lync Server.

<div class="">


> [!TIP]  
> Para más información sobre las entradas ACE creadas en la raíz del dominio y en los contenedores usuarios, equipos y controladores de dominio, vea <A href="lync-server-2013-changes-made-by-domain-preparation.md">cambios realizados por la preparación del dominio en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ejecutar la preparación del dominio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

