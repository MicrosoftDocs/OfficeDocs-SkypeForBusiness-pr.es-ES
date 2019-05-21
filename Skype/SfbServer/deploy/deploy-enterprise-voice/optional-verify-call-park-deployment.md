---
title: Faculta Comprobar la implementación del parque de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobar la implementación de el parque de llamadas en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292846"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="1ba3f-103">Faculta Comprobar la implementación del parque de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="1ba3f-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="1ba3f-104">Comprobar la implementación de el parque de llamadas en la telefonía IP empresarial de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="1ba3f-105">Después de instalar y configurar el parque de llamadas, debe comprobar la configuración para asegurarse de que el aparcamiento y la recuperación de llamadas funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="1ba3f-106">Como mínimo, compruebe los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ba3f-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="1ba3f-107">Llamar a un usuario que tiene habilitada la opción estacionamiento de llamadas y hacer que el usuario aparca la llamada.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ba3f-108">Si habilitó el parque de llamadas en la Directiva de voz justo antes de realizar esta prueba, el usuario que está aparcando la llamada necesita cerrar la sesión de Skype empresarial y, a continuación, volver a iniciarla, para poder ver la opción estacionamiento de llamadas en la lista de llamadas de transferencia.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="1ba3f-109">Marque el número de órbita para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="1ba3f-p102">Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

