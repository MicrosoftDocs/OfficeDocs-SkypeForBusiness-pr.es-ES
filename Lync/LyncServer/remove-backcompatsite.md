---
title: Quitar BackCompatSite
description: Quite BackCompatSite.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809324320ec1869ac0c9d324b8fc270a3cf8f174
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570276"
---
# <a name="remove-backcompatsite"></a>Quitar BackCompatSite

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Una vez que se desactivaron todos los grupos de servidores y se desinstalaron todos los servidores perimetrales, ejecute el asistente para la combinación del Generador de topologías a fin de quitar **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Para quitar el sitio BackCompat del Generador de topologías

1.  Abra una implementación existente del Generador de topologías.

2.  En el menú **Acción**, haga clic en **Combinar topología de 2007**.

3.  Haga clic en **Siguiente ** para continuar.

4.  En la página **Especificar servidor perimetral heredado**, asegúrese de que la lista de servidores perimetrales esté vacía. Si no lo está, utilice el botón **Quitar** para quitar todos los servidores perimetrales heredados y, a continuación, haga clic en **Siguiente**.
    
    ![Asistente para combinar topología, especificar página de configuración perimetral](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Asistente para combinar topología, especificar página de configuración perimetral")  

5.  En la página **Especificar puerto SIP interno**, haga clic en **Siguiente**.

6.  En la página **Resumen** , haga clic en **siguiente** para comenzar a combinar las topologías para quitar el sitio heredado.

7.  En la columna **Estado**, compruebe que el valor sea **Correcto** y haga clic en **Finalizar** para cerrar el asistente.

8.  En el panel izquierdo de Topology Builder, expanda BackCompatSite y compruebe que no se muestre ningún servidor.

9.  Haga clic con el botón secundario en **BackCompatSite** y, a continuación, haga clic en **Eliminar**.

10. En el **Generador de topologías**, seleccione el primer nodo **Lync Server**.

11. En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.

12. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

