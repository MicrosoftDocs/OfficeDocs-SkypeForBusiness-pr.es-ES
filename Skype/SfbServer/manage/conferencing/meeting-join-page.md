---
title: Configurar la página de participación en la reunión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: obtenga información sobre cómo configurar la página de participación en la reunión en Skype Empresarial Server.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828040"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="ec8a8-103">Configurar la página de participación en la reunión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ec8a8-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="ec8a8-104">**Resumen:** Obtenga información sobre cómo configurar la página de participación en la reunión en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="ec8a8-105">Cuando un usuario hace clic en un vínculo de reunión en una solicitud de reunión, la página de participación en la reunión detecta si un cliente de Skype Empresarial ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="ec8a8-106">Si hay uno instalado, el cliente se abre y se une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="ec8a8-107">Si un cliente no está instalado, se abre de forma predeterminada el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="ec8a8-108">Configurar la página para unirse a la reunión</span><span class="sxs-lookup"><span data-stu-id="ec8a8-108">Configure the meeting join page</span></span>

<span data-ttu-id="ec8a8-109">Puede modificar el comportamiento de la página de participación en la reunión si desea permitir a los usuarios unirse a reuniones con otras versiones del cliente.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="ec8a8-110">Estas opciones de configuración se han quitado del Panel de control de Skype Empresarial Server, pero se configuran con el cmdlet Set-CsWebServiceConfiguration configuración.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="ec8a8-111">**Parámetros de la página de participación Set-CsWebServiceConfiguration reunión**</span><span class="sxs-lookup"><span data-stu-id="ec8a8-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="ec8a8-112">**Parámetro Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ec8a8-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="ec8a8-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ec8a8-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ec8a8-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="ec8a8-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="ec8a8-115">Este parámetro ha quedado obsoleto para su uso con la versión local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="ec8a8-116">Si se establece en True, los usuarios que se unan a una reunión mediante una aplicación cliente que no sea Skype Empresarial tendrán la oportunidad de unirse a la reunión mediante su aplicación cliente actual.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="ec8a8-117">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="ec8a8-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="ec8a8-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="ec8a8-119">Este parámetro ha quedado obsoleto para su uso con la versión local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="ec8a8-120">Si se establece en True, las opciones alternativas para unirse a una conferencia en línea se expanden automáticamente y se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="ec8a8-121">Si se establece en False (el valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ec8a8-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

