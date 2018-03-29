---
title: Crear o modificar una regla de conversión para presentación del identificador de llamada en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Resumen: Conozca cómo configurar identificador utilizando el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: b5460558d621b04ca041bd540f9aba9d3a19bd45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="97cb5-103">Crear o modificar una regla de conversión para presentación del identificador de llamada en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="97cb5-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="97cb5-104">**Resumen:** Aprenda a configurar identificador mediante el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="97cb5-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="97cb5-105">Con Skype para Business Server, número de teléfono del receptor (es decir, el número de teléfono llamado) se pueden traducir en formato E.164 en el formato de marcado local requerido por el _interlocutor de tronco_ (es decir, la puerta de enlace asociada, private branch exchange ( PBX), o troncal SIP).</span><span class="sxs-lookup"><span data-stu-id="97cb5-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="97cb5-106">Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="97cb5-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>
  
<span data-ttu-id="97cb5-107">Skype para Business Server también tendrá la opción también traducir el número de teléfono de la persona que llama (es decir, el número de teléfono que el llamador está llamando desde) de formato E.164 para el formato de marcado local requerido por el interlocutor de tronco.</span><span class="sxs-lookup"><span data-stu-id="97cb5-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="97cb5-108">Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.</span><span class="sxs-lookup"><span data-stu-id="97cb5-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="97cb5-109">Para configurar el identificador de llamadas mediante Skype para Panel de Control de servidor de Business</span><span class="sxs-lookup"><span data-stu-id="97cb5-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="97cb5-110">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="97cb5-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="97cb5-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
    
3. <span data-ttu-id="97cb5-112">En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
4. <span data-ttu-id="97cb5-113">Para configurar la presentación del identificador de llamada:</span><span class="sxs-lookup"><span data-stu-id="97cb5-113">To configure caller ID presentation:</span></span>
    
   - <span data-ttu-id="97cb5-114">Para elegir una o más reglas en una lista de todas las reglas de traducción disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="97cb5-115">En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
   - <span data-ttu-id="97cb5-116">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="97cb5-117">Para obtener más información acerca de la definición de una nueva regla, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="97cb5-117">For details about defining a new rule, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="97cb5-118">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-118">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="97cb5-119">Para obtener más información, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="97cb5-119">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>
    
   - <span data-ttu-id="97cb5-120">Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-120">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="97cb5-121">Para obtener más información, consulte [Definición de las reglas de conversión](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span><span class="sxs-lookup"><span data-stu-id="97cb5-121">For details, see [Defining Translation Rules](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span> 
    
   - <span data-ttu-id="97cb5-122">Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="97cb5-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="97cb5-123">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="97cb5-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span> 
  

