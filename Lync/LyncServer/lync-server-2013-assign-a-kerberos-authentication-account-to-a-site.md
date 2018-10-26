---
title: "Lync Server 2013 : Attribution d’un compte d’auth. Kerberos sur un site"
TOCTitle: Asignar una cuenta de autenticación Kerberos a un sitio
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48275052
ms.date: 04/19/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013

 

_**Última modificación del tema:** 2017-04-18_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Después de crear la cuenta Kerberos, debe asignarla a un sitio. Se trata de un sitio de Lync Server 2013, no un sitio de Active Directory. Puede crear varias cuentas de autenticación Kerberos por implementación, pero solo puede asignar una sola cuenta un sitio. Use el siguiente procedimiento para asignar una cuenta de autenticación Kerberos creada con anterioridad a un sitio. Para obtener más información sobre la creación de la cuenta Kerberos, consulte [Crear una cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

## Para asignar cuenta de autenticación Kerberos a un sitio

1.  Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio en que se ejecuta Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
    ```
    New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount" -Identity "site:SiteName"
    ```
    ```
    Enable-CsTopology
    ```

    Por ejemplo:
    
    ```
    New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth" -Identity "site:redmond"
    ```
    ```
    Enable-CsTopology
    ```

    > [!NOTE]
    > Debe especificar el parámetro UserAccount con el formato dominio\nombre de usuario. No se admite el formato User@Domain.extension para hacer referencia a los objetos de equipo creados con fines de autenticación Kerberos.

    
    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar o quitar una cuenta, deberá ejecutar <strong>Enable-CsTopology</strong> desde el símbolo del sistema del Shell de administración de Lync Server.
    

