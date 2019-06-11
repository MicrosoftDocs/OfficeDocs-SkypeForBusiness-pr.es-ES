---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conecte el grupo de servidores piloto a los servidores perimetrales heredados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Después de implementar Lync Server 2013, no se configura una ruta de Federación para este sitio. Para poder usar la ruta federada que usa Office Communications Server 2007 R2, Lync Server 2013 debe estar configurado para usar esta ruta.

Para habilitar el sitio de Lync Server 2013 para que use el director y el servidor perimetral de la BackCompatSite, use el generador de topologías para asociar el grupo perimetral heredado.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo perimetral heredado mediante el generador de topología

1.  Abra la topología de la agrupación piloto en el generador de topología.

2.  Seleccione el sitio de 2013 de Lync Server.

3.  En el menú **acción** , haga clic en **Editar propiedades**.

4.  En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el director de Office Communications Server 2007 R2 o el servidor perimetral de Office Communications Server 2007 R2 si no se muestra ningún director.
    
    ![Cuadro de diálogo Editar propiedades, página Ruta de Federación] (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")  

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

6.  En el generador de topologías, en el nodo de 2013 de Lync Server, vaya a los grupos de servidores **Standard Edition** o **Enterprise Edition**, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

7.  En **asociaciones**, active la casilla situada junto a **asociar grupo perimetral (para componentes multimedia)**.

8.  En la lista, seleccione la interfaz del servidor perimetral para la BackCompatSite.
    
    ![Cuadro de diálogo Editar propiedades, página general] (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")  

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

10. En el **generador**de topologías, seleccione el nodo de nivel superior, **Lync Server**.

11. En el menú **acción** , haga clic en **publicar topología**y, a continuación, haga clic en **siguiente**.

12. Cuando finalice el **Asistente para la publicación** , haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

