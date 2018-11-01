---
title: "Lync Server 2013: Informes de disponibilidad funcional para autenticación Kerberos"
TOCTitle: Comprobar y crear informes de disponibilidad funcional para la autenticación Kerberos
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48276793
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar y crear informes de disponibilidad funcional para la autenticación Kerberos en Lync Server 2013

 

_**Última modificación del tema:** 2012-01-16_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Use el cmdlet **Test-CsKerberosAccountAssignment** de Windows PowerShell para probar una asignación de sitio para la autenticación Kerberos y notificar que está lista desde el punto de vista funcional. Este comando realiza una consulta al sitio especificado en el parámetro Identity requerido. El parámetro opcional Report hace que el cmdlet escriba un informe HTML en C:\\Registros en el equipo donde se ejecuta el comando. El parámetro opcional Verbose notifica la información de actividad en la pantalla.

## Para probar la autenticación Kerberos de un sitio y notificar que está lista desde el punto de vista funcional

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo en el dominio ejecutando Lync Server 2013 o en el equipo donde estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Desde la línea de comandos, ejecute el siguiente comando:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Por ejemplo:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

