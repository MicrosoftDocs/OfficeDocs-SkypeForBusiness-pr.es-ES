---
title: Crear un filtro de dirección URL para procesar hipervínculos en conversaciones de mensajería instantánea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Crear un filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

Además de modificar el filtro de dirección URL global, puede configurar filtros de URL personalizados para sitios individuales dentro de la implementación de Lync Server 2013. Para obtener más información sobre el filtrado de URL, consulte [configuración de la transferencia de archivos y filtrado de URL para mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Para crear un filtro de dirección URL nuevo

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **mensajería instantánea y presencia**y, a continuación, haga clic en **filtro de URL**.

4.  En la página **filtro de URL** , haga clic en **nuevo**.

5.  En **seleccionar un sitio**, haga clic en el sitio para el que desea crear el filtro de dirección URL y, a continuación, haga clic en **Aceptar**.

6.  En el cuadro de diálogo **nuevo filtro de URL** , seleccione la casilla de verificación **Habilitar filtro** de URL para habilitar el filtrado de URL para el sitio.

7.  Para bloquear cualquier dirección URL activa que contenga un archivo con una extensión enumerada en **extensiones de tipo de archivo que se bloquean** en **Editar filtro de archivo**, active la casilla **bloquear direcciones URL con extensión de archivo** .

8.  En el **** cuadro de lista desplegable prefijo del hipervínculo, haga clic en la opción que corresponde a cómo desea controlar las direcciones URL en las conversaciones de mensajes instantáneos.
    
    El cuadro **permitir mensaje** permite que se envíe un mensaje de advertencia al usuario al enviar hipervínculos que pueden enviarse.

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar el filtro de dirección URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

