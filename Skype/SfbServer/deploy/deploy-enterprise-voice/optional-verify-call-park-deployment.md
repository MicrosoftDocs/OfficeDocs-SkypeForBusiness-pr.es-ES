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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225635"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa
 
Comprobación de la implementación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice. 
  
Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que de estacionamiento y recuperación de llamadas funciona según lo previsto. Como mínimo, compruebe los elementos siguientes:
  
- Llamar a un usuario que tenga habilitado estacionamiento de llamadas y haga que Estacione la llamada.
    
    > [!NOTE]
    > Si se habilita el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que es estacionar la llamada debe cerrar la sesión de Skype para la empresa y, a continuación, inicie sesión en, podrá ver la opción de estacionamiento de llamadas en la transferencia de la lista de llamadas. 
  
- Marque el número de órbita para recuperar la llamada.
    
- Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.
    

