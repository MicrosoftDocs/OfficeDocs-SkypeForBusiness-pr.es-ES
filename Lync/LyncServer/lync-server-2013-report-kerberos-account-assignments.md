---
title: 'Lync Server 2013: Creación de informes de asignación de cuentas Kerberos'
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
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Creación de informes de asignación de cuentas Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.

Puede usar el cmdlet **Get-CsKerberosAccountAssignment** para consultar información acerca de las asignaciones de cuentas de autenticación Kerberos y notificar la información sobre las asignaciones actuales de su implementación.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Para consultar asignaciones de cuentas de autenticación Kerberos para un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute uno de los siguientes comandos:
    
      - Para consultar todas las asignaciones de cuentas de autenticación Kerberos de su organización y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet sin ningún parámetro:
        
            Get-CsKerberosAccountAssignment
    
      - Para consultar todas las asignaciones de cuentas de autenticación Kerberos de su implementación y devolver información de asignación de sitio sobre cada una de ellas, ejecute el cmdlet con el parámetro Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Por ejemplo:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Para consultar todas las asignaciones de cuentas de autenticación Kerberos en un solo sitio y devolver información sobre cada una de ellas, ejecute el cmdlet con el parámetro Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Por ejemplo:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Si se especifica * SiteName para el parámetro de filtro, se devuelve información acerca de todos los sitios que contienen el nombre de sitio especificado en el identificador de sitio (por ejemplo, todos los sitios que contienen la cadena Redmond en el identificador de sitio).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

