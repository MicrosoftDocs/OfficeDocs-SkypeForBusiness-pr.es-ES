---
title: Quitar BackCompatSite
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
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Quitar BackCompatSite

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

4.  On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.
    
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

