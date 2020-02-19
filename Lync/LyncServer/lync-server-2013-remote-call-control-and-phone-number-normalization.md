---
title: 'Lync Server 2013: control remoto de llamadas y normalización de números de teléfono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ddf66011a992c9ed306a1fb6652f63133ecb123
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="1d1af-102">Control remoto de llamadas y normalización de números de teléfono en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d1af-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d1af-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="1d1af-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="1d1af-104">Los clientes de Lync descargan reglas de normalización de números de teléfono como parte de la descarga de archivos del servicio de libreta de direcciones (ABS).</span><span class="sxs-lookup"><span data-stu-id="1d1af-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="1d1af-105">En los escenarios de control remoto de llamadas, las reglas de normalización de número de teléfono del servicio de libreta de direcciones se aplican a las llamadas entrantes y salientes del control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1d1af-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="1d1af-106">Para las llamadas entrantes a un usuario habilitado para el control remoto de llamadas, el número de teléfono del autor de la llamada se normaliza primero al formato E. 164 mediante la puerta de enlace SIP/CSTA o central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="1d1af-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="1d1af-107">Cuando Lync Server 2013 recibe la llamada de la puerta de enlace, realiza una búsqueda inversa de números (RNL) en el número de teléfono del autor de la llamada en relación con el número normalizado de la lista de contactos de Microsoft Office Outlook del destinatario de la llamada o la lista global de direcciones (GAL) almacenada en el servicio de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="1d1af-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="1d1af-108">Si la búsqueda de números inversas encuentra una coincidencia, el autor de la llamada se identifica por su nombre en la notificación de llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="1d1af-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="1d1af-109">Para las llamadas de control remoto de llamadas salientes, Lync aplica las reglas de normalización de números de teléfono del servicio de libreta de direcciones al número marcado antes de enrutar la llamada a la puerta de enlace SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="1d1af-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="1d1af-110">Para obtener información detallada sobre cómo crear reglas de normalización de números de teléfono para el control remoto de llamadas, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="1d1af-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="1d1af-111">Migración de reglas de normalización de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="1d1af-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="1d1af-112">Si va a migrar usuarios habilitados previamente para control remoto de llamadas, consulte los siguientes temas en la documentación sobre migración:</span><span class="sxs-lookup"><span data-stu-id="1d1af-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="1d1af-113">Para Lync Server 2010, consulte [Migrate Address Book](migrate-address-book.md) en la documentación de migración.</span><span class="sxs-lookup"><span data-stu-id="1d1af-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="1d1af-114">Para Communications Server 2007 R2, consulte [Migrate Address Book](migrate-address-book_1.md) en la documentación de migración.</span><span class="sxs-lookup"><span data-stu-id="1d1af-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

