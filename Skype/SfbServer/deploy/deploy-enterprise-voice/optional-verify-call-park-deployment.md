---
title: (Opcional) Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial
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
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830900"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="a72b5-103">(Opcional) Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a72b5-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="a72b5-104">Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a72b5-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a72b5-105">Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que el estacionamiento y la recuperación de llamadas funcionen según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="a72b5-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="a72b5-106">Como mínimo, compruebe los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a72b5-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="a72b5-107">Llame a un usuario que tenga habilitado el estacionamiento de llamadas y haga que estacione la llamada.</span><span class="sxs-lookup"><span data-stu-id="a72b5-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a72b5-108">Si habilitó el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que estacione la llamada debe cerrar sesión en Skype Empresarial y, a continuación, volver a iniciarla para poder ver la opción Estacionamiento de llamadas en la lista de llamadas de transferencia.</span><span class="sxs-lookup"><span data-stu-id="a72b5-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="a72b5-109">Marque el número de órbita para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="a72b5-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="a72b5-p102">Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="a72b5-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

