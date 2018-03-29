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
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a>(Opcional) Comprobar la implementación del estacionamiento de llamadas en Skype Empresarial 2015
 
Comprobación de la implementación del parque de llamada en Skype para Telefonía IP empresarial de Business Server. 
  
Después de instalar y configurar llamada Park, debe comprobar la configuración para asegurarse de que el estacionamiento y recuperar llamadas funciona como se esperaba. Como mínimo, compruebe los elementos siguientes:
  
- Llamar a un usuario que tiene habilitado el parque de llamada y tener el parque de usuario la llamada.
    
    > [!NOTE]
    > Si habilitó llamada Park en directiva de voz justo antes de realizar esta prueba, el usuario que es la llamada de estacionamiento debe cerrar la sesión de Skype para el negocio y, a continuación, iniciar sesión en, podrá ver la opción llamada Park en la transferencia de la lista de llamadas. 
  
- Marque el número de órbita para recuperar la llamada.
    
- Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.
    

