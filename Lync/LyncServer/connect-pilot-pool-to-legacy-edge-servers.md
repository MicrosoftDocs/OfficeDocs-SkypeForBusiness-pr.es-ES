---
title: Conectar el grupo piloto a servidores perimetrales heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9213dbf5d75b80ccbfc67d03cfb3c02ef87145
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar el grupo piloto a servidores perimetrales heredados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Después de implementar Lync Server 2013, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que usa Lync Server 2010, Lync Server 2013 debe estar configurado para usar esta ruta.

Para habilitar el sitio de Lync Server 2013 para usar el director y el servidor perimetral de la implementación de Lync Server 2010, use el generador de topologías para asociar el grupo de servidores perimetrales heredados.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para asociar el grupo de servidores perimetrales heredado con el Generador de topologías:

1.  Abra el **Generador de topologías**.

2.  Seleccione el sitio, que se encuentra justo debajo del nodo **Lync Server**.

3.  En el menú **Acciones**, haga clic en **Editar propiedades**.

4.  En el panel izquierdo, seleccione **Ruta de federación**.

5.  En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el Director de Lync Server 2010 o el servidor perimetral de Lync Server 2010 si no aparece ningún director.
    
    ![Editar propiedades, página Ruta de Federación](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propiedades, página Ruta de Federación")  

6.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.

7.  En el generador de topologías, en el nodo Lync Server 2013, vaya a los grupos de servidores **front-end** **Standard Edition** o Enterprise Edition, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.

8.  En **Asociaciones**, active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**.

9.  En la lista, seleccione el servidor perimetral heredado.
    
    ![Cuadro de diálogo Editar propiedades, selección del perímetro heredado](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Cuadro de diálogo Editar propiedades, selección del perímetro heredado")  

10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.

11. En el **Generador de topologías**, seleccione el nodo superior, **Lync Server**.

12. En el menú **Acciones**, haga clic en **Publicar topología** y en **Siguiente**.

13. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

