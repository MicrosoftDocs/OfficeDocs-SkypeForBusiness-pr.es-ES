---
title: 'Lync Server 2013: implementación de almacén de contactos unificados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c88b5264883d05eff717bb3b8d99f63a5640a2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a>Implementar el almacén de contactos unificados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-06_

La habilitación del almacén de contactos unificados en Lync Server 2013 no requiere ninguna configuración de topología. Para habilitar el almacén de contactos unificados para los usuarios, se debe cumplir lo siguiente:

  - La directiva de almacén de contactos unificados está habilitada (que es el comportamiento predeterminado).

  - Los usuarios inician sesión con Lync 2013 al menos una vez.

Una vez que se han migrado los contactos de un usuario, lo que ocurre automáticamente cuando un usuario inicia sesión con Lync 2013, puede tener acceso y administrar los contactos de Lync desde Lync 2013, Outlook 2013 o Outlook Web Access. No es necesario que el usuario haya iniciado sesión en Lync para administrar sus contactos desde Outlook o Outlook Web Access.

<div>


> [!IMPORTANT]  
> Si un usuario inicia sesión desde Lync 2010 después de la migración, los contactos y los grupos están disponibles y actualizados, pero el usuario no puede administrarlos (es decir, agregar, eliminar, mover, etiquetar, quitar o modificar) dichos contactos.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Habilitar a los usuarios para el almacén de contactos unificados en Lync Server 2013](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [Migrar usuarios a almacén de contactos unificados en Lync Server 2013](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [Revertir usuarios migrados en Lync Server 2013](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

