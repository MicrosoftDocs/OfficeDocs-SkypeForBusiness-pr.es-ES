---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c51eed6e5164316c2785ff5d560291afe58015c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>Restablecer el control de admisión de llamadas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

Si un grupo de servidores front-end 2010 de Lync Server hospeda el controlador de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Lync Server 2013 para poder quitar el grupo de servidores front-end de Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Para restablecer el CAC

1.  Abra el Generador de topologías.

2.  Haga clic con el botón secundario en el nodo del sitio y luego haga clic en **Editar propiedades**.

3.  En el parámetro **Control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** esté activado.

4.  En **grupo de servidores front-end para ejecutar el control de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Lync Server 2013 que va a hospedar CAC y, a continuación, haga clic en **Aceptar**.

5.  Publique la topología.

</div>

</div>

<span> </span>

</div>

</div>

</div>

