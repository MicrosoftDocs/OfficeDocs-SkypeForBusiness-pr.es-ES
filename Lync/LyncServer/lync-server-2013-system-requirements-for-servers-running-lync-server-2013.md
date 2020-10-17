---
title: 'Lync Server 2013: requisitos del sistema para servidores que ejecutan Lync Server 2013'
description: 'Lync Server 2013: requisitos del sistema para servidores que ejecutan Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562656"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Requisitos del sistema para servidores que ejecutan Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-24_

<div>


> [!NOTE]
> Para obtener más información sobre los requisitos de hardware, vea <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync Server 2013</A>.



</div>

Los servidores Standard Edition y Enterprise Edition comparten los mismos requisitos de software.

Los servidores que ejecutan Lync Server 2013, Enterprise Edition están pensados para grandes organizaciones como la implementación principal de la organización. El servidor Enterprise Edition se ha diseñado para alcanzar una escala de, aproximadamente, 80.000 usuarios hospedados en cada grupo de servidores. Los servidores que ejecutan Lync Server 2013, Standard Edition están pensados para organizaciones más pequeñas y ubicaciones remotas desde la implementación principal de la organización. Un par de servidores Standard Edition puede admitir hasta 5.000 usuarios. Para obtener más información sobre las diferencias entre los servidores Standard Edition y los servidores Enterprise Edition, consulte [información general sobre la implementación de Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Instalación del sistema operativo

<div>


> [!IMPORTANT]
> Lync Server 2013 solo está disponible en una edición de 64 bits, que requiere hardware de 64 bits y una edición de 64 bits del sistema operativo Windows Server. Una edición de 32 bits de Lync Server 2013 no está disponible en esta versión.



</div>

El servidor Standard Edition y Enterprise Edition puede usar cualquiera de las siguientes opciones:

  - Windows Server 2008 R2 SP1 o el último Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

Instale el software del sistema operativo en el servidor Standard Edition o el servidor front-end Enterprise Edition. Aplique todas las actualizaciones para dotar al sistema operativo de la versión más reciente y del nivel de actualización necesario que sea coherente con los estándares de su organización. Para obtener más información sobre los requisitos operativos, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

> [!NOTE] 
> La actualización local del sistema operativo no es compatible con Lync Server 2013.  Debe implementar un grupo independiente y migrar los usuarios al nuevo grupo con un sistema operativo diferente.

<div>


> [!NOTE]
> Para que Lync Server 2013 funcione en Windows Server 2012 R2, es posible que deba cambiar el valor de una clave del registro en Windows Server. Este cambio puede ser necesario para que los certificados funcionen correctamente y para que los clientes se registren con aplicaciones de sucursal con funciones de supervivencia. Para obtener más información, consulte <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Software adicional para Lync Server 2013

Además de las actualizaciones necesarias para el sistema operativo, Lync Server 2013 requiere funciones del sistema operativo, características y software para funcionar. Para obtener información detallada sobre el software adicional que debe instalarse antes de publicar la topología e instalar Lync Server 2013, consulte [Additional software Requirements for Lync server 2013](lync-server-2013-additional-software-requirements.md) en la documentación de planeación.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Software adicional necesario para todos los roles de servidor

En todos los roles de servidor, también debe asegurarse de que la interfaz de línea de comandos de Windows PowerShell 3,0 y Microsoft .NET Framework 4,5 estén instalados.

Además, se requiere la interfaz de línea de comandos 3,0 de Windows PowerShell y Microsoft .NET Framework 4,5 en cualquier equipo en el que vaya a ejecutar las herramientas administrativas de Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 requiere la instalación de Windows PowerShell 3,0 en cada equipo que vaya a formar parte de la topología de Lync Server. Para más detalles sobre la instalación de Windows PowerShell 3,0, vea [Installing Windows powershell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]
> En Windows Server &nbsp; 2008 &nbsp; R2 con SP1, la interfaz de línea de comandos de windows PowerShell 3,0 no se puede instalar antes de instalar Microsoft .net Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Al instalar Microsoft .NET Framework 4,5 en servidores que ejecutarán Lync Server 2013 en Windows Server 2012 o Windows Server 2012 R2, debe realizar un paso adicional. Una vez instalado .NET Framework 4,5, use el administrador del servidor para instalar la activación HTTP.

**Para instalar la activación HTTP de .NET 4,5 en Windows Server 2012 o Windows Server 2012 R2**

1.  En el menú **Inicio** , haga clic en **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de servidores**.

2.  En Administrador del servidor, en **Resumen de características**, elija **Agregar características**.

3.  Expanda **.NET Framework 4,5**.

4.  Seleccione **activación de WCF** si aún no está seleccionada. A continuación, seleccione **activación http**.

5.  Haga clic en **siguiente** y siga las instrucciones para finalizar la instalación.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

