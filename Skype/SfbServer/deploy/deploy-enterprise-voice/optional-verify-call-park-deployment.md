---
title: (Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa
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
ms.openlocfilehash: b07b3b3bfb709770a4f30f2f6cb43e5ce5dbcc3a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000532"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Comprobación de la implementación de estacionamiento de llamadas en Skype para la empresa
 
Comprobación de la implementación de estacionamiento de llamadas en Skype para Business Server Enterprise Voice. 
  
Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que de estacionamiento y recuperación de llamadas funciona según lo previsto. Como mínimo, compruebe los elementos siguientes:
  
- Llamar a un usuario que tenga habilitado estacionamiento de llamadas y haga que Estacione la llamada.
    
    > [!NOTE]
    > Si se habilita el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que es estacionar la llamada debe cerrar la sesión de Skype para la empresa y, a continuación, inicie sesión en, podrá ver la opción de estacionamiento de llamadas en la transferencia de la lista de llamadas. 
  
- Marque el número de órbita para recuperar la llamada.
    
- Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.
    

