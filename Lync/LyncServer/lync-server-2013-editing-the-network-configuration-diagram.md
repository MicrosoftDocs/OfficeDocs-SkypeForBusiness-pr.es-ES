---
title: 'Lync Server 2013: edición del diagrama de configuración de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc199098d27364c3bc5f512a48d2e512c7c9d984
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Editar el diagrama de configuración de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

La mayoría del trabajo que un diseñador hace en Lync Server 2013, la herramienta de planeación consiste en definir las entradas de las direcciones IP y los nombres de dominio completos (FQDN) de las entradas del diagrama de red. La información que se introduce en esta página se repite en los informes y otra información de la herramienta de planificación.

![Diagrama de red de la Herramienta de planeación](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagrama de red de la Herramienta de planeación")

La herramienta de planeación crea un diagrama de red con texto predeterminado para las direcciones IP y FQDN.

Para editar el diagrama de red y los valores de entrada:

1.  Elija una sección de la red en la cual comenzar a trabajar. Por ejemplo, haga doble clic en el texto, **access1.contoso.com**. En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real en lugar de 131.107.155.3.

2.  Haga clic en **Aceptar** para guardar las entradas.

3.  Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.

Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:

1.  Haga doble clic en los servidores front-end agrupados. Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.

2.  Por ejemplo, el valor de inicio para el primer servidor es fe0101.contoso.com y la dirección IP es 192.168.21.122.

3.  Escriba **fe0.contoso.com** en **FQDN de servidor front-end**, escriba **192.168.21.131** en **Dirección IP de servidor front-end** y, después haga clic en **Aceptar**.

4.  La característica de incremento automático actualiza todos los servidores del grupo a fe01 hasta fe06 y todas las direcciones IP desde 192.168.21.131 hasta 136.

Una vez completadas todas las modificaciones, guarde la topología. Para ello, siga los siguientes pasos:

Para guardar el diseño de la herramienta de planeación, haga clic en **archivo**y, a continuación, haga clic en **Guardar topología** o **Guardar topología como**. Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.

<div>

## <a name="see-also"></a>Vea también


[Edición del diseño en Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

