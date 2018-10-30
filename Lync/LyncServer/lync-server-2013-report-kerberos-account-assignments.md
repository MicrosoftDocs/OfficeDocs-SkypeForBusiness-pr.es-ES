---
title: 'Lync Server 2013: Creación de informes de asignación de cuentas Kerberos'
TOCTitle: Creación de informes de asignación de cuentas Kerberos
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48275267
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de informes de asignación de cuentas Kerberos en Lync Server 2013

 

_**Última modificación del tema:** 2012-01-16_

Para completar correctamente este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Puede usar el cmdlet **Get-CsKerberosAccountAssignment** para consultar información sobre las asignaciones de cuenta de autenticación Kerberos e información de informe sobre las asignaciones actuales de su implementación.

## Para consultar las asignaciones de cuenta de autenticación Kerberos de un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio en que se ejecuta Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

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
        

        > [!NOTE]
        > La especificación de *SiteName para el parámetro Filter devuelve información acerca de todos los sitios que contienen el nombre de sitio especificado en cualquier lugar del identificador del sitio (por ejemplo, todos los sitios que contengan la cadena Redmond en el identificador del sitio).


