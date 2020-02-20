---
title: 'Lync Server 2013: configuración de contraseñas de cuentas de autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bef30a82479c876dbb4b4e6e6e9b55b3c2b37dc3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Configuración de contraseñas de cuentas de autenticación Kerberos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2010-11-03_

Una vez creado el objeto de equipo para la cuenta de autenticación Kerberos, puede configurar la contraseña para la cuenta. Ejecute el cmdlet de Windows PowerShell para establecer la contraseña de la cuenta Kerberos en un servidor. Puede definir la contraseña en el objeto que ha creado para la autenticación Kerberos. La contraseña puede tener un valor conocido, pero de forma predeterminada es una contraseña aleatoria. La contraseña está disponible para todas las fuentes de autenticación Kerberos que usan la cuenta. Use los cmdlets de Windows PowerShell para configurar y administrar las contraseñas de las cuentas Kerberos.

<div>


> [!NOTE]  
> El objeto de cuenta Kerberos es un objeto de equipo, pero usa el parámetro Cuentadeusuario para las operaciones en los cmdlets de Windows PowerShell a los que se hace referencia. Tenga en cuenta que esto no es un error, sino el comportamiento previsto del cmdlet cuando se usa con la creación y el mantenimiento de la cuenta Kerberos.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Sincronizar una contraseña de cuenta de autenticación Kerberos con IIS en Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

