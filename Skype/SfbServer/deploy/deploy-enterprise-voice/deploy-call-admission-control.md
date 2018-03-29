---
title: Implementar el control de admisión de llamadas en Skype Empresarial Server 2015
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, consulte Plan de control de admisión de llamadas en Skype para Business Server 2015.
ms.openlocfilehash: 0302663546a099e682b5dc405625d4519fe998d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>Implementar el control de admisión de llamadas en Skype Empresarial Server 2015
 
El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, consulte [Plan de control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implementar el control de admisión de llamadas

1.  Recopilar toda la información necesaria para la topología de red de la empresa, como se describe en [ejemplo: recopilación de requisitos para el control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red. Para obtener más información, vea [implementar regiones de red, sitios y subredes en Skype para negocios 2015](deploy-network.md).
    
3. Crear perfiles de directiva, como se describe en [crear perfiles de directiva de ancho de banda en Skype para Business Server 2015](create-bandwidth-policy-profiles.md) de ancho de banda
    
4. Crear vínculos de región de la red, como se detalla en la [creación de vínculos de red región en Skype para Business Server 2015](create-network-region-links.md).
    
5. Crear rutas de Inter-región de la red, como se describe en [crear red interregional las rutas en Skype para Business Server 2015](create-network-interregional-routes.md).
    
6. Crear directivas entre sitios de la red, como se detalla en [directivas entre sitios de red crear en Skype para Business Server 2015](create-network-intersite-policies.md).
    
7. Habilitar control de admisión de llamada, como se describe en [Habilitar control de admisión de llamada en Skype para Business Server 2015](enable-call-admission-control.md).
    
8. Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente. Para obtener más información, consulte [llamar a la implementación de control de admisión: lista de comprobación final para Skype para Business Server 2015](final-checklist.md).
    

