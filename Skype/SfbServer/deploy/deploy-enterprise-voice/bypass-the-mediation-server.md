---
title: Configurar el desvío de medios en Skype para Business Server omitir siempre el servidor de mediación
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Habilitar desvío de medios omitir siempre el servidor de mediación en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 2671a4df1b7c068e650cba35be6409f97b8682f8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881857"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>Configurar el desvío de medios en Skype para Business Server omitir siempre el servidor de mediación
 
Habilitar desvío de medios omitir siempre el servidor de mediación en Skype para Business Server Enterprise Voice. 
  
 Si usa los pasos descritos en este tema para establecer la configuración global para los medios de desvío, es de la suposición de que dispone de buena conectividad entre Skype para los extremos de negocio y cualquier elemento del mismo nivel para los que ha configurado el desvío de medios en la conexión del tronco.
  
Si no se dispone de buena conectividad entre Skype para los extremos de negocio y todos los elementos del mismo nivel para el servidor de mediación cuyas conexiones de tronco respectivos han sido habilitadas para el desvío de medios, debe establecer la configuración de desvío de medios global para usar información de sitio y región Cuando el desvío de medios que emplean. Esto permite más control sobre la determinación de cuándo medios omiten el servidor de mediación. Para ello, utilice los pasos descritos en [la configuración global en Skype para Business Server usar la información de sitio y región de desvío de medios de configurar](use-site-and-region-information.md) y [asociar una subred a un sitio de red](deploy-network.md#BKMK_AssociateSubnets) en su lugar.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga doble clic en la configuración **Global** de la lista.
    
4. En la página **Editar configuración global**, seleccione la casilla **Habilitar omisión de medios**.
    
5. Haga clic en **Omitir siempre**.
    
6. Haga clic en **Confirmar**.
    
## <a name="see-also"></a>Vea también

[Planear el desvío de medios en Skype para la empresa](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[Implementar el desvío de medios en Skype para Business Server](deploy-media-bypass.md)

