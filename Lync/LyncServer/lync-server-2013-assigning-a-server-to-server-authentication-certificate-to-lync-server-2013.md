---
title: Asignación de un certificado de autenticación de servidor a servidor a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Asignación de un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-24_

Para determinar si un certificado de autenticación de servidor a servidor ya se ha asignado a Microsoft Lync Server 2013, ejecute el siguiente comando desde el shell de administración de Lync Server 2013:

    Get-CsCertificate -Type OAuthTokenIssuer

Si no recibe información del certificado, necesita asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor. Como regla general, cualquier certificado de Lync Server 2013 se puede usar como certificado de OAuthTokenIssuer; por ejemplo, su certificado predeterminado de Lync Server 2013 también se puede usar como el certificado OAuthTokenIssuer. (El certificado OAUthTokenIssuer también puede ser cualquier certificado de servidor Web que incluya el nombre de su dominio SIP en el campo asunto). Los dos requisitos principales para el certificado que se usa para la autenticación de servidor a servidor son los siguientes: 1) el mismo certificado se debe configurar como el certificado de OAuthTokenIssuer en todos los servidores front-end; y 2) el certificado debe tener al menos 2048 bits.

Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Una vez que haya solicitado y obtenido el nuevo certificado, puede iniciar sesión en cualquiera de los servidores front-end y usar un comando de Windows PowerShell similar al siguiente para importar y asignar ese certificado:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado. Este procedimiento debe ejecutarse una sola vez: el servicio de replicación de Lync Server creará automáticamente un conjunto de tareas programadas que descifrarán e implementarán el certificado en todos los servidores front-end.

Como alternativa, puede usar un certificado existente como certificado de autenticación de servidor a servidor. (Como se indica, el certificado predeterminado puede usarse como certificado de autenticación de servidor a servidor). El siguiente par de comandos de Windows PowerShell recupera el valor de la propiedad Thumbprint del certificado predeterminado y luego usa ese valor para convertir el certificado predeterminado en el certificado de autenticación de servidor a servidor:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

En el comando anterior, el certificado recuperado está configurado para funcionar como certificado de autenticación de servidor a servidor global; eso significa que el certificado será replicado y usado por todos los servidores front-end. De nuevo, este comando solo se debe ejecutar una vez y solo en uno de los servidores front-end. Aunque todos los servidores front-end deben usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor front-end. En su lugar, configure el certificado una vez y deje que el servidor de replicación de Lync Server tenga cuidado al copiar ese certificado en cada servidor.

El cmdlet Set-CsCertificate toma el certificado en cuestión y lo configura inmediatamente para que actúe como el certificado de OAuthTokenIssuer actual. (Lync Server 2013 conserva dos copias de un tipo de certificado: el certificado actual y el certificado anterior). Si necesita que el nuevo certificado empiece a funcionar inmediatamente como el certificado OAuthTokenIssuer, debe usar el cmdlet Set-CsCertificate.

También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado. "Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado. Por ejemplo, este comando recupera el certificado predeterminado y, después, configura ese certificado para que tome el control como el certificado de OAuthTokenIssuer actual a partir del 1 de julio de 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

El 1 de julio de 2012 el nuevo certificado se configurará como el certificado de OAuthTokenIssuer actual y el certificado de OAuthTokenIssuer "antiguo" se configurará como el certificado anterior.

Si no desea usar Windows PowerShell, también puede usar la consola MMC certificados para exportar un certificado de un servidor front-end y, a continuación, importar ese mismo certificado en todos los demás servidores front-end. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.

<div>


> [!WARNING]
> En este caso, el procedimiento debe realizarse en cada servidor front-end. Al exportar e importar certificados de esta forma, Lync Server 2013 no replicará ese certificado en cada servidor front-end.



</div>

Una vez que el certificado se ha importado a todos los servidores front-end, ese certificado se puede asignar mediante el Asistente para la implementación de Lync Server en lugar de Windows PowerShell. Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:

1.  Haga clic en Inicio, seleccione todos los programas, **Microsoft Lync server 2013**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.

2.  En el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.

3.  En la página Microsoft Lync Server 2013, haga clic en el botón **Ejecutar** bajo el título **paso 3: solicitar, instalar o asignar certificados**. Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.

4.  En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.

5.  En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.

6.  En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.

7.  En la página Resumen de asignación de certificados, haga clic en **Siguiente**.

8.  En la página Ejecutar comandos, haga clic en **Finalizar**.

9.  Cierre el Asistente para certificados y el Asistente para la implementación.

</div>

<span> </span>

</div>

</div>

</div>

