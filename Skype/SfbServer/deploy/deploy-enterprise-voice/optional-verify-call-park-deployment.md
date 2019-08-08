---
title: Faculta Comprobar la implementación del parque de llamadas en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobar la implementación de el parque de llamadas en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: d698bf46f0a36a86729856c388fde09514288253
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240441"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Faculta Comprobar la implementación del parque de llamadas en Skype empresarial
 
Comprobar la implementación de el parque de llamadas en la telefonía IP empresarial de Skype empresarial. 
  
Después de instalar y configurar el parque de llamadas, debe comprobar la configuración para asegurarse de que el aparcamiento y la recuperación de llamadas funciona según lo esperado. Como mínimo, compruebe los elementos siguientes:
  
- Llamar a un usuario que tiene habilitada la opción estacionamiento de llamadas y hacer que el usuario aparca la llamada.
    
    > [!NOTE]
    > Si habilitó el parque de llamadas en la Directiva de voz justo antes de realizar esta prueba, el usuario que está aparcando la llamada necesita cerrar la sesión de Skype empresarial y, a continuación, volver a iniciarla, para poder ver la opción estacionamiento de llamadas en la lista de llamadas de transferencia. 
  
- Marque el número de órbita para recuperar la llamada.
    
- Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.
    

