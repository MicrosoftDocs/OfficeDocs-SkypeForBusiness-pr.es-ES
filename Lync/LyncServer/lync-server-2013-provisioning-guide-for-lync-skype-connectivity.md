---
title: 'Lync Server 2013: Guía de aprovisionamiento para la conectividad entre Lync y Skype'
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
ms.openlocfilehash: f94da566e4322f9b8d1d039441c561f5ed60f6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="afec6-102">Guía de aprovisionamiento para la conectividad entre Lync y Skype en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afec6-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afec6-103">_**Última modificación del tema:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="afec6-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="afec6-p101">Lync Server 2013 es compatible con Skype. Esta conexión permite que sus usuarios de Lync 2013 agreguen contactos de Skype con el usuario de la cuenta Microsoft (MSA). Los clientes de Skype también pueden agregar usuarios de Lync a su lista de contactos. Basándose en las políticas establecidas administrativamente en Lync Server, los usuarios de Lync y Skype podrán comunicarse a través de mensajería instantánea, verse los unos a los otros e iniciar llamadas de audio y vídeo. La conectividad entre Lync y Skype es una característica disponible en Lync Online y puede activarse para los clientes de Lync Online desde el centro de administración de Lync en el portal de Office 365.</span><span class="sxs-lookup"><span data-stu-id="afec6-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="afec6-p102">Si Lync Server ya está configurado para conectarse con Windows Messenger a través de Public Instant Messaging Connectivity (PIC), la implementación ya está configurada para la conectividad entre Lync y Skype. El único cambio que podría considerar sería cambiar el nombre de la entrada PIC de Messenger como Skype. Para obtener más detalles, consulte Configurar el proveedor PIC de Skype para Lync más adelante en esta guía.</span><span class="sxs-lookup"><span data-stu-id="afec6-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="afec6-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="afec6-112">In This Section</span></span>

  - [<span data-ttu-id="afec6-113">Nota acerca de Lync: conectividad de Skype en Lync Server 2013 para clientes de Lync Online</span><span class="sxs-lookup"><span data-stu-id="afec6-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="afec6-114">Acceder al aprovisionamiento de la conectividad de mensajería instantánea pública para Lync Server desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afec6-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="afec6-115">Activar la conectividad entre Lync y Skype en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afec6-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="afec6-116">Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afec6-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="afec6-117">Preguntas frecuentes: Aprovisionamiento de conectividad de Lync Server 2013 para Skype</span><span class="sxs-lookup"><span data-stu-id="afec6-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

