---
title: 'Lync Server 2013: presentación de identificación de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afe4682250bd6065ba368d7812dfdcd5626042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="46834-102">Presentación de la identificación de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46834-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46834-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="46834-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="46834-104">Con Lync Server 2010, el número de teléfono de la persona que se llama (es decir, el número de teléfono llamado) se puede traducir desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco del SIP).</span><span class="sxs-lookup"><span data-stu-id="46834-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="46834-105">Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="46834-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="46834-106">Lync Server 2013 introduce la opción de traducir el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) desde E. 164 formato al formato de marcado local requerido por el interlocutor troncal.</span><span class="sxs-lookup"><span data-stu-id="46834-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="46834-107">Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.</span><span class="sxs-lookup"><span data-stu-id="46834-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="46834-108">**Para configurar la identificación de llamadas mediante el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="46834-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="46834-109">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="46834-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="46834-110">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="46834-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="46834-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46834-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="46834-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46834-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="46834-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="46834-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="46834-114">En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="46834-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="46834-115">Para configurar la presentación del identificador de llamada:</span><span class="sxs-lookup"><span data-stu-id="46834-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="46834-116">Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="46834-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46834-117">En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46834-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="46834-118">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="46834-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="46834-119">Para obtener más información sobre cómo definir una nueva regla, vea [definir reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="46834-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46834-120">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="46834-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="46834-121">Para obtener información detallada, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="46834-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46834-122">Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="46834-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="46834-123">Para obtener más información, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="46834-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="46834-124">Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="46834-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="46834-125">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="46834-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

