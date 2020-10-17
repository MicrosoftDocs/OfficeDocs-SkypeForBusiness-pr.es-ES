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
ms.openlocfilehash: e0b637ea06d0255d53f73eef0385c3e929045071
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528537"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a>Habilitación de la supervisión en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Aunque los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada servidor front-end, esto no significa que inicie automáticamente la recopilación de datos de supervisión en el momento de finalizar la instalación de Microsoft Lync Server 2013. En su lugar, deberá llevar a cabo dos tareas: debe asociar los servidores front-end/grupos de servidores front-end a una base de datos de supervisión y debe habilitar la supervisión del registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE) en ámbito global o del sitio.

Para obtener instrucciones paso a paso sobre la Asociación de servidores front-end o grupos de servidores front-end con una base de datos de supervisión, consulte el tema sobre cómo [asociar un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) en la guía de implementación. Una vez realizadas estas asociaciones, y tras publicar la nueva topología de Lync Server, seguirá sin poder recopilar datos de supervisión. Esto se debe a que, de forma predeterminada, la recopilación de datos de CDR y QoE está deshabilitada al instalar Lync Server 2013.

Para comenzar la recopilación de datos, deberá habilitar la supervisión de CDR o QoE. (Tenga en cuenta que no tiene que habilitar la supervisión de CDR y QoE; si lo prefiere, puede habilitar un tipo de supervisión y dejar el otro tipo deshabilitado). Para habilitar la supervisión de CDR en el ámbito global, ejecute el siguiente comando desde el shell de administración de Lync Server:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Como alternativa, puede habilitar la supervisión de CDR desde el panel de control de Lync Server 2013. Desde el panel de control de Lync Server, realice el procedimiento siguiente:

1.  Haga clic en **Supervisión**.

2.  En la pestaña **Registro detallado de llamadas**, haga doble clic en **Global**.

3.  En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de registros detallados de llamadas (CDR)** y haga clic en **Confirmar**.

Para habilitar la supervisión de QoE en el ámbito global, ejecute este comando desde el shell de administración de Lync Server:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Si lo prefiere, también puede habilitar la supervisión de QoE desde el panel de control de Lync Server. Desde el Panel de control, lleve a cabo el procedimiento siguiente:

1.  Haga clic en **Supervisión**.

2.  En la pestaña **Datos de calidad de la experiencia**, haga doble clic en **Global**.

3.  En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** y haga clic en **Confirmar**.

Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de datos de CDR y QoE en la organización. De forma alternativa, puede separar la configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio. Por ejemplo, puede habilitar la supervisión de datos de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín. Para obtener más información sobre cómo administrar las opciones de configuración de la supervisión, consulte el tema guía de implementación configuración del [registro de detalles de llamadas y la calidad de la experiencia en Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

