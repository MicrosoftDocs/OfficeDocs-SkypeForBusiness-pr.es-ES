---
title: 'Lync Server 2013: Quitar la autenticación Kerberos de un sitio'
TOCTitle: Quitar la autenticación Kerberos de un sitio
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48276037
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar la autenticación Kerberos de un sitio en Lync Server 2013

 

_**Última modificación del tema:** 2012-01-16_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Si necesita quitar la autenticación Kerberos de un sitio o retirar un sitio, debe quitar la asignación de cuenta de autenticación Kerberos del sitio, usando el cmdlet **Remove-CsKerberosAccountAssignment**. Siga el procedimiento que se indica a continuación para quitar la asignación de cuenta de autenticación Kerberos, que quita la asignación de todos los equipos del sitio.

> [!WARNING]  
> Si va a retirar permanentemente la cuenta habilitada para Kerberos, debe usar los equipos y usuarios de Active Directory para eliminarla de Servicios de dominio de Active Directory después de haber quitado la asignación. Si piensa usar el objeto en el futuro, es posible que prefiera conservar el objeto de Active Directory.



## Para quitar la autenticación Kerberos de un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio en que se ejecuta Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
    ```
    Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
    ```
    ```
    Enable-CsTopology
    ```
    
    Por ejemplo:
    
    ```
    Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
    ```
    ```
    Enable-CsTopology
    ```
    
    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar o quitar una cuenta, deberá ejecutar <strong>Enable-CsTopology</strong> desde el símbolo del sistema del Shell de administración de Lync Server.
    

