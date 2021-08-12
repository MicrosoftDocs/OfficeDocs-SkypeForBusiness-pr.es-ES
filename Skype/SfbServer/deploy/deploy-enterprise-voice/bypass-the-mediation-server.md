---
title: Configurar la omisión de medios Skype Empresarial Server para omitir siempre el servidor de mediación
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
description: Habilitar la omisión de medios para omitir siempre el servidor de mediación en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: c80b3479546e9154480af8f71417b5ebce43b261510eec19332ecf1cf9287bc4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310039"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar la omisión de medios Skype Empresarial Server para omitir siempre el servidor de mediación
 
Habilitar la omisión de medios para omitir siempre el servidor de mediación en Skype Empresarial Server Telefonía IP empresarial. 
  
 Si usa los pasos de este tema para configurar la configuración global para la omisión de medios, se supone que tiene una buena conectividad entre los extremos de Skype Empresarial y cualquier punto del mismo nivel para el que configuró la omisión de medios en la conexión troncal.
  
Si no tiene una buena conectividad entre los puntos de conexión de Skype Empresarial y todos los del mismo nivel al servidor de mediación cuyas conexiones troncales respectivas se han habilitado para la omisión de medios, debe configurar las opciones de omisión de medios globales para usar la información de sitio y región al emplear la omisión de medios. Con esto se permite un control más preciso para determinar cuándo los medios omiten el servidor de mediación. Para ello, siga los pasos descritos en [Configure media bypass global settings in Skype Empresarial Server to use site and region information](use-site-and-region-information.md) y Associate a subnet with a network [site](deploy-network.md#BKMK_AssociateSubnets) instead.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1. Abra Skype Empresarial Server Panel de control.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la lista.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.
    
5. Haga clic en **Desviar siempre**.
    
6. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Consulte también

[Planear la omisión de medios en Skype Empresarial](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implementar la omisión de medios en Skype Empresarial Server](deploy-media-bypass.md)

