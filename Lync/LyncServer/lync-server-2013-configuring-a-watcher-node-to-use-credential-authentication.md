---
title: 'Lync Server 2013: configuración de un nodo de monitor para usar la autenticación de credenciales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configuración de un nodo de monitor para usar la autenticación de credenciales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Si el equipo del nodo de observador se encuentra fuera de la red perimetral, debe seguir un procedimiento ligeramente diferente para configurar ese nodo de observador de forma que se ejecuten las transacciones sintéticas. En concreto, no debe crear un grupo de aplicaciones de confianza ni una aplicación de confianza, y debe instalar un certificado que permita al nodo de monitor enviar alertas a un equipo dentro de la red perimetral. Esto significa que tendrá que completar dos tareas independientes:

  - Actualizar la pertenencia al grupo administradores de RTC locales de solo lectura del equipo

  - Instalar los archivos de configuración del nodo de monitor

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Actualización de la pertenencia al grupo de administradores RTC local de solo lectura

Si el nodo de monitor se encuentra fuera de la red perimetral, debe agregar la cuenta de servicio de red al grupo de administradores RTC local de solo lectura en el equipo del nodo de supervisor. Para ello, complete el siguiente procedimiento en el nodo Watcher (monitor):

1.  Haga clic en **Inicio**, haga clic con el botón secundario en **equipo**y, a continuación, haga clic en **administrar**.

2.  En Administrador del servidor, expanda **configuración**, expanda **usuarios locales y grupos**y, a continuación, haga clic en **grupos**.

3.  En el panel grupos, haga doble clic en **RTC local-Only Administrators**.

4.  En el cuadro de diálogo **propiedades de administrador de solo lectura local de RTC** , haga clic en **Agregar**.

5.  En el cuadro de diálogo **Seleccionar usuarios, equipos, cuentas de servicio o grupos** , haga clic en **ubicaciones**.

6.  En el cuadro de diálogo **ubicaciones** , seleccione el nombre del equipo del nodo de monitor y, a continuación, haga clic en **Aceptar**.

7.  En el cuadro **Escriba los nombres de objeto que desea seleccionar** , escriba **servicio de red**y haga clic en **Aceptar**.

8.  En el cuadro de diálogo **propiedades de administradores locales de solo lectura** , haga clic en **Aceptar**y, a continuación, cierre el **Administrador del servidor**.

Reinicie el equipo del nodo de observador.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Instalar los archivos de configuración del nodo de monitor

Después de reiniciar el equipo del nodo de observador, el siguiente paso es ejecutar el archivo Watchernode. msi. Para ejecutar este archivo, abra el shell de administración de Lync Server 2013 haciendo clic en **Inicio**, haga clic en **todos los programas**, en **Lync Server 2013**y, por último, en el **Shell de administración de Lync Server**. En el shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione Entrar (Asegúrese de especificar la ruta de acceso real a su copia de Watchernode. msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Como se indicó anteriormente, Watchernode. msi también se puede ejecutar desde una ventana de comandos. Para abrir una ventana Comandos, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y, a continuación, haga clic en <STRONG>Ejecutar como administrador</STRONG>. Cuando se abra la ventana de comandos, escriba el mismo comando que se mostró anteriormente.



</div>

El modo Negotiate se usa en cualquier momento que el nodo de monitor no se puede configurar como un grupo de servidores de aplicaciones de confianza. En este modo, los administradores tendrán que administrar contraseñas de usuario de prueba en el nodo de monitor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

