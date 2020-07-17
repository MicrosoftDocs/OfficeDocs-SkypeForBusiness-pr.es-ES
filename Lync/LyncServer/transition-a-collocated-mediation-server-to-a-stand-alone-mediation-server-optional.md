---
title: Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce0228edacba502161c4d44a6a94b38cede6655
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Utilice el procedimiento siguiente para realizar la transición del servidor de mediación, combinado en el servidor Standard Edition o grupo Front-End, a un servidor de mediación independiente para una implementación de sitio único.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Para realizar la transición de un servidor de mediación combinado a un servidor de mediación independiente

1.  Abre una topología existente del Generador de topologías.

2.  En el panel izquierdo, vaya a **Grups de mediación  **.

3.  Haga clic con el botón secundario en **Grupos de mediación**    y seleccione **Nuevo servidor de mediación  **.

4.  En la página **Definir nuevo grupo de servidores de mediación**, proporcione el nombre completo del nuevo grupo de servidor de mediación. Además, seleccione si este grupo va a ser un grupo de servidor único o de varios servidores y, a continuación, haga clic en **Siguiente**.

5.  Seleccione el siguiente grupo de salto del servidor de usuario al que el nuevo servidor de mediación enrutará las llamadas entrantes y, a continuación, haga clic en **Siguiente**.

6.  Seleccione el grupo perimetral que va a usar el servidor de mediación y, a continuación, haga clic en **Siguiente**.

7.  En la página **Definir nuevo grupo de servidores de mediación**, asocie la puerta de enlace RTC anterior con el servidor de mediación. Seleccione la puerta de enlace y, a continuación, haga clic en **Agregar  **.

8.  Haga clic en **Finalizar ** para cerrar el asistente **Definir nuevo grupo de servidores de mediación  **.

9.  En **generador de topologías**, seleccione el nodo superior **Lync Server 2013**.

10. En el panel **Acciones**, seleccione **Publicar topología** y complete el asistente.

11. Siga los pasos descritos en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) en la documentación de implementación para instalar los archivos en el nuevo servidor de mediación.

12. Después de instalar los archivos en el servidor de mediación, vuelva al generador de topologías y en el panel izquierdo, desplácese al grupo.

13. Haga clic con el botón derecho en el grupo y seleccione **Editar propiedades**.

14. En    **Servidor de mediación  **, desactive la casilla **Servidor de mediación combinado habilitado** y, a continuación, haga clic en **Aceptar**.

15. En **generador de topologías**, seleccione el nodo superior **Lync Server 2013**.

16. Desde el menú **Acción**, seleccione **Publicar topología** y complete el asistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

