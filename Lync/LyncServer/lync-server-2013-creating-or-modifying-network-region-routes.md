---
title: 'Lync Server 2013: crear o modificar rutas de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31daafe6cafbf74f9f12812f8259c24cfa7349
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Crear o modificar rutas de región de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-08_

Cada región dentro de una configuración de control de admisión de llamadas (CAC) debe tener alguna forma de tener acceso a todas las demás regiones. Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre las regiones y también representan los vínculos físicos, una ruta determina qué ruta de acceso vinculada pasará la conexión de una región a otra. Puede usar el panel de control de Lync Server para configurar las rutas de la región de red. En el panel de control de Lync Server, puede crear, modificar o eliminar una ruta de región de red. Use este tema para crear o modificar una ruta de región de red. Para más información sobre cómo eliminar una ruta de la región de red existente, vea [eliminar las rutas de la región de red existente en Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Para crear una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y luego en **ruta de región**.

4.  En la página Ruta de la **región** , haga clic en **nuevo**.

5.  En **ruta de nueva región**, escriba un valor en el campo **nombre** .
    
    <div>
    

    > [!NOTE]  
    > Este valor debe ser único dentro de la implementación de Microsoft Lync Server 2013.

    
    </div>

6.  En la lista desplegable ** \#región de red 1** , seleccione una de las dos regiones que se van a conectar mediante esta ruta.

7.  En la lista desplegable ** \#región de red 2** , seleccione la otra región de esta ruta. Esta región debe ser diferente de la región seleccionada para la región \#de red 1.

8.  Use el cuadro de lista **vínculos de región de red** para agregar vínculos de región a la ruta. Haga clic en el botón **Agregar** para mostrar la página de vínculos de la **región** . Haga clic en un vínculo de región para agregar a esta ruta y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Siga haciendo clic en el botón <STRONG>Agregar</STRONG> para agregar más vínculos o seleccione un vínculo y haga clic en <STRONG>quitar</STRONG> para quitar un vínculo.

    
    </div>

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Para modificar una ruta de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y luego en **ruta de región**.

4.  En la página Ruta de la **región** , haga clic en la ruta de la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la **ruta de edición región**, puede modificar las regiones Unidas por esta ruta y los vínculos de región asociados a la ruta.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar las rutas de la región de red existente en Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

