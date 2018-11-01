---
title: Habilitación de la supervisión en Lync Server 2013
TOCTitle: Habilitación de la supervisión en Lync Server 2013
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49888923
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación de la supervisión en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-17_

Aunque los agentes de recopilación de datos unificados se instalan y activan automáticamente en cada servidor front-end, ello no implica que pueda comenzar a recopilar datos de supervisión inmediatamente después de que finalice la instalación de Microsoft Lync Server 2013. En su lugar, deberá llevar a cabo dos tareas: debe asociar los servidores front-end/grupos de servidores front-end a una base de datos de supervisión y debe habilitar la supervisión del registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE) en ámbito global o del sitio.

Para obtener instrucciones paso a paso sobre la asociación de servidores o grupos de servidores front-end a una base de datos de supervisión, vea el tema [Asociación de un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) en la guía de implementación. Una vez realizadas estas asociaciones, y tras publicar la nueva topología de Lync Server, seguirá sin poder recopilar datos de supervisión. Esto se debe a que la recopilación de datos de CDR y QoE no se habilita con la instalación de Lync Server 2013.

Para iniciar la recopilación de datos, deberá habilitar la supervisión de datos CDR o QoE. (Tenga en cuenta que no necesita habilitar la supervisión de datos de CDR y QoE. Si lo prefiere, puede habilitar un tipo de supervisión y dejar la otra supervisión deshabilitada.) Para habilitar la supervisión de datos CDR de forma global, ejecute el comando siguiente desde el Shell de administración de Lync Server:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

De forma alternativa, puede habilitar la supervisión de datos de CDR desde el Panel de control de Lync Server 2013. Desde el Panel de control de Lync Server, lleve a cabo el procedimiento siguiente:

1.  Haga clic en **Supervisión**.

2.  En la pestaña **Registro detallado de llamadas**, haga doble clic en **Global**.

3.  En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de registros detallados de llamadas (CDR)** y haga clic en **Confirmar**.

Para habilitar la supervisión de QoE de forma global, ejecute este comando desde el Shell de administración de Lync Server:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Si lo prefiere, también puede habilitar la supervisión de QoE desde el Panel de control de Lync Server. Desde el Panel de control, lleve a cabo el procedimiento siguiente:

1.  Haga clic en **Supervisión**.

2.  En la pestaña **Datos de calidad de la experiencia**, haga doble clic en **Global**.

3.  En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de calidad de la experiencia (QoE)** y haga clic en **Confirmar**.

Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de datos de CDR y QoE en la organización. De forma alternativa, puede separar la configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio. Por ejemplo, puede habilitar la supervisión de datos de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín. Para obtener más información sobre la administración de la configuración de supervisión, consulte el tema [Configuración de la grabación de detalles de llamada y la calidad de la experiencia en Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md) de la guía de implementación.

