---
title: Configurar la omisión de medios en Skype Empresarial Server para que siempre omita el servidor de mediación
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilite la omisión de medios para omitir siempre el servidor de mediación en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804220"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar la omisión de medios en Skype Empresarial Server para que siempre omita el servidor de mediación
 
Habilite la omisión de medios para omitir siempre el servidor de mediación en Skype Empresarial Server Telefonía IP empresarial. 
  
 Si usa los pasos de este tema para configurar la configuración global para la omisión de medios, se supone que tiene una buena conectividad entre los puntos de conexión de Skype Empresarial y cualquier sistema del mismo nivel para el que configuró la omisión de medios en la conexión troncal.
  
Si no tiene una buena conectividad entre los puntos de conexión de Skype Empresarial y todos los sistemas del mismo nivel con el servidor de mediación cuyas conexiones troncales respectivas se han habilitado para la omisión de medios, debe configurar las opciones globales de omisión de medios para usar información de sitio y región al usar la omisión de medios. Con esto se permite un control más preciso para determinar cuándo los medios omiten el servidor de mediación. Para ello, siga los pasos descritos en Configure [media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and Associate a subnet with a network [site](deploy-network.md#BKMK_AssociateSubnets) instead.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1. Abra el Panel de control de Skype Empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la lista.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.
    
5. Haga clic en **Desviar siempre**.
    
6. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

[Planear la omisión de medios en Skype Empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implementar la omisión de medios en Skype Empresarial Server](deploy-media-bypass.md)

