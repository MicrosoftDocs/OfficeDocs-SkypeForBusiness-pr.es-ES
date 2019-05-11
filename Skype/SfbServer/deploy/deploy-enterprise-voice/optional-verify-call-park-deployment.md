---
title: (Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobación de la implementación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: da53d351acef3eb2fc7fcc1b59e24a83d0cb2495
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894671"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="968ca-103">(Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="968ca-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="968ca-104">Comprobación de la implementación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="968ca-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="968ca-105">Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que de estacionamiento y recuperación de llamadas funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="968ca-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="968ca-106">Como mínimo, compruebe los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="968ca-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="968ca-107">Llamar a un usuario que tenga habilitado estacionamiento de llamadas y haga que Estacione la llamada.</span><span class="sxs-lookup"><span data-stu-id="968ca-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="968ca-108">Si se habilita el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que es estacionar la llamada debe cerrar la sesión de Skype para la empresa y, a continuación, inicie sesión en, podrá ver la opción de estacionamiento de llamadas en la transferencia de la lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="968ca-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="968ca-109">Marque el número de órbita para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="968ca-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="968ca-p102">Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="968ca-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

