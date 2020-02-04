---
title: Transición de un servidor de mediación en un servidor de mediación independiente (opcional)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c6a76bceb935900521859911ce5398ae2213e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Transición de un servidor de mediación en un servidor de mediación independiente (opcional)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Use el procedimiento que se indica a continuación para realizar la transición de su servidor de mediación, en el servidor Standard Edition o en el grupo front-end, a un servidor de mediación independiente para una implementación de sitio único.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Para migrar un servidor de mediación ordenada a un servidor de mediación independiente

1.  Abra una topología existente desde el generador de topología.

2.  En el panel de la izquierda, vaya a **grupos de mediación**.

3.  Haga clic con el botón secundario en **grupos de mediación** y seleccione **nuevo servidor de mediación**.

4.  En la página **definir nuevo grupo de mediación** , proporcione el FQDN del nuevo grupo de servidores de mediación. Además, seleccione si este grupo será un solo servidor o un grupo de varios servidores y, a continuación, haga clic en **siguiente**.

5.  Seleccione el grupo de servidores front-end de próximo salto al que el servidor de mediación enrutará las llamadas entrantes y, a continuación, haga clic en **siguiente**.

6.  Seleccione el grupo perimetral que va a usar el servidor de mediación y, a continuación, haga clic en **siguiente**.

7.  En la página **especificar puertas de enlace RTC** , asocie la puerta de enlace RTC anterior con el servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en **Agregar**.

8.  Haga clic en **Finalizar** para cerrar el asistente **definir nuevo grupo de mediación** .

9.  En el **generador de topologías**, seleccione el nodo superior de **Lync Server 2013**.

10. En el panel **acciones** , seleccione **publicar topología** y complete el asistente.

11. Siga los pasos que se indican en [instalar los archivos de Media Server en Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) en la documentación de implementación para instalar los archivos en el nuevo servidor de mediación.

12. Una vez que los archivos estén instalados en el servidor de mediación, vuelva al generador de topología y, en el panel izquierdo, vaya al grupo.

13. Haga clic con el botón derecho en el grupo y seleccione **Editar propiedades**.

14. En **servidor de mediación**, desactive la casilla servidor de mediación con el que **está habilitada** y haga clic en **Aceptar**.

15. En el **generador de topologías**, seleccione el nodo superior de **Lync Server 2013**.

16. En el menú **acción** , seleccione **publicar topología** y complete el asistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

