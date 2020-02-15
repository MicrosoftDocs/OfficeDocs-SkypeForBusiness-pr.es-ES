---
title: 'Lync Server 2013: herramientas de administración de Windows PowerShell y Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e475cd9249030ec09ad3261e84e068d9db0e8c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Herramientas de administración de Windows PowerShell y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-20_

En Microsoft Lync Server 2013, las herramientas de administración se implementan con Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Entre las herramientas de Lync Server 2013 que se implementan con Windows PowerShell se incluyen las siguientes:

  - **Generador de topologías**. Puede usar el generador de topologías para crear, ajustar y publicar la topología planeada, así como validar la topología antes de comenzar con las instalaciones del servidor. Al instalar Lync Server 2013 en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor tal como se indicó en la topología. Después de la instalación, la información de configuración se replica automáticamente en todos los servidores. Los componentes se pueden agregar a la implementación solo mediante el generador de topologías.

  - **Shell de administración de Lync Server**. Puede usar el shell de administración de Lync Server para la administración de la línea de comandos completa de la implementación.

  - **Panel de control de Lync Server**. Puede usar la interfaz de usuario del panel de control de Microsoft Lync Server 2013 para administrar las tareas más comunes en su implementación.

Estas herramientas usan los cmdlets de Windows PowerShell para la administración de la implementación, incluidos los cmdlets cercanos a 550 específicos del producto. Los cmdlets de seguridad incluidos en Lync Server 2013 se usan principalmente para administrar la autenticación y los permisos y derechos de usuario. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, una serie de cmdlets le permiten usar la nueva característica de control de acceso basado en roles (RBAC) para delegar el control administrativo de Lync Server 2013. Para obtener más información sobre los cmdlets de Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con las secuencias de comandos de tecnologías anteriores, como Microsoft Visual Basic Scripting Edition (VBScript). Las características de seguridad de Windows PowerShell están pensadas para crear un entorno en el que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. De forma predeterminada, las características de seguridad de Windows PowerShell están habilitadas. Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una variedad de objetivos de seguridad. Esto no quiere decir que el shell impida a los usuarios ejecutar scripts. En su lugar, el shell dificulta (de forma predeterminada) que los usuarios ejecuten scripts sin darse cuenta de que lo hacen. Para obtener más información, consulte Seguridad de scripts de Windows PowerShell en [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).

</div>

<span> </span>

</div>

</div>

</div>

