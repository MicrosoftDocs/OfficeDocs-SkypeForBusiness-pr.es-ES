---
title: Configurar la omisión de elementos multimedia en Skype empresarial Server para omitir siempre el servidor de mediación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilitar omisión de elementos multimedia para omitir siempre el servidor de mediación en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: cde2a1bff41016e05ac6c74978fa65b45f11a1e7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768273"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar la omisión de elementos multimedia en Skype empresarial Server para omitir siempre el servidor de mediación
 
Habilitar omisión de elementos multimedia para omitir siempre el servidor de mediación en Skype empresarial Server Enterprise Voice. 
  
 Si usa los pasos de este tema para establecer la configuración global para la omisión de medios, se supone que tiene una buena conectividad entre los puntos de conexión de Skype empresarial y cualquier otro elemento del mismo nivel para el que haya configurado el bypass de medios en la conexión troncal.
  
Si no tiene buena conectividad entre los puntos de conexión de Skype empresarial y todos los elementos del servidor de media cuyas conexiones troncales se hayan habilitado para la omisión de medios, debe configurar la configuración de omisión de multimedia global para usar la información del sitio y de la región. al emplear la omisión de medios. Esto permite un mayor control para determinar cuándo el contenido multimedia pasa por alto el servidor de mediación. Para ello, use los pasos de [configurar la configuración global de omisión de medios en Skype empresarial Server para usar la información del sitio y de la región](use-site-and-region-information.md) y [asociar una subred con un sitio de red](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1. Abra el panel de control de Skype empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la lista.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.
    
5. Haga clic en **Omitir siempre**.
    
6. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

[Plan de omisión de multimedia en Skype empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implementación de omisión de contenido multimedia en Skype empresarial Server](deploy-media-bypass.md)

