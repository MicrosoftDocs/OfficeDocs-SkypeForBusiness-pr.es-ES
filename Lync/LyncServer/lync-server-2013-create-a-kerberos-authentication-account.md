---
title: 'Lync Server 2013: Crear una cuenta de autenticación Kerberos'
TOCTitle: Crear una cuenta de autenticación Kerberos
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48275470
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una cuenta de autenticación Kerberos en Lync Server 2013

 

_**Última modificación del tema:** 2012-01-02_

Para completar satisfatoriamente este procedimiento, deberá haber iniciado sesión en el servidor o en el dominio como miembro del grupo Admins. del dominio como mínimo.

Puede crear cuentas de autenticación Kerberos para cada uno de los sitios, o bien crear una sola cuenta de autenticación Kerberos y usarla para todos los sitios. Se usan cmdlets Windows PowerShell para crear y administrar las cuentas, incluida la identificación de las cuentas asignadas a cada uno de los sitios. Generador de topologías y Panel de control de Lync Server 2013 no muestran cuentas de autenticación Kerberos. Use el siguiente procedimiento para crear la(s) cuenta(s) de usuario que se usará(n) para la autenticación Kerberos.

## Para crear una cuenta Kerberos

1.  Como miembro del grupo Admins. del dominio, inicie sesión en un equipo del dominio que ejecuta Lync Server 2013 o en un equipo que tenga las herramientas administrativas instaladas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Desde la línea de comandos, ejecute el siguiente comando:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Por ejemplo:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Confirme que se ha creado el objeto Equipo al abrir el usuario y los equipos de Active Directory, expanda el contenedor **Usuarios** y, a continuación, confirme que el objeto Equipo de la cuenta de usuario se encuentra en el contenedor.

