---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e114d3f18e482c11a8e83c9d4308f3c5712932c
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Configurar la supervisión SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Después de migrar a Microsoft Lync Server 2013, debe completar algunas tareas para configurar Lync Server 2013 para que funcione con System Center Operations Manager.

  - Aplique actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de descubrimiento central.

  - Actualice la clave del registro del candidato de detección central.

  - Configure el servidor de administración principal de System Center Operations Manager para que invalide el nodo de detección central candidato.

A continuación se proporcionan instrucciones para llevar a cabo estas tareas.

**Aplique actualizaciones de Lync Server 2010 a un servidor elegido para administrar la lógica de descubrimiento central.**

1.  Elija un servidor que tenga instalados los archivos del agente System Center Operations Manager y esté configurado como un nodo de detección candidato.

2.  Aplique las actualizaciones de Lync Server 2010 a este servidor. Vea el tema sobre cómo [aplicar actualizaciones de Lync Server 2010](apply-lync-server-2010-updates.md).

**Actualice la clave del registro del candidato de detección central.**

1.  En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.

2.  En la línea de comandos, escriba:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Siempre que edite el registro, es posible que se produzca un error en el comando si la clave del registro ya existe. Si tiene esto, puede ignorar el error sin riesgos.

    
    </div>

**Configure su servidor de administración principal de System Center Operations Manager para invalidar el nodo de supervisor de detección central candidato.**

1.  En un equipo en el que se haya instalado la consola de System Center Operations Manager, expanda los **objetos del módulo de administración** y seleccione **descubrimientos de objetos**.

2.  Haga clic en **cambiar ámbito...**

3.  En la página **objetos del módulo de administración del ámbito** , seleccione candidato de detección de **LS**.

4.  Invalide el **valor efectivo candidato** a la detección de LS al nombre del servidor candidato elegido en el procedimiento anterior.

Por último, para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de raíz de System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

