---
title: Configurar la omisión de medios en Skype para Business Server 2015 se omite siempre el servidor de mediación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Permitir omisión de medios omitir siempre el servidor de mediación en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 5a7ca70b6f060c9d6a5399934fb784c9247e95fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a>Configurar la omisión de medios en Skype para Business Server 2015 se omite siempre el servidor de mediación
 
Permitir omisión de medios omitir siempre el servidor de mediación en Skype para Telefonía IP empresarial de Business Server. 
  
 Si utiliza omitir los pasos de este tema para configurar opciones globales de los medios de comunicación, la suposición es que tiene buena conectividad entre Skype para extremos de negocio y cualquier elemento del mismo nivel para el que configuró omisión de medios en la conexión de troncal.
  
Si no tiene buena conectividad entre Skype para extremos de negocios y todos los elementos del mismo nivel para el servidor de mediación cuyas conexiones tronco respectivo se han habilitado para la omisión de medios, debe configurar media global omisión para utilizar la información del sitio y región Cuando los medios de comunicación que emplean omitir. Esto permite más control sobre la determinación cuando media pasa por alto el servidor de mediación. Para ello, utilice los pasos de [medios configurar Ignorar configuración global de Skype para Business Server 2015 utilizar la información del sitio y región](use-site-and-region-information.md) y [asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) .
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la lista.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.
    
5. Haga clic en **Omitir siempre**.
    
6. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

#### 

[Planear la omisión de medios en Skype para negocios 2015](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implementar la omisión de medios en Skype para Business Server 2015](deploy-media-bypass.md)

