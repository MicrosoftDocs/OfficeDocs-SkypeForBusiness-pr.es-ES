---
title: 'Lync Server 2013: modificar el filtro de transferencia de archivos predeterminado'
description: 'Lync Server 2013: modificar el filtro de transferencia de archivos predeterminado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8091dfebea87b793c56b9a670cfeeeab15ce6c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566936"
---
# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Lync Server 2013 proporciona un filtro de transferencia de archivos global que bloquea determinados tipos de archivos durante las siguientes actividades relacionadas con archivos dentro de la implementación de Lync Server 2013:

  - Solicitudes de transferencia de archivos durante las conversaciones de mensajería instantánea (mi)

  - Cargas y descargas de archivos al usar la característica de documentos en el cliente de Office Live Meeting 2007

  - Reproducción multimedia durante las conferencias

En función de los tipos de archivos que quiera bloquear o permitir, puede usar el panel de control de Lync Server para modificar el filtro global. Para obtener más información sobre el filtrado de transferencia de archivos, consulte [configuración de transferencia de archivos y filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Para modificar el filtro de transferencia de archivos predeterminado

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Mensajería instantánea y presencia** y, a continuación, en **Filtro de archivo**.

4.  En la página **filtro de archivos** , haga doble clic en el filtro **global** .

5.  En **Editar filtro de archivo**, active la casilla de verificación **Habilitar filtro de archivos** .

6.  En el cuadro de lista desplegable **transferencia de archivos** , haga clic en **bloquear todos** o en **bloquear tipos de archivo específicos**.

7.  Si hizo clic en **bloquear todos**, vaya al paso 9.

8.  Si hizo clic en **Bloquear tipos de archivos específicos**, haga lo siguiente:
    
    1.  Haga clic en **Seleccionar** para modificar la lista predeterminada de las extensiones de tipo de archivo que desea bloquear.
    
    2.  En **Seleccionar tipo de archivo**, seleccione los tipos de archivo que desea bloquear o permitir agregando o quitando sus extensiones de las categorías de **extensiones de tipo de archivo**.
    
    3.  Si no ve la extensión para un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista** y, a continuación, haga clic en **Agregar**.
    
    4.  Haga clic en **Aceptar**.

9.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración de la transferencia de archivos y el filtrado de URL para la mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Crear un nuevo filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modificar el filtro de direcciones URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

