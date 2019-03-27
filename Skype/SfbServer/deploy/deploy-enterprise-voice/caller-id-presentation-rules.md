---
title: Crear o modificar una regla de conversión para la presentación del identificador de autor de la llamada de Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumen: Obtenga información sobre cómo configurar el identificador de autor de la llamada mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: cfd6af9d31d165bc18f45439cf8925b0e47055d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890990"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="f132d-103">Crear o modificar una regla de conversión para la presentación del identificador de autor de la llamada de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="f132d-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="f132d-104">**Resumen:** Obtenga información sobre cómo configurar el identificador de autor de la llamada mediante el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f132d-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="f132d-105">Con Skype para Business Server, número de teléfono del receptor (es decir, el número de teléfono denominado) se puede traducir del formato E.164 al formato de marcado local que requiera el _mismo nivel del tronco_ (es decir, la puerta de enlace asociada, (exchange) central de conmutación PBX), o un tronco SIP).</span><span class="sxs-lookup"><span data-stu-id="f132d-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="f132d-106">Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f132d-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="f132d-107">Skype para Business Server también proporciona la opción de traducir también el número de teléfono de la persona que llama (es decir, el número de teléfono que el autor de la llamada está llamando desde) del formato E.164 a formato de marcado local requerido por el par de tronco.</span><span class="sxs-lookup"><span data-stu-id="f132d-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="f132d-108">Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.</span><span class="sxs-lookup"><span data-stu-id="f132d-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f132d-109">Para configurar el identificador de autor de la llamada mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="f132d-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f132d-110">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="f132d-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f132d-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="f132d-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="f132d-112">En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="f132d-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="f132d-113">Para configurar la presentación del identificador de llamada:</span><span class="sxs-lookup"><span data-stu-id="f132d-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="f132d-114">Para elegir una o varias reglas de una lista de todas las reglas de conversión disponibles en su implementación de Enterprise Voice, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="f132d-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f132d-115">En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f132d-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="f132d-116">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="f132d-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="f132d-117">Para obtener información detallada sobre cómo definir una nueva regla, consulte [Definición de reglas de conversión](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f132d-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="f132d-p105">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener más información, consulte  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="f132d-p105">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**. For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="f132d-p106">Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="f132d-p106">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**. For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="f132d-122">Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f132d-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="f132d-123">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="f132d-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


