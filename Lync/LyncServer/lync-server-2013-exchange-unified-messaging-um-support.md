---
title: 'Lync Server 2013: Compatibilidad de mensajería unificada (UM) de Exchange'
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
ms.openlocfilehash: 8925bd8a07693800c49ff2d818d3677b33452b97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="737dd-102">Compatibilidad de mensajería unificada (UM) de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="737dd-102">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="737dd-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="737dd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="737dd-104">Lync Server 2013 admite la integración con mensajería unificada de Exchange (UM) para combinar la mensajería de voz y la mensajería de correo electrónico en una sola infraestructura de mensajería.</span><span class="sxs-lookup"><span data-stu-id="737dd-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="737dd-105">En Exchange 2013, la mensajería unificada de Exchange consta del servicio MU de Exchange, que se instala y se ejecuta en el servidor de buzón de correo, y el enrutador de llamadas de mensajería unificada, que se instala y se ejecuta en el servidor de acceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="737dd-105">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="737dd-106">Para implementaciones de Lync Server 2013 Enterprise Voice, la mensajería UNIFICAda de Exchange combina la mensajería de voz y la mensajería de correo electrónico en un solo almacén accesible desde un teléfono (es decir, Outlook Voice Access) o un equipo.</span><span class="sxs-lookup"><span data-stu-id="737dd-106">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="737dd-107">La mensajería unificada de Exchange y Lync Server 2013 funcionan de forma conjunta para proporcionar respuesta de llamada, Outlook Voice Access y los servicios de operador automático a los usuarios de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="737dd-107">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="737dd-108">Además de la compatibilidad para la integración con implementaciones locales de la mensajería unificada de Exchange, Lync Server 2013 admite la integración con mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="737dd-108">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="737dd-109">Esto le permite proporcionar mensajería de voz a los usuarios si migra algunos o todos a un proveedor de servicios de Exchange hospedado como Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="737dd-109">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="737dd-110">Lync Server 2013 admite las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="737dd-110">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="737dd-111">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="737dd-111">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="737dd-112">Microsoft Exchange Server 2010 (obligatorio) o con el Service Pack más reciente (recomendado)</span><span class="sxs-lookup"><span data-stu-id="737dd-112">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="737dd-113">Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obligatorio) o el Service Pack más reciente (recomendado)</span><span class="sxs-lookup"><span data-stu-id="737dd-113">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="737dd-114">No puede Collocate mensajería unificada de Exchange con Lync Server 2013 o una base de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="737dd-114">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="737dd-115">Puede instalar la mensajería unificada de Exchange y Lync Server 2013 en bosques diferentes.</span><span class="sxs-lookup"><span data-stu-id="737dd-115">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="737dd-116">Es posible que no se necesite la mensajería unificada de Exchange para implementaciones de telefonía IP con una PBX implementada, porque la PBX puede seguir proporcionando correo de voz y servicios relacionados a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="737dd-116">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="737dd-117">Si finalmente retira el sistema PBX (por ejemplo, si implementa la configuración de troncal de SIP para conectividad de red telefónica conmutada (RTC)), debe volver a configurar la mensajería unificada de Exchange para proporcionar el correo de voz a los usuarios que antes usaban el sistema de correo de voz PBX.</span><span class="sxs-lookup"><span data-stu-id="737dd-117">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="737dd-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="737dd-118">In This Section</span></span>

  - [<span data-ttu-id="737dd-119">Componentes y topologías para mensajería unificada local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="737dd-119">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="737dd-120">Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="737dd-120">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

