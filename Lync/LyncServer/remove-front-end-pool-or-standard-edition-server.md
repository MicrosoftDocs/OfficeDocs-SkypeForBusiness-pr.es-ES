---
title: Quitar un grupo de servidores front-end o servidor Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a3b08d6e8b4f0b792063b19a47889de11283c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>Quitar un grupo de servidores front-end o servidor Standard Edition

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Este tema le guiará a través del proceso de eliminación de un grupo de servidores front-end o de un servidor front-end Standard Edition. Al quitar un grupo de servidores front-end, se quita cada servidor front-end que pertenece al grupo como parte del proceso de eliminación de la agrupación. Al quitar un servidor front-end Standard Edition, debe quitar la definición de la tienda SQL del generador de topología.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>Para quitar un grupo de servidores front-end

1.  Abra el generador de topologías.

2.  Vaya al nodo de 2010 de Lync Server.

3.  Expanda agrupaciones **front end de Enterprise Edition**, expanda el grupo de servidores front-end, haga clic con el botón secundario en el grupo de servidores front-end que desee quitar y, a continuación, haga clic en **eliminar**.

4.  Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Para quitar un servidor front-end Standard Edition

1.  Abra el generador de topologías.

2.  Vaya al nodo de 2010 de Lync Server.

3.  Expanda **servidores front-end Standard Edition**, haga clic con el botón secundario en el servidor front-end que desee quitar y, a continuación, haga clic en **eliminar**.

4.  Expanda **almacenes SQL**, haga clic con el botón secundario en la base de datos de SQL Server asociada al servidor front-end Standard Edition y, después, haga clic en **eliminar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Debe quitar la definición de las bases de datos de SQL Server en el servidor front-end Standard Edition.

    
    </div>

5.  Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

