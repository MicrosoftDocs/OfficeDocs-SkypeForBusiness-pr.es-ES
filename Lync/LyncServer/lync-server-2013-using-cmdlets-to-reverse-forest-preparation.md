---
title: 'Lync Server 2013: usar cmdlets para invertir la preparación del bosque'
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
ms.openlocfilehash: 2e3104f07934e590dc22ac9f5000601bc8166b6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535797"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Uso de cmdlets para invertir la preparación del bosque para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-19_

Use el cmdlet **Disable-CsAdForest** para invertir el paso de preparación del bosque.

<div>


> [!WARNING]  
> Si ejecuta el cmdlet <STRONG>Disable-CsAdForest</STRONG> en un entorno en el que también tiene instalada una versión anterior de Lync Server, también se eliminará la configuración global de la versión anterior.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Para usar los cmdlets para invertir la preparación del bosque

1.  Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo Admins. del dominio en el dominio raíz del bosque.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Por ejemplo:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    El parámetro Force especifica si se debe forzar la ejecución de la tarea. Si este parámetro no está presente, el comando no se ejecutará si aún hay un dominio del bosque preparado para Lync Server 2013. Si se especifica el parámetro Force, la acción continuará sea cual sea el estado de otros dominios del bosque.
    
    Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Ejecutar la preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Preparar el bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

