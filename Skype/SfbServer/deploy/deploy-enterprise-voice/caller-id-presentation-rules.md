---
title: Crear o modificar una regla de traducción para la presentación del identificador de autor de la llamada en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Summary: Learn how to configure Caller ID by using the Skype for Business Server Control Panel.'
ms.openlocfilehash: 2ffe547927c9f4d6df16a06cc8c95dff9814fc7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113036"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="d8566-103">Crear o modificar una regla de traducción para la presentación del identificador de autor de la llamada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8566-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="d8566-104">**Resumen:** Obtenga información sobre cómo configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d8566-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="d8566-105">Con Skype Empresarial Server, el número de teléfono de la parte llamada (es decir, el número de teléfono llamado) se puede traducir del formato E.164 al formato de marcado local que requiere el tronco del mismo nivel  _(es_ decir, la puerta de enlace asociada, la central de conmutación de sucursal privada (PBX) o el tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="d8566-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="d8566-106">Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d8566-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="d8566-107">Skype Empresarial Server también le ofrece la opción de traducir también el número de teléfono de la persona que realiza la llamada (es decir, el número de teléfono desde el que llama el autor de la llamada) del formato E.164 al formato de marcado local que requiere el mismo nivel de tronco.</span><span class="sxs-lookup"><span data-stu-id="d8566-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="d8566-108">Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.</span><span class="sxs-lookup"><span data-stu-id="d8566-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d8566-109">Para configurar el identificador de llamada mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d8566-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d8566-110">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d8566-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d8566-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="d8566-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="d8566-112">En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="d8566-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="d8566-113">Para configurar la presentación del identificador de llamada:</span><span class="sxs-lookup"><span data-stu-id="d8566-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="d8566-114">Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d8566-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d8566-115">En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d8566-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="d8566-116">Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="d8566-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d8566-117">Para obtener más información sobre cómo definir una nueva regla, consulte  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d8566-117">For details about defining a new rule, see  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="d8566-118">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d8566-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="d8566-119">Para obtener más información, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) en la documentación referente a la implementación.</span><span class="sxs-lookup"><span data-stu-id="d8566-119">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

   - <span data-ttu-id="d8566-120">Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="d8566-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="d8566-121">Para obtener más información, consulte [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).</span><span class="sxs-lookup"><span data-stu-id="d8566-121">For details, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).</span></span>

   - <span data-ttu-id="d8566-122">Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="d8566-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="d8566-123">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas puedan entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="d8566-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>