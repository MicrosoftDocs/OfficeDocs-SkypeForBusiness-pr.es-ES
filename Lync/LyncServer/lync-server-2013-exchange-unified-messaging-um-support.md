---
title: 'Lync Server 2013: compatibilidad con mensajería unificada (MU) de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac42e46bf92e7fa170ee3dff059edc1b5871aafd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533127"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="f676e-102">Compatibilidad con mensajería unificada (MU) de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f676e-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f676e-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f676e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f676e-104">Lync Server 2013 admite la integración con la mensajería unificada (UM) de Exchange para combinar la mensajería de voz y la mensajería de correo electrónico en una única infraestructura de mensajería.</span><span class="sxs-lookup"><span data-stu-id="f676e-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="f676e-105">En Exchange 2013, la mensajería unificada de Exchange consta del servicio MU de Exchange, que se instala y se ejecuta en el servidor de buzones de correo, y el enrutador de llamadas de mensajería unificada, que se instala y se ejecuta en el servidor de acceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="f676e-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="f676e-106">Para las implementaciones de Lync Server 2013 Enterprise Voice, la mensajería UNIFICAda de Exchange combina la mensajería de voz y la mensajería de correo electrónico en un solo almacén al que se puede tener acceso desde un teléfono (es decir, Outlook Voice Access) o un equipo.</span><span class="sxs-lookup"><span data-stu-id="f676e-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="f676e-107">La mensajería unificada de Exchange y Lync Server 2013 funcionan de forma conjunta para proporcionar servicios de contestador automático, Outlook Voice Access y operador automático a los usuarios de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f676e-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="f676e-108">Además de la compatibilidad para la integración con implementaciones locales de mensajería unificada de Exchange, Lync Server 2013 admite la integración con la mensajería unificada de Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="f676e-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="f676e-109">Esto le permite proporcionar mensajería de voz a sus usuarios si los migra, en su totalidad o en parte, a un proveedor de servicios de Exchange hospedado como Microsoft Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f676e-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="f676e-110">Lync Server 2013 admite las siguientes versiones:</span><span class="sxs-lookup"><span data-stu-id="f676e-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="f676e-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="f676e-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="f676e-112">Microsoft Exchange Server 2010 (obligatorio) o con el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="f676e-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="f676e-113">Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obligatorio) o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="f676e-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="f676e-114">No puede combinar mensajería unificada de Exchange con Lync Server 2013 o una base de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f676e-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="f676e-115">Puede instalar la mensajería unificada de Exchange y Lync Server 2013 en bosques independientes.</span><span class="sxs-lookup"><span data-stu-id="f676e-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f676e-116">Es posible que no se requiera la mensajería unificada de Exchange para implementaciones de Enterprise Voice que tengan implementado un sistema PBX, ya que el sistema PBX puede continuar proporcionando correo de voz y servicios relacionados a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f676e-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="f676e-117">Si finalmente retira la PBX (por ejemplo, si implementa un enlace troncal SIP para la conectividad de red telefónica conmutada (RTC)), debe volver a configurar la mensajería unificada de Exchange para proporcionar correo de voz a los usuarios que usaron previamente el sistema de correo de voz PBX.</span><span class="sxs-lookup"><span data-stu-id="f676e-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f676e-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f676e-118">In This Section</span></span>

  - [<span data-ttu-id="f676e-119">Componentes y topologías para mensajería unificada local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f676e-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="f676e-120">Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f676e-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

