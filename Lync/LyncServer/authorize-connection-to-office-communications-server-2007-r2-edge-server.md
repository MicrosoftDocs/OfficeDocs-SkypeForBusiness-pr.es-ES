---
title: Autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6adeaa07efea62697ecfbd38fede7d2f2191b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Para cada servidor front-end de Lync Server 2013 o servidor Standard Edition del grupo piloto, debe actualizar la lista de servidores internos que están autorizados a conectarse al servidor perimetral de Office Communications Server 2007 R2. Sin estas actualizaciones, no funcionará la conferencia de audio/vídeo (A/V) externa para los usuarios que se unen al servidor perimetral heredado.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Para autorizar la conexión al servidor perimetral de Office Communications Server 2007 R2

1.  Desde el servidor perimetral de Office Communications Server 2007 R2, en el grupo **herramientas administrativas** , abra el complemento **Administración de equipos** .

2.  En el árbol de consola, expanda **Servicios y Aplicaciones**.

3.  Haga clic con el botón secundario en **Office Communications Server 2007 R2** y, a continuación, haga clic en **Propiedades**.

4.  Haga clic en la pestaña **Interno**.

5.  En **Agregar servidor**, haga clic en **Agregar**.

6.  En el cuadro de diálogo **Agregar Office Communications Server**, escriba la información apropiada:
    
      - Especifique el nombre de dominio completo (FQDN) de cada servidor front-end de Lync Server 2013 o servidor Standard Edition, y grupo de servidores de Lync Server 2013.
    
      - Especifique el FQDN del Director de Lync Server 2013 si configuró una ruta estática en el grupo de servidores que especifica el equipo del próximo salto por su FQDN.

7.  Una vez que haya agregado una entrada para cada 2013, servidor front-end, servidor Standard Edition, grupo de servidores y director de Lync Server, haga clic en **aplicar** y, a continuación, haga clic en **Aceptar** para cerrar la página de propiedades.

</div>

</div>

<span> </span>

</div>

</div>

</div>

