---
title: 'Lync Server 2013: habilitar la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f11aab3c58a43ac0746cb1f297bf4f3f85d28c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Habilitar la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Aunque los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada servidor front-end, eso no significa que comience a recopilar datos de supervisión de forma automática en el momento de finalizar la instalación de Microsoft Lync Server 2013. En su lugar, debe hacer dos cosas: debe asociar los servidores front-end o las agrupaciones front-end con una base de datos de supervisión, y debe habilitar la supervisión de la grabación de detalles de llamadas (CDR) o la calidad de la experiencia (QoE) en el ámbito global o en el ámbito del sitio.

Para obtener instrucciones paso a paso sobre la Asociación de servidores front-end o grupos de aplicaciones para el usuario con una base de datos de supervisión, consulte el tema sobre cómo [asociar una tienda de supervisión con un grupo de servidores front-end en Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) en la guía de implementación. Después de que se hayan realizado estas asociaciones y después de que se haya publicado la nueva topología de Lync Server, aún no podrá recopilar datos de supervisión. Esto se debe a que, de forma predeterminada, la recopilación de datos de CDR y QoE está deshabilitada al instalar Lync Server 2013.

Para comenzar la recopilación de datos, deberá habilitar la supervisión de CDR y/o QoE. (Tenga en cuenta que no tiene que habilitar la supervisión de CDR y QoE; si lo prefiere, puede habilitar un tipo de supervisión y dejar el otro tipo deshabilitado). Para habilitar la supervisión de CDR en el ámbito global, ejecute el siguiente comando desde el shell de administración de Lync Server:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Como alternativa, puede habilitar la supervisión de CDR desde el panel de control de Lync Server 2013. En el panel de control de Lync Server, complete el procedimiento siguiente:

1.  Haga clic en **Supervisión**.

2.  En la pestaña **Registro detallado de llamadas**, haga doble clic en la configuración **Global**.

3.  En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de CDR** y haga clic en **Confirmar**.

Para habilitar la supervisión de QoE en el ámbito global, ejecute este comando desde el shell de administración de Lync Server:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Si lo prefiere, también puede habilitar la supervisión de QoE desde el panel de control de Lync Server. Desde allí, lleve a cabo el procedimiento siguiente:

1.  Haga clic en **Supervisión**.

2.  En la pestaña **Datos de calidad de la experiencia**, haga doble clic en la configuración **Global**.

3.  En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de QoE** y haga clic en **Confirmar**.

Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de CDR y QoE en toda la organización. De forma alternativa, puede separar las opciones de configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio. Por ejemplo, puede habilitar la supervisión de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín. Para obtener más información sobre cómo administrar las opciones de configuración de supervisión, consulte el tema de la guía de implementación configuración de la [grabación de detalles de llamadas y configuración de la calidad de la experiencia en Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

