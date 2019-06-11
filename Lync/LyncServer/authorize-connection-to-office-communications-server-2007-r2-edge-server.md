---
title: Autorizar la conexión a Office Communications Server 2007 R2 servidor perimetral
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f81d8aaf9a01fc73516778487f8cc9a2d28a04ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorizar la conexión a Office Communications Server 2007 R2 servidor perimetral

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Para cada servidor front-end de Lync Server 2013 o servidor Standard Edition de su grupo piloto, debe actualizar la lista de servidores internos autorizados para conectarse al servidor perimetral de Office Communications Server 2007 R2. Sin estas actualizaciones, las conferencias de audio/visual (A/V) externas para usuarios que se unen mediante el servidor perimetral heredado no funcionarán.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Para autorizar la conexión con el servidor perimetral de Office Communications Server 2007 R2

1.  Desde el servidor perimetral de Office Communications Server 2007 R2, en el grupo **herramientas administrativas** , abra el complemento **Administración de equipos** .

2.  En el árbol de consola, expanda **servicios y aplicaciones**.

3.  Haga clic con el botón secundario en **Office Communications Server 2007 R2**y, a continuación, haga clic en **propiedades**.

4.  Haga clic en la pestaña **interno** .

5.  En **Agregar servidor**, haga clic en **Agregar**.

6.  En el cuadro de diálogo **Agregar Office Communications Server** , escriba la información adecuada:
    
      - Especifique el nombre de dominio completo (FQDN) de todos los servidores front-end de Lync Server 2013 o el servidor Standard Edition y el grupo de servidores de Lync Server 2013.
    
      - Especifique el FQDN del Director de Lync Server 2013 si ha configurado una ruta estática en el grupo que especifica el equipo del próximo salto por su FQDN.

7.  Una vez que haya agregado una entrada para cada servidor de Lync Server 2013, servidor front-end, servidor Standard Edition, grupo y director, haga clic en **aplicar** y, a continuación, haga clic en **Aceptar** para cerrar la página de propiedades.

</div>

</div>

<span> </span>

</div>

</div>

</div>

