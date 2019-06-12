---
title: Comprobar y crear informes de disponibilidad funcional para la autenticación Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Comprobar y crear informes de disponibilidad funcional para la autenticación Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-16_

Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.

Puede usar el cmdlet **Test-CsKerberosAccountAssignment** de Windows PowerShell para probar y notificar la preparación funcional de una asignación de sitio para la autenticación Kerberos. Este comando consulta el sitio especificado en el parámetro Identity requerido. El parámetro de informe opcional hace que el cmdlet escriba un informe HTML en C\\: logs en el equipo en el que se ejecuta el comando. El parámetro detallado opcional informa de la información de actividad en la pantalla.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>Para probar e informar sobre la preparación funcional de la autenticación Kerberos para un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en el equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute el siguiente comando:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Por ejemplo:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

