---
title: 'Lync Server 2013: Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Si un grupo de servidores perimetrales deja de funcionar pero el grupo de servidores front-end en el mismo sitio aún se está ejecutando, tendrá que configurar el grupo de servidores front-end para que use un grupo de límites en un sitio diferente hasta que se restaure el grupo perimetral con error.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Cambiar el grupo perimetral asociado a un grupo de servidores front-end

1.  En el generador de topología, vaya al nombre del grupo de servidores front-end que necesita cambiar.

2.  Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.

3.  En la sección **asociaciones** , en **asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.

4.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Recuperación ante desastres del servidor perimetral en Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

