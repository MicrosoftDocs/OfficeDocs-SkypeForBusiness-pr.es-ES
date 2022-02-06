---
title: (Opcional) Comprobar la implementación de estacionamiento de llamadas en Skype Empresarial
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
---

# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Opcional) Comprobar la implementación de estacionamiento de llamadas en Skype Empresarial
 
Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial. 
  
Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que el estacionamiento y la recuperación de llamadas funciona según lo esperado. Como mínimo, compruebe los elementos siguientes:
  
- Llame a un usuario que tenga habilitado el estacionamiento de llamadas y haga que el usuario estacione la llamada.
    
    > [!NOTE]
    > Si ha habilitado el estacionamiento de llamadas en la directiva de voz justo antes de realizar esta prueba, el usuario que estaciona la llamada debe cerrar sesión en Skype Empresarial y, a continuación, volver a iniciar sesión para poder ver la opción Estacionamiento de llamadas en la lista de llamadas de transferencia. 
  
- Marque el número de órbita para recuperar la llamada.
    
- Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.
    

