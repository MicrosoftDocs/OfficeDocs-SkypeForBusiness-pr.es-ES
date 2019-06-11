---
title: 'Lync Server 2013: Crear una cuenta de autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Crear una cuenta de autenticación Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-01-02_

Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio.

Puede crear cuentas de autenticación Kerberos para cada sitio o puede crear una sola cuenta de autenticación Kerberos y usarla para todos los sitios. Use los cmdlets de Windows PowerShell para crear y administrar las cuentas, incluida la identificación de las cuentas asignadas a cada sitio. El generador de topología y el panel de control de Lync Server 2013 no muestran cuentas de autenticación Kerberos. Use el procedimiento siguiente para crear una o más cuentas de usuario para usarlas en la autenticación Kerberos.

<div>

## <a name="to-create-a-kerberos-account"></a>Para crear una cuenta de Kerberos

1.  Como miembro del grupo administradores de dominio, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute el siguiente comando:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Por ejemplo:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Confirme que el objeto de equipo se creó al abrir usuarios y equipos de Active Directory, expanda el contenedor **usuarios** y, a continuación, confirme que el objeto de equipo de la cuenta de usuario se encuentra en el contenedor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

