---
title: 'Lync Server 2013: Guía de aprovisionamiento para la conectividad de Lync y Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8684fb619c73145baa627c07bab64be9478232ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="7f63d-102">Guía de aprovisionamiento para Lync-conectividad de Skype en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f63d-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f63d-103">_**Última modificación del tema:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="7f63d-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="7f63d-104">Lync Server 2013 admite conectividad con Skype.</span><span class="sxs-lookup"><span data-stu-id="7f63d-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="7f63d-105">Esta conectividad permite a los usuarios de Lync 2013 agregar contactos de Skype mediante la cuenta de Microsoft de usuario de Skype (MSA).</span><span class="sxs-lookup"><span data-stu-id="7f63d-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="7f63d-106">Los clientes de Skype también pueden agregar usuarios de Lync a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="7f63d-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="7f63d-107">En función de las directivas establecidas administrativamente en Lync Server, los usuarios de Lync y Skype podrán comunicarse con la mensajería instantánea, ver la presencia de los demás e iniciar llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="7f63d-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="7f63d-108">La conectividad de Lync y Skype también es una característica de Lync Online y se puede habilitar para clientes de Lync Online desde el centro de administración de Lync en el portal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f63d-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="7f63d-109">Si Lync Server ya está configurado para conectarse con Windows Messenger mediante Public Instant Messaging Connectivity (PIC), la implementación ya está configurada para la conectividad entre Lync y Skype.</span><span class="sxs-lookup"><span data-stu-id="7f63d-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="7f63d-110">El único cambio que debería considerar es cambiar el nombre de la entrada de PIC de Messenger existente como Skype.</span><span class="sxs-lookup"><span data-stu-id="7f63d-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="7f63d-111">Para obtener más información, consulte Configuración del proveedor de PIC de Skype para Lync más adelante en esta guía.</span><span class="sxs-lookup"><span data-stu-id="7f63d-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f63d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7f63d-112">In This Section</span></span>

  - [<span data-ttu-id="7f63d-113">Nota sobre la conectividad entre Lync y Skype en Lync Server 2013 para clientes de Lync Online</span><span class="sxs-lookup"><span data-stu-id="7f63d-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="7f63d-114">Acceso al sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Lync Server desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f63d-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="7f63d-115">Habilitar la conectividad entre Lync y Skype en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f63d-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="7f63d-116">Usar la conectividad de Lync y Skype en Lync Server 2013 como un usuario final</span><span class="sxs-lookup"><span data-stu-id="7f63d-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="7f63d-117">Preguntas más frecuentes: aprovisionamiento de Lync Server 2013 para conectividad de Skype</span><span class="sxs-lookup"><span data-stu-id="7f63d-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

