---
title: 'Lync Server 2013: Herramientas de administración de Windows PowerShell y Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Herramientas de administración de Windows PowerShell y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-20_

En Microsoft Lync Server 2013, las herramientas de administración se implementan con Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos de productos y un lenguaje de scripting completo. Entre las herramientas de Lync Server 2013 que se implementan con Windows PowerShell se incluyen las siguientes:

  - **Generador de topología**. El generador de topología se usa para crear, ajustar y publicar su topología planeada, y valida su topología antes de empezar con las instalaciones del servidor. Al instalar Lync Server 2013 en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor tal como se indica en la topología. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.

  - **Shell de administración de Lync Server**. Puede usar el shell de administración de Lync Server para la administración de la línea de comandos completa de la implementación.

  - **Panel de control de Lync Server**. Puede usar la interfaz de usuario del panel de control de Microsoft Lync Server 2013 para administrar las tareas más comunes en su implementación.

Estas herramientas usan cmdlets de Windows PowerShell para administrar su implementación, incluidos los cmdlets específicos de 550 de producto. Los cmdlets de seguridad incluidos en Lync Server 2013 se usan principalmente para administrar la autenticación y los permisos y derechos de usuario. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN. Además, varios cmdlets permiten usar la nueva característica de control de acceso basado en roles (RBAC) para delegar el control administrativo de Lync Server 2013. Para obtener más información sobre los cmdlets de Lync Server, consulte [Shell de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md).

Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías antiguas, incluido Microsoft Visual Basic Scripting Edition (VBScript). Las características de seguridad de Windows PowerShell se han diseñado para crear un entorno en el que los usuarios no pueden ejecutar scripts de manera sencilla o sin problemas. De forma predeterminada, las características de seguridad de Windows PowerShell están habilitadas. Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una amplia variedad de objetivos de seguridad. Eso no significa que el shell impida a los usuarios ejecutar scripts. Lo que hace (de forma predeterminada) es que resulte difícil que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener más información, consulte Seguridad de scripts de Windows PowerShell en [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).

</div>

<span> </span>

</div>

</div>

</div>

