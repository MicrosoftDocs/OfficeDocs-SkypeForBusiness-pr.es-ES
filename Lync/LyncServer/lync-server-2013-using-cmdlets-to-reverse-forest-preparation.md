---
title: 'Lync Server 2013: Usar cmdlets para invertir la preparación del bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b893eb79cb19856572e90bd449b315f0ade803c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Usar cmdlets para invertir la preparación del bosque para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-19_

Use el cmdlet **Disable-CsAdForest** para invertir el paso de preparación del bosque.

<div>


> [!WARNING]  
> Si ejecuta el cmdlet <STRONG>Disable-CsAdForest</STRONG> en un entorno en el que también tiene una versión anterior de Lync Server implementada, también se eliminará la configuración global de la versión anterior.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Para usar cmdlets para invertir la preparación del bosque

1.  Inicie sesión en un equipo unido a un dominio como miembro del grupo administradores del dominio en el dominio raíz del bosque.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Por ejemplo:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    El parámetro Force especifica si se debe forzar la ejecución de la tarea. Si este parámetro no está presente, el comando no se ejecutará si aún hay un dominio del bosque preparado para Lync Server 2013. Si se especifica el parámetro Force, la acción continuará independientemente del estado de otros dominios del bosque.
    
    Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="see-also"></a>Vea también


[Ejecutar la preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

