---
title: 'Lync Server 2013: crear un filtro de transferencia de archivos para un sitio específico'
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
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Crear un filtro de transferencia de archivos nuevo en Lync Server 2013 para un sitio específico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Además de modificar el filtro global de transferencia de archivos, puede configurar filtros de transferencia de archivos personalizados para sitios específicos dentro de la implementación de Lync Server 2013. Para más información sobre el filtrado de transferencia de archivos, vea [configuración de la transferencia de archivos y filtrado de URL para mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Para crear un filtro de transferencia de archivos para un sitio específico

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **mensajería instantánea y presencia** y, a continuación, haga clic en **filtro de archivos**.

4.  En la página **filtro de archivos** , haga clic en **nuevo**.

5.  En el cuadro de diálogo **seleccionar un sitio** , haga clic en el sitio para el que desea crear el filtro de transferencia de archivos y, a continuación, haga clic en **Aceptar**.

6.  En **filtro de archivo nuevo**, haga clic en la casilla de verificación **Habilitar filtro de archivos** .

7.  En el cuadro de lista desplegable **transferencia de archivos** , haga clic en **bloquear todo** o **bloquear tipos de archivo específicos**.

8.  Si hizo clic en **bloquear todo**, vaya al paso 10.

9.  Si hizo clic en **bloquear tipos de archivo específicos**, siga este procedimiento:
    
    1.  Haga clic en **seleccionar** para modificar la lista predeterminada de extensiones de tipo de archivo que desea bloquear.
    
    2.  En el cuadro de diálogo **Seleccionar tipo de archivo** , seleccione los tipos de archivo que desea bloquear o permitir agregando o quitando sus extensiones de las categorías de **extensiones de tipo de archivo**.
    
    3.  Si no ve la extensión de un tipo de archivo que desea bloquear, escriba la extensión en el cuadro de texto en **Agregar extensiones de tipo de archivo a la lista**y, a continuación, haga clic en **Agregar**.
    
    4.  Haga clic en **Aceptar**.

10. Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la transferencia de archivos y el filtrado de URL para mensajería instantánea (mi) en Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Crear un filtro de dirección URL en Lync Server 2013 para administrar hipervínculos en conversaciones de mensajería instantánea](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modificar el filtro de transferencia de archivos predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modificar el filtro de dirección URL predeterminado en Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

