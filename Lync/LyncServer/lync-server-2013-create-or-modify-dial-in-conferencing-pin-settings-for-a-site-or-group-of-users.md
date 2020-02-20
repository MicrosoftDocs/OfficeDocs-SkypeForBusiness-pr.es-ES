---
title: 'Lync Server 2013: crear o modificar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b65d62514cabe64381fc002e4c7242c9a782acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a>Crear o modificar la configuración de PIN de conferencia de acceso telefónico local en Lync Server 2013 para un sitio o grupo de usuarios

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Siga los pasos a continuación para crear o modificar una directiva de número de identificación personal (PIN) de conferencias de acceso telefónico local a nivel de usuario o a nivel de sitio. Para más información sobre cómo cambiar la Directiva de PIN global, vea [modificar la configuración del PIN de conferencias de acceso telefónico local predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>Para crear una directiva de PIN de usuario o sitio

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, haga clic en **Nueva** y, a continuación, siga uno de los procedimientos siguientes:
    
      - Para crear una directiva de nivel de usuario, haga clic en **Directiva de usuario**. En **Nueva directiva de PIN**, en **Nombre**, escriba un nombre descriptivo para la directiva.
    
      - Para crear una directiva de nivel de sitio, haga clic en **Directiva de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba todo o parte del nombre del sitio para el que desea crear una directiva. En la lista de sitios, haga clic en el sitio que desee y, a continuación, en **Aceptar**.

5.  En el campo **Descripción**, escriba una descripción de la directiva de PIN.

6.  En el campo **Longitud mínima de PIN**, escriba o seleccione la longitud mínima de PIN que se va a admitir. La longitud mínima predeterminada es de cinco dígitos.

7.  Para poder especificar un número máximo de intentos de inicio de sesión antes de que un usuario quede bloqueado, active la casilla **Especificar máximo de intentos de inicio de sesión**. Si no selecciona esta opción, el número máximo de intentos permitidos queda determinado automáticamente en función de la longitud del PIN. De forma predeterminada, el número máximo de intentos se determina automáticamente.

8.  Si activa la casilla **Especificar máximo de intentos de inicio de sesión** en **Máximo de intentos de inicio de sesión**, escriba o seleccione un número máximo de intentos de inicio de sesión que quiera permitir.

9.  Para que los PIN tengan vencimiento, active la casilla **Habilitar expiración de PIN**. Si no selecciona esta opción, los PIN nunca expirarán. De forma predeterminada, los PIN nunca expiran.

10. Si activa la casilla **Habilitar expiración de PIN**, en **el PIN expira después de (días)**; escriba o seleccione el número de días después de los cuales expira el PIN.

11. En **Recuento de historial de PIN**, escriba el número de PIN que debe crear un usuario antes de que pueda volver a usar el PIN. De forma predeterminada, los usuarios pueden volver a usar sus PIN.

12. Para permitir patrones comunes de dígitos en los PIN como, por ejemplo, números secuenciales y conjuntos repetitivos de números, active la casilla de verificación **Permitir patrones comunes**. Si no selecciona esta opción, solamente se permitirán patrones complejos de dígitos. De forma predeterminada, solo se permiten patrones complejos de dígitos.
    
    <div>
    

    > [!IMPORTANT]
    > Se recomienda no permitir patrones comunes.

    
    </div>

13. Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a>Para modificar una directiva de PIN de usuario o sitio nueva

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **Directiva de PIN**.

4.  En la página **Directiva de PIN**, haga clic en la directiva de PIN que desee modificar, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar directiva de PIN**, modifique cualquier configuración de directivas (salvo el nombre de la directiva, que no se puede modificar).

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

