---
title: 'Lync Server 2013: modificar una directiva de PIN existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d2a3d259ee5f45241063764cfd905cbd0f0854
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a>Modificar una directiva de PIN existente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-19_

Puede usar la pestaña **Directiva de PIN** para proporcionar autenticación de número de identificación personal (PIN) a los usuarios que se conectan a Lync 2013 con teléfonos IP. Para utilizar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web. Para obtener más información, vea modificar la configuración [de un servicio web existente en Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio.

<div>

## <a name="to-modify-an-existing-pin-policy"></a>Para modificar una directiva de PIN existente

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar directiva de PIN**, en **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que desea permitir. La longitud mínima predeterminada es de cinco dígitos.

6.  Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla   **Especificar número máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.

7.  Si ha seleccionado la casilla **Especificar número máximo de intentos de inicio de sesión**, en **Número máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.

8.  Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.

9.  Si activa la casilla **Habilitar expiración de PIN**, en **El PIN expira tras (días)**, escriba o seleccione el número de días después de los cuales expira el PIN.

10. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.

11. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    <div>
    

    > [!IMPORTANT]  
    > Se recomienda no permitir patrones comunes.

    
    </div>

12. Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

