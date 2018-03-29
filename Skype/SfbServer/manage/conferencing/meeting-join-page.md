---
title: Configurar la reunión página join en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumen: Aprender a configurar la reunión página join en Skype para Business Server 2015.'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a><span data-ttu-id="438ea-103">Configurar la reunión página join en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="438ea-103">Configure the meeting join page in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="438ea-104">**Resumen:** Aprenda a configurar la reunión página join en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="438ea-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="438ea-105">Cuando un usuario hace clic en un vínculo de reunión en una convocatoria de reunión, la reunión página combinación detecta si un Skype para Business client ya está instalado en el equipo del usuario.</span><span class="sxs-lookup"><span data-stu-id="438ea-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="438ea-106">Si un cliente ya está instalado, el cliente se abre y une a la reunión.</span><span class="sxs-lookup"><span data-stu-id="438ea-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="438ea-107">Si un cliente no está instalado, de forma predeterminada la versión 2015 de Skype para Business client abre.</span><span class="sxs-lookup"><span data-stu-id="438ea-107">If a client is not installed, by default the 2015 version of Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="438ea-108">Configurar la reunión página de combinación</span><span class="sxs-lookup"><span data-stu-id="438ea-108">Configure the meeting join page</span></span>

<span data-ttu-id="438ea-109">Puede modificar el comportamiento de la combinación de reunión si desea permitir que los usuarios puedan unirse a reuniones con otras versiones del cliente de la página.</span><span class="sxs-lookup"><span data-stu-id="438ea-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="438ea-110">Estas opciones de configuración se han quitado de la Skype para Panel de Control de servidor empresarial, pero configurarlos mediante el cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="438ea-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="438ea-111">**Parámetros de CsWebServiceConfiguration de conjunto página unirse a reuniones**</span><span class="sxs-lookup"><span data-stu-id="438ea-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="438ea-112">**Parámetro del conjunto de CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="438ea-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="438ea-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="438ea-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="438ea-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="438ea-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="438ea-115">Este parámetro está desusado para su uso con la versión local de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="438ea-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server 2015.</span></span>  <br/> <span data-ttu-id="438ea-116">Si se establece en True, unirse a una reunión mediante una aplicación de cliente distinto de Skype para empresas se ofrecerá la oportunidad de incorporarse a la reunión mediante su aplicación de cliente actual.</span><span class="sxs-lookup"><span data-stu-id="438ea-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="438ea-117">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="438ea-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="438ea-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="438ea-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="438ea-119">Este parámetro está desusado para su uso con la versión local de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="438ea-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server 2015.</span></span>  <br/>  <span data-ttu-id="438ea-120">Si se establece en True, alternativo opciones para unirse a una conferencia en línea se expande y muestra a los usuarios automáticamente.</span><span class="sxs-lookup"><span data-stu-id="438ea-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="438ea-121">Si se establece en False (valor predeterminado), estas opciones estarán disponibles, pero el usuario tendrá que mostrar la lista de opciones por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="438ea-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

