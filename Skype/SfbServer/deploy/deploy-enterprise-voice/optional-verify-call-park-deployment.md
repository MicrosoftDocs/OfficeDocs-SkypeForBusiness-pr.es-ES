---
title: (Opcional) Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobación de la implementación del parque de llamada en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a><span data-ttu-id="73f3e-103">(Opcional) Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="73f3e-103">(Optional) Verify Call Park deployment in Skype for Business 2015</span></span>
 
<span data-ttu-id="73f3e-104">Comprobación de la implementación del parque de llamada en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="73f3e-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="73f3e-105">Después de instalar y configurar llamada Park, debe comprobar la configuración para asegurarse de que el estacionamiento y recuperar llamadas funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="73f3e-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="73f3e-106">Como mínimo, compruebe los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="73f3e-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="73f3e-107">Llamar a un usuario que tiene habilitado el parque de llamada y tener el parque de usuario la llamada.</span><span class="sxs-lookup"><span data-stu-id="73f3e-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="73f3e-108">Si habilitó llamada Park en directiva de voz justo antes de realizar esta prueba, el usuario que es la llamada de estacionamiento debe cerrar la sesión de Skype para el negocio y, a continuación, iniciar sesión en, podrá ver la opción llamada Park en la transferencia de la lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="73f3e-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="73f3e-109">Marque el número de órbita para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="73f3e-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="73f3e-p102">Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="73f3e-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

