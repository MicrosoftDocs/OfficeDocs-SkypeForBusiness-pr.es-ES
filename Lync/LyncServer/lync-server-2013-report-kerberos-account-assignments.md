---
title: 'Lync Server 2013: informes de asignación de cuentas Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9576d772aa340e7d578186974fb00418479ea691
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Informar sobre las asignaciones de cuentas Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Puede usar el cmdlet **Get-CsKerberosAccountAssignment** para consultar información sobre las asignaciones de cuenta de autenticación Kerberos e información de informe sobre las asignaciones actuales de su implementación.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Para consultar las asignaciones de cuenta de autenticación Kerberos de un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute uno de los comandos que se indican a continuación:
    
      - Para consultar todas las asignaciones de cuenta de autenticación Kerberos de su organización y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet sin ningún parámetro:
        
            Get-CsKerberosAccountAssignment
    
      - Para consultar todas las asignaciones de cuenta de autenticación Kerberos de su implementación y devolver información de asignación del sitio sobre cada una de ellas, ejecute el cmdlet con el parámetro Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Por ejemplo:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Para consultar todas las asignaciones de cuenta de autenticación Kerberos de un único sitio y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet con el parámetro Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Por ejemplo:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > La especificación de *nombre_sitio para el parámetro Filter devuelve información acerca de todos los sitios que contienen el nombre de sitio especificado en cualquier lugar del identificador del sitio (por ejemplo, todos los sitios que contengan la cadena Redmond en el identificador del sitio).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

