---
title: (Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobación de la implementación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 514c82590d56a2de16ca31cc892032afe5e7a34c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895100"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="33c10-103">(Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="33c10-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="33c10-104">Comprobación de la implementación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="33c10-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="33c10-105">Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que de estacionamiento y recuperación de llamadas funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="33c10-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="33c10-106">Como mínimo, compruebe los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="33c10-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="33c10-107">Llamar a un usuario que tenga habilitado estacionamiento de llamadas y haga que Estacione la llamada.</span><span class="sxs-lookup"><span data-stu-id="33c10-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33c10-108">Si se habilita el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que es estacionar la llamada debe cerrar la sesión de Skype para la empresa y, a continuación, inicie sesión en, podrá ver la opción de estacionamiento de llamadas en la transferencia de la lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="33c10-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="33c10-109">Marque el número de órbita para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="33c10-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="33c10-p102">Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="33c10-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

