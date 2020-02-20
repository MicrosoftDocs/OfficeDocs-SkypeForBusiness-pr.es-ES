---
title: Crear un nuevo filtro de dirección URL para administrar hipervínculos en conversaciones de mensajería instantánea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 250533f8de89eb1cd5aaa72d8f66cfd0800a1bc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Además de modificar el filtro de dirección URL global, puede configurar filtros de URL personalizados para sitios individuales dentro de la implementación de Lync Server 2013. Para obtener más información sobre el filtrado de URL, consulte [configuración de transferencia de archivos y filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Para crear un filtro nuevo para direcciones URL

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro para direcciones URL**.

4.  En la página **Filtro para direcciones URL**, haga clic en **Nuevo**.

5.  En el cuadro de diálogo **Seleccionar un sitio**, haga clic en el sitio para el que desea crear un filtro para direcciones URL y, a continuación, haga clic en **Aceptar**.

6.  En el cuadro **Filtro para direcciones URL nuevo**, active la casilla **Habilitar filtro para direcciones URL** para habilitar el filtrado para direcciones URL del sitio.

7.  Para bloquear cualquier URL activa que contenga un archivo con una extensión que aparezca en **Extensiones de tipo de archivo a bloquear**, en **Editar filtro de archivo**, active la casilla **Bloquear direcciones URL con extensión de archivo**.

8.  En la lista desplegable **Prefijo de hipervínculo**, haga clic en la opción que corresponde a cómo desea administrar direcciones URL en conversaciones de mensajería instantánea.
    
    Con el cuadro **Permitir mensaje**, puede enviar un mensaje de advertencia al usuario cuando se envíen hipervínculos permitidos.

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar el filtro de direcciones URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

