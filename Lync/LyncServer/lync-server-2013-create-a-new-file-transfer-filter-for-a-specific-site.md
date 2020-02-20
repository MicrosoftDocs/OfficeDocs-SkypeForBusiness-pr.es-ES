---
title: 'Lync Server 2013: crear un filtro de transferencia de archivos nuevo para un sitio específico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a374cb234567c5aeb44ce6071f6e67559c5159ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Además de modificar el filtro de transferencia global de archivos, puede configurar filtros de transferencia de archivos personalizados para sitios específicos dentro de la implementación de Lync Server 2013. Para obtener más información sobre el filtrado de transferencia de archivos, consulte [configuración de transferencia de archivos y filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Para crear un filtro de transferencia de archivos para un sitio específico

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro de archivo**.

4.  En la página **Filtro de archivo**, haga clic en **Nuevo**.

5.  En el cuadro de diálogo **Seleccionar un sitio**, haga clic en el sitio para el que desea crear un filtro de transferencia de archivos y, a continuación, haga clic en **Aceptar**.

6.  En **Nuevo filtro de archivo**, haga clic en la casilla **Habilitar filtro de archivos**.

7.  En la lista desplegable **Transferencia de archivos**, haga clic en **Bloquear todos** o en **Bloquear tipos de archivos específicos**.

8.  Si hizo clic en **Bloquear todos**, vaya al paso 9.

9.  Si hizo clic en **Bloquear tipos de archivos específicos**, haga lo siguiente:
    
    1.  Haga clic en **Seleccionar** para modificar la lista predeterminada de las extensiones de tipo de archivo que desea bloquear.
    
    2.  En el cuadro de diálogo **Seleccionar tipo de archivo**, seleccione los tipos de archivo que desea bloquear o permitir; para ello permita o quite sus extensiones de las categorías en **Extensiones de tipo de archivo**.
    
    3.  Si no ve la extensión para un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista** y, a continuación, haga clic en **Agregar**.
    
    4.  Haga clic en **Aceptar**.

10. Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar el filtro de direcciones URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

