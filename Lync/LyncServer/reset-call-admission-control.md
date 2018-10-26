---
title: Restablecer el control de admisión de llamadas
TOCTitle: Restablecer el control de admisión de llamadas
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49889194
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restablecer el control de admisión de llamadas

 

_**Última modificación del tema:** 2012-10-11_

Si un Lync Server 2010Grupo de servidores front-end hospeda el control de admisión de llamadas (CAC), debe mover el alojamiento de CAC a un grupo de Lync Server 2013 antes de poder quitar el Lync Server 2010Grupo de servidores front-end.

## Para restablecer el CAC

1.  Abra Generador de topologías.

2.  Haga clic con el botón secundario en el nodo del sitio y luego haga clic en **Editar propiedades**.

3.  En el parámetro **Control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** esté activado.

4.  En **Grupo de servidores front-end para ejecutar el control de admisión de llamadas (CAC)**, seleccione el grupo de Lync Server 2013 que va a hospedar el CAC y luego haga clic en **Aceptar**.

5.  Publique la topología.

