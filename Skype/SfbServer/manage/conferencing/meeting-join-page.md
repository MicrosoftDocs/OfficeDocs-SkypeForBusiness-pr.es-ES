---
title: Configurar la página de combinación de reuniones en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: Aprenda a configurar la página de la combinación de reuniones en Skype empresarial Server.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818521"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="f8a04-103">Configurar la página de combinación de reuniones en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f8a04-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="f8a04-104">**Resumen:** Aprenda a configurar la página de la combinación de reuniones en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f8a04-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="f8a04-105">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la página de unirse a la reunión detecta si un cliente de Skype empresarial ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="f8a04-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="f8a04-106">Si un cliente ya está instalado, el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f8a04-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="f8a04-107">Si un cliente no está instalado, el cliente de Skype empresarial se abre de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f8a04-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="f8a04-108">Configurar la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="f8a04-108">Configure the meeting join page</span></span>

<span data-ttu-id="f8a04-109">Puede modificar el comportamiento de la página de la combinación de reuniones si desea permitir que los usuarios se unan a reuniones con otras versiones del cliente.</span><span class="sxs-lookup"><span data-stu-id="f8a04-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="f8a04-110">Estas opciones de configuración se han eliminado del panel de control de Skype empresarial Server, pero se configuran mediante el cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8a04-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="f8a04-111">**Conjunto de páginas de combinación de reuniones-parámetros de CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f8a04-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="f8a04-112">**Parámetro Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f8a04-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="f8a04-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f8a04-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8a04-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="f8a04-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="f8a04-115">Este parámetro ha quedado obsoleto para usarse con la versión local de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f8a04-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="f8a04-116">Si se establece en true, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Skype empresarial tendrán la oportunidad de unirse a la reunión mediante la aplicación de cliente actual.</span><span class="sxs-lookup"><span data-stu-id="f8a04-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="f8a04-117">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="f8a04-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="f8a04-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="f8a04-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="f8a04-119">Este parámetro ha quedado obsoleto para usarse con la versión local de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f8a04-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="f8a04-120">Si se establece en true, las opciones alternativas para unirse a una conferencia en línea se expanden y se muestran automáticamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f8a04-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="f8a04-121">Si se establece en falso (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f8a04-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

