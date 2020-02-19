---
title: 'Lync Server 2013: actualización de la lista de habilitación de Outlook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1f71d1ef0ebcb6bc5f8aee8875c013a24a4de0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Actualizar la lista de habilitación de Outlook en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-07_

Puede asegurarse de que el complemento de conferencia en línea para Microsoft Lync 2013 siempre sigue habilitado para los usuarios mediante la creación de una directiva que lo incluya en la lista de administración de complementos de Outlook. Esta directiva forma parte de los archivos de plantilla administrativa de Office de la Consola de administración de directivas de grupo. Crea una clave del registro en HKCU\\software\\\\Policies\\Microsoft\\Office\\15,0\\Outlook15 Resiliency\\AddinList. Puede Agregar un valor para ucaddin. dll a esta clave y configurar el valor de ucaddin. dll para que esté siempre habilitado y para que los usuarios no puedan deshabilitarlo manualmente

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Para agregar ucaddin. dll a la lista de complementos de Outlook

  - En la clave del registro AddinList, que se\\encuentra\\en\\la\\página\\directivas\\de\\software HKCU\\Microsoft Office 15,0 Outlook15 Resiliency AddinList, agregue el siguiente valor:
    
      - Tipo de registro =\_reg SZ
    
      - Nombre = ucaddin.dll
    
      - Valor = 1 (significa que el complemento siempre está habilitado y que el usuario final no puede administrarlo)

</div>

</div>

<span> </span>

</div>

</div>

</div>

