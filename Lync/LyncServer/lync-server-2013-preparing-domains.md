---
title: 'Lync Server 2013: preparación de dominios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f77c37b1694383284ec80667eba745109814c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Preparar dominios para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

La preparación del dominio es el último paso en la preparación de los servicios de dominio de Active Directory para Lync Server 2013. El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.

Puede ejecutar la preparación del dominio en cualquier equipo del dominio donde vaya a implementar Lync Server. Debe preparar cada dominio que hospede Lync Server o los usuarios.

Si la herencia de permisos está deshabilitada o los permisos de usuarios autenticados están deshabilitados en su organización, hay pasos adicionales que debe realizar durante la preparación de los dominios. Para obtener más información, consulte [preparar los servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Si en su organización se usan unidades organizativas (OU) en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura de las OU al grupo Usuarios autenticados. El acceso de lectura de los contenedores se necesita para preparar dominios. Si el grupo Usuarios autenticados no tiene acceso de lectura de la OU, ejecute el cmdlet **Grant-CsOuPermission** según se indica en los siguientes códigos de ejemplo, para conceder permisos de lectura a cada OU.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Para obtener más información sobre el cmdlet **Grant-CsOuPermission** , consulte la documentación del shell de administración de Lync Server.

<div class="">


> [!TIP]  
> Para obtener más información sobre las ACE creadas en la raíz del dominio y en los contenedores usuarios, equipos y controladores de dominio, vea <A href="lync-server-2013-changes-made-by-domain-preparation.md">cambios realizados por la preparación del dominio en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ejecutar la preparación del dominio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Uso de cmdlets para invertir la preparación del dominio para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

