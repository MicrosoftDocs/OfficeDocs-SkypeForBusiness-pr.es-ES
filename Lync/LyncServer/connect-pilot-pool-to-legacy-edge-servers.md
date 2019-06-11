---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc42c645548ea9bad072da5f18643271a9eceeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conecte el grupo de servidores piloto a los servidores perimetrales heredados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Después de implementar Lync Server 2013, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que está usando Lync Server 2010, Lync Server 2013 debe estar configurado para usar esta ruta.

Para habilitar el sitio de 2013 de Lync Server para que use el director y el servidor perimetral de la implementación de Lync Server 2010, use el generador de topología para asociar el grupo perimetral heredado.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo perimetral heredado mediante el generador de topología

1.  Abra el **generador**de topologías.

2.  Seleccione su sitio, que se encuentra directamente debajo del nodo de **Lync Server** .

3.  En el menú **acciones** , haga clic en **Editar propiedades**.

4.  En el panel de la izquierda, seleccione **ruta de Federación**.

5.  En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el Director de Lync Server 2010 o el servidor perimetral de Lync Server 2010 si no se muestra ningún director.
    
    ![Editar propiedades, página de ruta de Federación] (images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propiedades, página de ruta de Federación")  

6.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

7.  En el generador de topologías, en el nodo de 2013 de Lync Server, vaya a los grupos de servidores **Standard Edition** o **Enterprise Edition**, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

8.  En **asociaciones**, active la casilla situada junto a **asociar grupo perimetral (para componentes multimedia)**.

9.  En la lista, seleccione el servidor perimetral heredado.
    
    ![Cuadro de diálogo Editar propiedades, selección del borde heredado] (images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Cuadro de diálogo Editar propiedades, selección del borde heredado")  

10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

11. En el **generador**de topologías, seleccione el nodo de nivel superior, **Lync Server**.

12. En el menú **acción** , haga clic en **publicar topología**y, a continuación, haga clic en **siguiente**.

13. Cuando finalice el **Asistente para la publicación** , haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

