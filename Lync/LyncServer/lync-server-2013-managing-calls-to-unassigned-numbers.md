---
title: 'Lync Server 2013: administración de llamadas a números no asignados'
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
ms.openlocfilehash: 571bddf8de62d7b22ac23a3b00de740030a2f7ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="4b473-102">Administración de llamadas a números no asignados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b473-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b473-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4b473-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4b473-104">Lync Server le permite configurar el control de las llamadas telefónicas entrantes cuando el número marcado es válido para su organización, pero no está asignado a un usuario o teléfono.</span><span class="sxs-lookup"><span data-stu-id="4b473-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="4b473-105">Puede usar la aplicación de anuncios para transferir estas llamadas a un destino predeterminado (número de teléfono, URI del SIP o correo de voz), o reproducir un anuncio de audio o ambos.</span><span class="sxs-lookup"><span data-stu-id="4b473-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="4b473-106">También puedes transferir estas llamadas a un número de teléfono de operador automático de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4b473-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="4b473-107">Controlar las llamadas a números no asignados de una de estas maneras le ayuda a evitar las situaciones en las que una persona que llama marca y escucha un tono de ocupado, o el cliente SIP recibe un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4b473-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="4b473-108">En esta sección se describe cómo administrar intervalos numéricos no asignados para controlar llamadas a números de teléfono sin asignar.</span><span class="sxs-lookup"><span data-stu-id="4b473-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="4b473-109">En la sección también se describe cómo administrar los anuncios durante la recuperación de desastres si quiere esta funcionalidad durante una interrupción.</span><span class="sxs-lookup"><span data-stu-id="4b473-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b473-110">El manejo de números no asignados durante una interrupción es opcional.</span><span class="sxs-lookup"><span data-stu-id="4b473-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4b473-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4b473-111">In This Section</span></span>

  - [<span data-ttu-id="4b473-112">Crear un anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b473-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="4b473-113">Configurar números de teléfono sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b473-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="4b473-114">Administrar anuncios durante la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b473-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

