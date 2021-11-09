---
title: (Opcional) Comprobar la implementación de estacionamiento de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 9258a38936ffe22eb209c4b4bd9d1e5692341003
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838342"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Comprobar la implementación de estacionamiento de llamadas en Skype Empresarial
 
Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial. 
  
Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que el estacionamiento y la recuperación de llamadas funciona según lo esperado. Como mínimo, compruebe los elementos siguientes:
  
- Llame a un usuario que tenga habilitado el estacionamiento de llamadas y haga que el usuario estacione la llamada.
    
    > [!NOTE]
    > Si ha habilitado el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que estaciona la llamada debe cerrar sesión en Skype Empresarial y, a continuación, volver a iniciar sesión para poder ver la opción Estacionamiento de llamadas en la lista de llamadas de transferencia. 
  
- Marque el número de órbita para recuperar la llamada.
    
- Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.
    

