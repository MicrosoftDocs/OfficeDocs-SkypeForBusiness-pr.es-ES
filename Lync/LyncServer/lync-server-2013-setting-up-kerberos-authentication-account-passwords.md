---
title: "Lync Server 2013: Configurar las contraseñas de cuenta de autenticación Kerberos"
TOCTitle: Configurar las contraseñas de cuenta de autenticación Kerberos
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48276408
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las contraseñas de cuenta de autenticación Kerberos en Lync Server 2013

 

_**Última modificación del tema:** 2010-11-03_

Una vez creado el objeto de equipo para la cuenta de autenticación Kerberos, puede configurar la contraseña para la cuenta. Debe ejecutar el cmdlet de Windows PowerShell para configurar la contraseña de la cuenta Kerberos en un servidor. Puede definir la contraseña en el objeto que ha creado para la autenticación Kerberos. La contraseña puede tener un valor conocido, pero de forma predeterminada es una contraseña aleatoria. La contraseña está disponible para todas las fuentes de autenticación Kerberos que usan la cuenta. Debe usar los cmdlets de Windows PowerShell para configurar y administrar las contraseñas de la cuenta Kerberos.


> [!NOTE]
> El objeto de la cuenta Kerberos es un objeto de equipo, pero usa el parámetro UserAccount para operaciones en los cmdlets de Windows PowerShell a los que se hace referencia. Tenga en cuenta que esto no es un error, sino el comportamiento previsto del cmdlet cuando se usa con la creación y el mantenimiento de la cuenta Kerberos.



## En esta sección

  - [Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS en Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

