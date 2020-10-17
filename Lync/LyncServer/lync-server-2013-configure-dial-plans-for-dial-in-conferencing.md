---
title: 'Lync Server 2013: configurar planes de marcado para conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4178d443d8577a9a141cbdd5bbeee05856ae6b40
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504767"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="922c5-102">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922c5-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="922c5-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="922c5-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="922c5-104">Al implementar la Conferencia de acceso telefónico local, debe crear o modificar uno o más planes de marcado para enrutar números de teléfono de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="922c5-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="922c5-105">Asegúrese de que al menos una regla de normalización en cada plan de marcado convierte las extensiones telefónicas en números de teléfono completos en formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="922c5-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="922c5-106">Los usuarios de conferencias de acceso telefónico local se unen a conferencias como usuarios empresariales autenticados introduciendo su número de identificación personal (PIN) y su número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="922c5-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="922c5-107">Necesita una regla de normalización para convertir las extensiones en números de teléfono completos para que los usuarios se puedan autenticar cuando entren solo una extensión telefónica.</span><span class="sxs-lookup"><span data-stu-id="922c5-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="922c5-108">Para configurar planes de marcado para las conferencias de acceso telefónico local, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="922c5-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="922c5-109">Independientemente de si implementa la telefonía IP empresarial, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y asegurarse de que una regla de normalización convierta con precisión los números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="922c5-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="922c5-110">Para obtener instrucciones detalladas, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="922c5-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="922c5-111">Si no implementó la telefonía IP empresarial, cree planes de marcado para los números de acceso de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="922c5-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="922c5-112">Asegúrese de incluir una región de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="922c5-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="922c5-113">Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="922c5-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="922c5-114">Si ha implementado Enterprise Voice, modifique los planes de marcado de Enterprise Voice según sea necesario para incluir regiones y usar las reglas de normalización adecuadas para los números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="922c5-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="922c5-115">Para obtener instrucciones detalladas, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="922c5-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="922c5-116">También puede crear planes de marcado dedicados que solo se usan para números de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="922c5-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="922c5-117">Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="922c5-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="922c5-118">Para obtener más información sobre las regiones de planeación, consulte [requisitos de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="922c5-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="922c5-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="922c5-119">In This Section</span></span>

  - [<span data-ttu-id="922c5-120">Ver información de plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922c5-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="922c5-121">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922c5-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="922c5-122">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922c5-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="922c5-123">Definición de reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922c5-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

