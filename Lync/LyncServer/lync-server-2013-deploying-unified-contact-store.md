---
title: 'Lync Server 2013: Implementar el almacenamiento de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94f4c52eb3adda31f32de410f139154788fa37e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="bac6b-102">Implementar el almacenamiento de contactos unificado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6b-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac6b-103">_**Última modificación del tema:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="bac6b-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="bac6b-104">Habilitar el almacén de contactos unificado en Lync Server 2013 no requiere ninguna configuración de topología.</span><span class="sxs-lookup"><span data-stu-id="bac6b-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="bac6b-105">Para habilitar el almacén de contactos unificado para los usuarios, necesita lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bac6b-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="bac6b-106">La directiva del almacén de contactos unificado está habilitada (que es el comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="bac6b-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="bac6b-107">Los usuarios inician sesión en Lync 2013 al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="bac6b-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="bac6b-108">Después de migrar los contactos de un usuario, lo cual sucede automáticamente cuando un usuario inicia sesión con Lync 2013, el usuario puede tener acceso y administrar sus contactos de Lync desde Lync 2013, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="bac6b-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="bac6b-109">El usuario no tiene que haber iniciado sesión en Lync para administrar sus contactos desde Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="bac6b-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bac6b-110">Si un usuario inicia sesión desde Lync 2010 después de la migración, los contactos y grupos están disponibles y actualizados, pero el usuario no puede administrarlos (es decir, agregar, eliminar, mover, etiquetar, quitar o modificar) esos contactos.</span><span class="sxs-lookup"><span data-stu-id="bac6b-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bac6b-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bac6b-111">In This Section</span></span>

  - [<span data-ttu-id="bac6b-112">Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6b-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="bac6b-113">Realizar la migración de usuarios a almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6b-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="bac6b-114">Revertir usuarios migrados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6b-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

