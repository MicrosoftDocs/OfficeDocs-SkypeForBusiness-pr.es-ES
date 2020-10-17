---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de0ca4d569c8a67eb134c5a1bd018ed143041046
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503367"
---
# <a name="configure-scom-monitoring"></a>Configurar la supervisión SCOM

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Después de migrar a Microsoft Lync Server 2013, debe realizar algunas tareas para configurar Lync Server 2013 para que funcione con System Center Operations Manager.

  - Aplique las actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de detección central.

  - Actualice la clave de registro del servidor candidato de detección central.

  - Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de detección central candidato.

A continuación se proporcionan instrucciones para realizar cada una de estas tareas.

**Aplique las actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de detección central.**

1.  Elija un servidor que tenga los archivos del agente System Center Operations Manager instalados y esté configurado como un nodo de detección candidato.

2.  Aplique las actualizaciones de Lync Server 2010 a este servidor. Consulte el tema [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).

**Actualice la clave de registro del servidor candidato de detección central.**

1.  En el servidor decidió administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.

2.  En la línea de comandos, escriba lo siguiente:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Al cambiar el registro, puede recibir un error que indica que el comando ha fallado si la clave de registro ya existe. Si le pasa esto, puede ignorar el error de forma segura.

    
    </div>

**Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de monitor de detección central candidato.**

1.  En un PC donde se haya instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y luego seleccione **Detecciones de objetos**.

2.  Haga clic en **Cambiar ámbito...**

3.  En la página **Objetos de módulo de administración de ámbito**, seleccione **Candidato de detección de LS**.

4.  Reemplace el **Valor efectivo de Candidato de detección de LS** con el nombre del servidor candidato elegido en el procedimiento anterior.

Por último, para finalizar los cambios, reinicie el servicio de estado en el Servidor de administración raíz de System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

