---
title: 'Lync Server 2013: crear una cuenta de autenticación Kerberos'
description: 'Lync Server 2013: crear una cuenta de autenticación Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542136"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Crear una cuenta de autenticación Kerberos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-02_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio de forma mínima como miembro del grupo administradores del dominio.

Puede crear cuentas de autenticación Kerberos para cada uno de los sitios, o bien crear una sola cuenta de autenticación Kerberos y usarla para todos los sitios. Use los cmdlets de Windows PowerShell para crear y administrar las cuentas, incluida la identificación de las cuentas asignadas a cada sitio. El generador de topologías y el panel de control de Lync Server 2013 no muestran cuentas de autenticación Kerberos. Use el siguiente procedimiento para crear la(s) cuenta(s) de usuario que se usará(n) para la autenticación Kerberos.

<div>

## <a name="to-create-a-kerberos-account"></a>Para crear una cuenta Kerberos

1.  Como miembro del grupo administradores de dominio, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Desde la línea de comandos, ejecute el siguiente comando:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Por ejemplo:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Confirme que se ha creado el objeto Equipo al abrir el usuario y los equipos de Active Directory, expanda el contenedor **Usuarios** y, a continuación, confirme que el objeto Equipo de la cuenta de usuario se encuentra en el contenedor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

