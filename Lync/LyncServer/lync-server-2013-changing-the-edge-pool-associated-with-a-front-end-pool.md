---
title: 'Lync Server 2013: cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ad6ee6e40edb76d4ef5d7d53524f89e44a2aee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Si se produce un error en un grupo perimetral pero el grupo de front-end del mismo sitio sigue en ejecución, deberá establecer el grupo de servidores front-end para que use un grupo perimetral de otro sitio hasta que se restablezca el grupo perimetral en el que se ha producido el error.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Cambio del grupo perimetral asociado a un grupo de servidores front-end

1.  En el Generador de topologías, navegue hasta el nombre del grupo de servidores front-end que desea cambiar.

2.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **Asociaciones**, en **Asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.

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

