---
title: "Establecer una contraseña de cuenta de autenticación Kerberos en un servidor"
TOCTitle: Establecer una contraseña de cuenta de autenticación Kerberos en un servidor
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48276005
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013

 

_**Última modificación del tema:** 2012-01-16_

Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.

Debe configurar una contraseña en la cuenta de Kerberos por cada sitio que tenga servidores front-end, servidores Standard Edition y directores. Para establecer la contraseña, puede ejecutar el cmdlet **Set-CsKerberosAccountPassword** de  Windows PowerShell en un servidor del sitio (por ejemplo, Servidor front-end). Por cada sitio, debe ejecutar el cmdlet **Set-CsKerberosAccountPassword**. El cmdlet configura Servicios de Internet Information Server (IIS) para el servicio Servicios web y, a continuación, establece la contraseña en la cuenta de equipo de Servicios de dominio de Active Directory. Un método alternativo, basado en el parámetro que se usa con el cmdlet, configura IIS en un servidor mientras usa otro servidor que se ha configurado como el origen de la contraseña de la cuenta de Kerberos.

Cuando usa el cmdlet **Set-CsKerberosAccountPassword** para establecer una contraseña, Kerberos elige como contraseña una cadena generada al azar. Este cmdlet contacta con todas las instancias de IIS de todos los sitios centrales de Lync Server 2013 a los que está asignada esta cuenta.

## Para establecer una contraseña de una cuenta de autenticación de Kerberos

1.  Inicie sesión en cualquier equipo del dominio con Shell de administración de Lync Server instalado como un miembro del grupo RTCUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute los dos comandos siguientes:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Por ejemplo:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    

    > [!NOTE]
    > Debe especificar el parámetro UserAccount con el formato dominio\nombre de usuario. No se admite el formato Usuario@Dominio.extensión para hacer referencia a los objetos de equipo creados para la autenticación de Kerberos.

    
    > [!IMPORTANT]  
    > Después de realizar cambios en la autenticación Kerberos, como agregar o quitar una cuenta, deberá ejecutar <strong>Enable-CsTopology</strong> desde el símbolo del sistema del Shell de administración de Lync Server.
    

