---
title: 'Lync Server 2013: compatibilidad con la integración de Exchange y SharePoint'
description: 'Lync Server 2013: compatibilidad con la integración de Exchange y SharePoint.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7416ffa23de9a0820c3087d18254810d58444ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564866"
---
# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="a49ed-103">Compatibilidad con la integración de Exchange y SharePoint en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a49ed-103">Exchange and SharePoint integration support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a49ed-104">_**Última modificación del tema:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="a49ed-104">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="a49ed-105">Lync Server 2013 y Lync 2013 pueden comunicarse de forma segura y sin problemas con otras aplicaciones y productos de servidor, incluidos Office 2013, Exchange Server 2013, Exchange Server 2016 y SharePoint, si estos productos se integran.</span><span class="sxs-lookup"><span data-stu-id="a49ed-105">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="a49ed-106">La integración de Lync Server 2013 y Office proporciona a los usuarios acceso en contexto a la mensajería instantánea (mi), la presencia mejorada, la telefonía y las capacidades de conferencia de Lync.</span><span class="sxs-lookup"><span data-stu-id="a49ed-106">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="a49ed-107">Los usuarios de Office pueden acceder a las características de Lync desde el cliente de mensajería y colaboración de Outlook 2013 y otros programas de Office o desde una página de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a49ed-107">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="a49ed-108">Los usuarios también pueden ver un registro de las conversaciones de Lync en la carpeta Historial de conversaciones de Outlook.</span><span class="sxs-lookup"><span data-stu-id="a49ed-108">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="a49ed-109">Cuando se integra con Exchange 2013, Exchange 2016 o Exchange Online, Lync Server 2013 también admite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a49ed-109">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="a49ed-110">Almacén de contactos unificado, que permite a los usuarios almacenar toda la información de contacto en Exchange o Exchange Online para que la información esté disponible de forma global en Lync 2013, Exchange, Outlook y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="a49ed-110">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="a49ed-111">Historial de conversaciones e historial de conferencias web, que se almacenan en las carpetas de usuario de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a49ed-111">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="a49ed-112">El contenido archivado de Lync, como la mensajería instantánea y el contenido de reuniones, se puede almacenar en el almacenamiento de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a49ed-112">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a49ed-113">Lync Server 2013 admite la integración con versiones anteriores de Microsoft Exchange Server y SharePoint Server, pero no todas las funciones son compatibles con estas versiones anteriores, como la integración del almacenamiento de archivado con Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="a49ed-113">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="a49ed-114">Si va a migrar los usuarios a Exchange 2013 o Exchange 2016, puede usar el almacenamiento de Exchange y el almacenamiento de Lync Server de manera provisional, mientras completa la migración.</span><span class="sxs-lookup"><span data-stu-id="a49ed-114">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="a49ed-115">No se admite el uso permanente de almacenamiento de Exchange y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a49ed-115">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="a49ed-116">La integración de Lync Server 2013 con Exchange Server y SharePoint Server requiere la autenticación de servidor a servidor entre los servidores que ejecutan Lync Server 2013, Exchange Server y SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="a49ed-116">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="a49ed-117">Lync Server 2013 admite el protocolo OAuth (Open Authorization) para la autenticación y autorización de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="a49ed-117">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="a49ed-118">Para la autenticación de servidor a servidor local entre dos servidores de Microsoft, no es necesario utilizar un servidor de token de terceros.</span><span class="sxs-lookup"><span data-stu-id="a49ed-118">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="a49ed-119">Lync Server 2013, Exchange Server y SharePoint Server tienen un servidor de tokens integrado que se puede usar para fines de autenticación entre sí.</span><span class="sxs-lookup"><span data-stu-id="a49ed-119">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="a49ed-120">Por ejemplo, Lync Server 2013 puede emitir y firmar un token de seguridad por sí mismo, y usar ese token para comunicarse con Exchange.</span><span class="sxs-lookup"><span data-stu-id="a49ed-120">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="a49ed-121">En este caso, no es necesario utilizar un servidor de token de terceros.</span><span class="sxs-lookup"><span data-stu-id="a49ed-121">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="a49ed-122">Lync Server 2013 admite los dos escenarios de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="a49ed-122">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="a49ed-123">Esto incluye la configuración de la autenticación de servidor a servidor entre los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a49ed-123">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="a49ed-124">Una instalación local de Lync Server 2013 y una instalación local de Exchange Server 2013, Exchange Server 2016 y/o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="a49ed-124">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="a49ed-125">Un par de componentes de Office (por ejemplo, entre Microsoft Exchange 365 y Microsoft Lync Server 365, o entre Microsoft Lync Server 365 y Microsoft SharePoint 365).</span><span class="sxs-lookup"><span data-stu-id="a49ed-125">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a49ed-126">La autenticación de servidor a servidor entre un servidor local y un componente de Microsoft 365 u Office 365 no es compatible con esta versión de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a49ed-126">Server-to-server authentication between an on-premises server and a Microsoft 365 or Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="a49ed-127">Entre otras cosas, esto significa que no se puede configurar la autenticación de servidor a servidor entre una instalación local de Lync Server 2013 y Microsoft Exchange 365.</span><span class="sxs-lookup"><span data-stu-id="a49ed-127">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="a49ed-128">Para obtener información detallada acerca de la autenticación de servidor a servidor, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) en la documentación de implementación u operaciones.</span><span class="sxs-lookup"><span data-stu-id="a49ed-128">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>
