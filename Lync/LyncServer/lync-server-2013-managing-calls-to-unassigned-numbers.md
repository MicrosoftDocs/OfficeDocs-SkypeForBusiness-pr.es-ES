---
title: 'Lync Server 2013: administración de llamadas a números sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 154f32e22ccce5ae23a4e3dceb175072618cc289
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="1b599-102">Administración de llamadas a números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b599-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b599-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1b599-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1b599-104">Lync Server le permite configurar el control de llamadas telefónicas entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o teléfono.</span><span class="sxs-lookup"><span data-stu-id="1b599-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="1b599-105">Puede usar la aplicación de anuncio para transferir estas llamadas a un destino predeterminado (número de teléfono, URI del SIP o correo de voz), o bien, reproducir un anuncio de audio o ambos.</span><span class="sxs-lookup"><span data-stu-id="1b599-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="1b599-106">También puede transferir estas llamadas a un número de teléfono del operador automático de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b599-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="1b599-107">Controlar las llamadas a números sin asignar de una de estas maneras ayuda a evitar las situaciones en las que el autor de la llamada marca un error de marcado y, a continuación, oye un tono ocupado o el cliente SIP recibe un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="1b599-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="1b599-108">En esta sección se describe cómo administrar intervalos de números sin asignar para controlar las llamadas a números de teléfono sin asignar.</span><span class="sxs-lookup"><span data-stu-id="1b599-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="1b599-109">La sección también describe cómo administrar anuncios durante la recuperación ante desastres si desea que esta funcionalidad se produzca durante una interrupción.</span><span class="sxs-lookup"><span data-stu-id="1b599-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b599-110">El uso de la administración de números sin asignar durante una interrupción es opcional.</span><span class="sxs-lookup"><span data-stu-id="1b599-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b599-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1b599-111">In This Section</span></span>

  - [<span data-ttu-id="1b599-112">Crear un anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b599-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="1b599-113">Configurar números de teléfono sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b599-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="1b599-114">Administrar anuncios durante la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b599-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

