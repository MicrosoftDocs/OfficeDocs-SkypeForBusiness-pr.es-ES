---
title: Configuración de la reunión de la página de participación en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: Obtenga información sobre cómo configurar la reunión página de participación en Skype para Business Server.'
ms.openlocfilehash: 7574dee341e0226a6a6e2ee8c77cdfb2353beb5a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977617"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="027c7-103">Configuración de la reunión de la página de participación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="027c7-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="027c7-104">**Resumen:** Obtenga información sobre cómo configurar la reunión página de participación en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="027c7-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="027c7-105">Cuando un usuario hace clic en un vínculo de la reunión en una convocatoria de reunión, la reunión de la página de participación detecta si un Skype para Business client ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="027c7-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="027c7-106">Si un cliente ya está instalado, el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="027c7-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="027c7-107">Si un cliente no está instalado, de forma predeterminada la Skype para la empresa cliente se abre.</span><span class="sxs-lookup"><span data-stu-id="027c7-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="027c7-108">Configuración de la reunión de la página de participación</span><span class="sxs-lookup"><span data-stu-id="027c7-108">Configure the meeting join page</span></span>

<span data-ttu-id="027c7-109">Puede modificar el comportamiento de la participación en reuniones de página si desea permitir que los usuarios puedan unirse a reuniones con otras versiones del cliente.</span><span class="sxs-lookup"><span data-stu-id="027c7-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="027c7-110">Estas opciones de configuración se han quitado de la Skype para el Panel de Control de servidor empresarial, pero configurarlas mediante el cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="027c7-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="027c7-111">**Parámetros de Set-CsWebServiceConfiguration de página unirse a la reunión**</span><span class="sxs-lookup"><span data-stu-id="027c7-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="027c7-112">**Parámetro SET-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="027c7-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="027c7-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="027c7-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="027c7-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="027c7-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="027c7-115">Este parámetro ha quedado obsoleto para su uso con la versión local de Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="027c7-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="027c7-116">Si establecido en True, los usuarios unirse a una reunión mediante el uso de una aplicación cliente distinto de Skype para la empresa se le dará la oportunidad de unirse a la reunión mediante el uso de su aplicación de cliente actual.</span><span class="sxs-lookup"><span data-stu-id="027c7-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="027c7-117">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="027c7-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="027c7-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="027c7-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="027c7-119">Este parámetro ha quedado obsoleto para su uso con la versión local de Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="027c7-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="027c7-120">Si se establece en True, alternativa opciones para unirse a una conferencia en línea se amplían automáticamente y se muestra a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="027c7-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="027c7-121">Si se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones para sí mismos.</span><span class="sxs-lookup"><span data-stu-id="027c7-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

