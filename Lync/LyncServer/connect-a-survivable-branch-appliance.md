---
title: Conectar una aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Conectar una aplicación de sucursal con funciones de supervivencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end que sirve como registrador de copias de seguridad de la SBA. Cuando el grupo de servidores front-end se migra a Lync Server 2013, SBA debe desasociarse del grupo de servidores front-end de Lync Server 2010 mientras se actualiza el grupo, una vez que el grupo se ha migrado a Lync Server 2013, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado. Esto implica eliminar SBA de la topología heredada de Lync Server 2010 en el generador de topología y, a continuación, agregar SBA a la topología de Lync Server 2013. Los usuarios alojados en el antiguo Lync Server 2010 SBA deben moverse primero a otro grupo de servidores front end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Lync Server 2013, esos usuarios podrán volver a la SBA. Estos pasos se resumen a continuación:

1.  Mueva los usuarios alojados en el servidor de Lync existente de SBA de 2010 a otro grupo de servidores front-end.

2.  Quite SBA de la topología heredada de Lync Server 2010 para desconectar el grupo de servidores front-end existente como registrador de copias de seguridad.

3.  Agregue SBA a la topología de Lync Server 2013 y configúrela como registrador de la copia de seguridad.

4.  Mueva los usuarios de la sucursal al nuevo Lync Server 2013 SBA.

**Agregar el sitio de la sucursal de SBA de Lync Server 2010 a su topología**

1.  Abra el **generador**de topologías.

2.  En el panel izquierdo, haga clic con el botón secundario en **sitios de sucursales**y luego haga clic en **nuevo sitio de rama**.

3.  En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre del sitio de la sucursal.

4.  Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.

5.  Haga clic en **Siguiente**.

6.  Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones:
    
    1.  Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.
    
    2.  Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.
    
    3.  Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.

7.  Haga clic en **siguiente**y, a continuación, siga uno de estos procedimientos:
    
    1.  Si está usando un equipo o servidor de una sucursal de Lync 2010, asegúrese de desactivar la opción **abrir el nuevo asistente superviviente cuando se cierre este asistente** . Haga clic en **Finalizar**.

8.  Para asociar el servidor de Lync Server 2010 SBA al grupo front-end de Lync Server 2013:
    
    1.  Expanda el sitio de la sucursal que ha creado.
    
    2.  Haga clic con el botón secundario en **Lync Server 2010** y, a continuación, haga clic en **nuevo**.
    
    3.  Haga clic en **equipo de rama superviviente...**

9.  Siga las instrucciones del asistente que se abre. Para obtener información sobre los elementos del asistente, consulte [definir un dispositivo o servidor de sucursal con la que sea reviviente en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Un dispositivo de sucursal 2010 de Lync Server solo se puede asociar con un almacén de supervisión de Lync Server 2010.

    
    </div>

10. Si no usa un equipo o servidor de sucursal con la supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.

11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

</div>

<span> </span>

</div>

</div>

</div>

