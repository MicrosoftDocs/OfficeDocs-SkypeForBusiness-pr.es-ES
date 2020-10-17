---
title: 'Lync Server 2013: implementación de almacén de contactos unificados'
description: 'Lync Server 2013: implementación del almacén de contactos unificado.'
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
ms.openlocfilehash: 056792d2e4ea66699b276d0d571e83c8a0256483
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557756"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="3c840-103">Implementar el almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c840-103">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c840-104">_**Última modificación del tema:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="3c840-104">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="3c840-105">La habilitación del almacén de contactos unificados en Lync Server 2013 no requiere ninguna configuración de topología.</span><span class="sxs-lookup"><span data-stu-id="3c840-105">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="3c840-106">Para habilitar el almacén de contactos unificados para los usuarios, se debe cumplir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c840-106">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="3c840-107">La directiva de almacén de contactos unificados está habilitada (que es el comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c840-107">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="3c840-108">Los usuarios inician sesión con Lync 2013 al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="3c840-108">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="3c840-109">Una vez que se han migrado los contactos de un usuario, lo que ocurre automáticamente cuando un usuario inicia sesión con Lync 2013, puede tener acceso y administrar los contactos de Lync desde Lync 2013, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3c840-109">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="3c840-110">No es necesario que el usuario haya iniciado sesión en Lync para administrar sus contactos desde Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3c840-110">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3c840-111">Si un usuario inicia sesión desde Lync 2010 después de la migración, los contactos y los grupos están disponibles y actualizados, pero el usuario no puede administrarlos (es decir, agregar, eliminar, mover, etiquetar, quitar o modificar) dichos contactos.</span><span class="sxs-lookup"><span data-stu-id="3c840-111">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c840-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3c840-112">In This Section</span></span>

  - [<span data-ttu-id="3c840-113">Habilitar a los usuarios para el almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c840-113">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="3c840-114">Migrar usuarios a almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c840-114">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="3c840-115">Revertir usuarios migrados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c840-115">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

