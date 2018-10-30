---
title: "Lync Server 2013: Sincronizar contraseña de cuenta de autenticación Kerberos con IIS"
TOCTitle: Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48274302
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS en Lync Server 2013

 

_**Última modificación del tema:** 2010-11-08_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

En un sitio, los servidores front-end, los servidores Standard Edition y los directores pueden usar una cuenta de autenticación Kerberos con el fin de autenticar solicitudes al servicio de Servicios web. Este procedimiento ubica cada uno de los servidores que ejecutan Servicios web en un sitio asignado a una cuenta Kerberos y actualiza las opciones de configuración de Servicios de Internet Information Server (IIS) para usar la cuenta Kerberos. Para obtener más información, consulte [Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

## Para establecer y configurar una contraseña de cuenta de autenticación Kerberos

1.  Inicie sesión en un equipo de origen (como, por ejemplo, fe01.contoso.com) como miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Desde la línea de comandos del Shell de administración de Lync Server, ejecute los dos comandos siguientes:
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Por ejemplo:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    > [!IMPORTANT]  
    > El nombre del equipo de origen y del equipo de destino deben ser un nombre de dominio completo (FQDN) del servidor. No puede usar el FQDN del grupo de servidores a menos que el nombre del mismo sea igual que el nombre del equipo que está usando como equipo de origen o equipo de destino.
    
    
    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar o quitar una cuenta, deberá ejecutar <strong>Enable-CsTopology</strong> desde el símbolo del sistema del Shell de administración de Lync Server.
    

