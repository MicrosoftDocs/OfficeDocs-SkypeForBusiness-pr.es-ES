---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

Si un grupo de aplicaciones para el usuario de Lync Server 2010 hospeda control de admisión de llamadas (CAC), debe mover el alojamiento de hospedaje de CAC a un grupo de servidores de Lync 2013 antes de poder quitar el grupo de aplicaciones para usuario de Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Para restablecer CAC

1.  Abra el generador de topologías.

2.  Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.

3.  En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado.

4.  En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de 2013 de Lync Server que hospedará CAC y, a continuación, haga clic en **Aceptar**.

5.  Publique la topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

