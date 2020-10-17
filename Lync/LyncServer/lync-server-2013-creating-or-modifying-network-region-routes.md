---
title: 'Lync Server 2013: creación o modificación de rutas de región de red'
description: 'Lync Server 2013: creación o modificación de rutas de región de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544096"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Creación o modificación de rutas de región de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Todas las regiones dentro de una configuración de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el panel de control de Lync Server para configurar rutas de región de red. En el panel de control de Lync Server, puede crear, modificar o eliminar una ruta de región de red. Consulte este tema para crear o modificar una ruta regional de red. Para obtener más información sobre cómo eliminar rutas de regiones de red existentes, consulte [eliminar rutas de regiones de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Para crear una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.

4.  En la página **Ruta regional**, haga clic en **Nueva**.

5.  En **Nueva ruta regional**, escriba un valor en el campo **Nombre**.
    
    <div>
    

    > [!NOTE]  
    > Este valor debe ser único dentro de la implementación de Microsoft Lync Server 2013.

    
    </div>

6.  En la lista desplegable **región de red \# 1** , seleccione una de las dos regiones que se conectarán mediante esta ruta.

7.  En la lista desplegable **región de red \# 2** , seleccione la otra región de esta ruta. Esta región debe ser diferente de la región seleccionada para la región de red \# 1.

8.  Use el cuadro de lista **Vínculos de región de red** para agregar vínculos de red a la ruta. Haga clic en el botón **Agregar** para mostrar la página **Vínculo regional**. Haga clic en un vínculo regional para agregarlo a esta ruta y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Haga clic otra vez en el botón <STRONG>Agregar</STRONG> para añadir más vínculos, o seleccione un vínculo y haga clic en <STRONG>Eliminar</STRONG> para eliminarlo.

    
    </div>

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Para modificar una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.

4.  En la página **Ruta regional**, haga clic en la ruta regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar ruta regional**, puede modificar las regiones agregadas a esta ruta y los vínculos regionales asociados a la misma.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Eliminación de rutas de región de red existentes en Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

