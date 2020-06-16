---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conecte el grupo de servidores piloto a los servidores perimetrales heredados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Después de implementar Lync Server 2013, no se configura ninguna ruta de Federación para este sitio. Para poder usar la ruta federada que usa Office Communications Server 2007 R2, Lync Server 2013 debe estar configurado para usar esta ruta.

Para habilitar el sitio de Lync Server 2013 para usar el director y el servidor perimetral de BackCompatSite, use el generador de topologías para asociar el grupo de servidores perimetrales heredados.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo perimetral heredado mediante el Generador de topologías

1.  Abra la topología del grupo piloto en Topology Builder.

2.  Seleccione su sitio de Lync Server 2013.

3.  En el menú **Acción**, haga clic en **Editar propiedades**.

4.  En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el director de Office Communications Server 2007 R2 o el servidor perimetral de Office Communications Server 2007 R2 si no hay ningún director en la lista.
    
    ![Cuadro de diálogo Editar propiedades, página Ruta de Federación](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")  

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.

6.  En el generador de topologías, en el nodo Lync Server 2013, vaya a los grupos de servidores **front-end** **Standard Edition** o Enterprise Edition, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

7.  En **Asociaciones**, active la casilla que se encuentra junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**.

8.  En la lista, seleccione la interfaz del servidor perimetral de la BackCompatSite.
    
    ![Cuadro de diálogo Editar propiedades, página general](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")  

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.

10. En el **Generador de topologías**, seleccione el nodo superior, **Lync Server**.

11. En el menú **Acciones**, haga clic en **Publicar topología** y en **Siguiente**.

12. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

