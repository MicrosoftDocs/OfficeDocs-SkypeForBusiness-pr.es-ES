---
title: 'Lync Server 2013: integración con Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489c5023ab995700762fa5e19ba361df1b49a6b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="44f9e-102">Integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44f9e-103">_**Última modificación del tema:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="44f9e-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="44f9e-104">Exchange y Lync Server tienen un historial de integración y compatibilidad prolongado.</span><span class="sxs-lookup"><span data-stu-id="44f9e-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="44f9e-105">Esta integración se hace patente sobre todo en sus respectivas aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="44f9e-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="44f9e-106">Por ejemplo, se puede informar de la información de presencia de Lync en Microsoft Outlook; de forma similar, Lync puede usar el calendario de Outlook para actualizar automáticamente esa información de presencia.</span><span class="sxs-lookup"><span data-stu-id="44f9e-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="44f9e-107">(Por ejemplo, Lync puede cambiar su estado a ocupado cada vez que el calendario muestre que tiene una reunión programada). Aunque no es necesario ejecutar Exchange para ejecutar Lync Server (o viceversa), hay muy poca duda de que usar los dos productos juntos epitomizes la definición del término "Better Together".</span><span class="sxs-lookup"><span data-stu-id="44f9e-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="44f9e-108">Esto es especialmente cierto con el lanzamiento de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44f9e-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="44f9e-109">Además de las características, como la mensajería unificada y la mensajería instantánea y la presencia, que se encuentran en Microsoft Exchange Server 2010 y Microsoft Lync Server 2010, las versiones 2013 de los productos de servidor incluyen varias funciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="44f9e-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="44f9e-110">Entre ellas, se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="44f9e-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="44f9e-111">**Integración con el archivado de Lync**.</span><span class="sxs-lookup"><span data-stu-id="44f9e-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="44f9e-112">En Lync Server 2013 los administradores siguen teniendo la opción de archivar las transcripciones de mensajería instantánea y de las conferencias web en SQL Server (de la misma manera que estas transcripciones se archivaron en Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="44f9e-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="44f9e-113">Sin embargo, de manera alternativa, los administradores pueden elegir que las transcripciones se archiven en Exchange 2013, almacenando dichas transcripciones en los buzones de usuario individuales de la misma forma en que Exchange archiva las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="44f9e-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="44f9e-114">Esto significa que un único repositorio para todas las comunicaciones electrónicas (tanto de Exchange como de Lync Server) facilita en gran medida la búsqueda y recuperación de esas comunicaciones archivadas en caso de que surjan necesidades.</span><span class="sxs-lookup"><span data-stu-id="44f9e-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="44f9e-115">**Almacén de contactos unificado**.</span><span class="sxs-lookup"><span data-stu-id="44f9e-115">**Unified Contact Store**.</span></span> <span data-ttu-id="44f9e-116">En Lync Server 2010, los usuarios tenían que mantener listas de contactos independientes en Outlook y Lync; de hecho, para asegurarse de que tenía los mismos contactos disponibles en ambos productos, tenía que mantener listas de contactos duplicadas, una para Outlook y otra para Lync.</span><span class="sxs-lookup"><span data-stu-id="44f9e-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="44f9e-117">Sin embargo, con Lync Server 2013, los contactos de usuario se pueden almacenar en Exchange 2013 y en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="44f9e-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="44f9e-118">Usar un solo almacén de contactos permite a los usuarios mantener un solo conjunto de contactos, con el mismo conjunto de contactos disponible en Lync 2013, Outlook 2013 y Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="44f9e-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="44f9e-119">**Programación de reuniones de Lync desde OWA**.</span><span class="sxs-lookup"><span data-stu-id="44f9e-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="44f9e-120">Con Lync Server 2013 y la integración de Exchange 2013, los usuarios pueden programar reuniones de Lync desde Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="44f9e-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="44f9e-121">**Fotografías de alta resolución**.</span><span class="sxs-lookup"><span data-stu-id="44f9e-121">**High resolution photos**.</span></span> <span data-ttu-id="44f9e-122">Lync 2010 solo podría mostrar pequeñas fotos de sus contactos; Esto se debe a que esas fotos se almacenaron en Active Directory y Active Directory impone un límite de 48 píxeles por 48 píxeles en las fotos almacenadas.</span><span class="sxs-lookup"><span data-stu-id="44f9e-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="44f9e-123">Sin embargo, con Lync Server 2013, las fotos se pueden almacenar en Microsoft Exchange; que permite fotos de alta resolución tan grandes como 648 píxeles por 648 píxeles.</span><span class="sxs-lookup"><span data-stu-id="44f9e-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="44f9e-124">Como cabría esperar, se ha actualizado Lync 2013 para permitir que se muestren estas fotografías de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="44f9e-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="44f9e-125">Tenga en cuenta que estas nuevas características requieren el uso de Lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="44f9e-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="44f9e-126">Además, los usuarios que esperan sacar el máximo partido de estas nuevas funciones deben tener cuentas en Lync Server 2013 y en Exchange 2013, y deben usar las versiones más recientes del software cliente (por ejemplo, Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="44f9e-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="44f9e-127">Por ejemplo, el almacén de contactos unificado no está disponible para los usuarios que se han hospedado en Lync Server 2010; del mismo modo, las fotos de alta resolución no se pueden mostrar en Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="44f9e-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="44f9e-128">En esta documentación se proporciona información sobre la integración de Lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="44f9e-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="44f9e-129">incluye información paso a paso sobre cómo habilitar nuevas características, como la integración de archivado y el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="44f9e-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="44f9e-130">Esta documentación no es una descripción de la instalación y la configuración inicial de estos dos productos.</span><span class="sxs-lookup"><span data-stu-id="44f9e-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="44f9e-131">Para obtener más información sobre la implementación de Lync Server 2013, consulte el centro técnico [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)de lync Server 2013 en.</span><span class="sxs-lookup"><span data-stu-id="44f9e-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="44f9e-132">Para obtener más información sobre la implementación de Exchange 2013, consulte el Exchange [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)2013 Tech Center en.</span><span class="sxs-lookup"><span data-stu-id="44f9e-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44f9e-133">En esta sección</span><span class="sxs-lookup"><span data-stu-id="44f9e-133">In This Section</span></span>

[<span data-ttu-id="44f9e-134">Requisitos previos para integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="44f9e-135">Configuración de aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="44f9e-136">Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="44f9e-137">Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="44f9e-138">Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="44f9e-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="44f9e-139">Configuración del uso de fotos de alta resolución en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="44f9e-140">Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="44f9e-141">Integración de Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="44f9e-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

