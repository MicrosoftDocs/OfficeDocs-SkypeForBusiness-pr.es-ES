---
title: 'Lync Server 2013: Configurar planes de marcado para las conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11424148db609fa8225b6c98d1de52fa360eb044
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="c6bf4-102">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6bf4-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6bf4-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c6bf4-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c6bf4-104">Al implementar la conferencia de acceso telefónico local, tiene que crear o modificar uno o más planes de marcado para enrutar números de teléfono de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="c6bf4-105">Asegúrese de que al menos una regla de normalización de cada plan de marcado convierte las extensiones telefónicas en números de teléfono completos en formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="c6bf4-106">Los usuarios de la conferencia de acceso telefónico local se unen a las conferencias como usuarios de empresa autenticados al escribir su número de identificación personal (PIN) y su número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="c6bf4-107">Necesita una regla de normalización para convertir las extensiones en números de teléfono completos, de modo que los usuarios puedan autenticarse cuando solo introduzcan una extensión telefónica.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="c6bf4-108">Para configurar planes de marcado para conferencias de acceso telefónico local, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6bf4-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="c6bf4-109">Tanto si implementa la Telefonía IP empresarial como si no, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y para garantizar que una regla de normalización convierta de forma precisa los números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="c6bf4-110">Para obtener instrucciones detalladas, vea [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c6bf4-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="c6bf4-111">Si no implementó la Telefonía IP empresarial, cree planes de marcado para los números de acceso a conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="c6bf4-112">Recuerde incluir una región de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="c6bf4-113">Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c6bf4-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="c6bf4-114">Si ha implementado la Telefonía IP empresarial, modifique los planes de marcado de la Telefonía IP empresarial según sea necesario para incluir regiones y usar las reglas de normalización pertinentes para los números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="c6bf4-115">Para obtener instrucciones detalladas, vea [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c6bf4-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="c6bf4-116">También puede crear planes de marcado dedicados que solo se usarán para números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="c6bf4-117">Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c6bf4-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="c6bf4-118">Para obtener más información acerca de las regiones de planeación, consulte [requisitos de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c6bf4-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6bf4-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c6bf4-119">In This Section</span></span>

  - [<span data-ttu-id="c6bf4-120">Ver información de un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6bf4-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="c6bf4-121">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6bf4-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="c6bf4-122">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6bf4-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="c6bf4-123">Definir las reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6bf4-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

