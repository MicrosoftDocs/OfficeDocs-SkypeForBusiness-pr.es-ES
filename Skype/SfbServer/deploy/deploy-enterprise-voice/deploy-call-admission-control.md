---
title: Implementar el control de admisión de llamadas en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, vea Plan para el control de admisión de llamadas en Skype for Business Server 2015.
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>Implementar el control de admisión de llamadas en Skype Empresarial Server 2015
 
El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, consulte [Plan para el control de admisión de llamadas en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implementar el control de admisión de llamadas

1.  Recopilar toda la información necesaria para la topología de red de empresa, tal como se describe en [ejemplo: recopilación de requisitos de control de admisión de llamadas en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red. Para obtener información detallada, consulte [Deploy regiones de red, sitios y las subredes de Skype para profesionales de 2015](deploy-network.md).
    
3. Crear perfiles de directiva, como se detalla en [crear perfiles de directiva de ancho de banda en Skype para Business Server 2015](create-bandwidth-policy-profiles.md) de ancho de banda
    
4. Crear vínculos de región de red, como se detalla en [crear vínculos de región de red en Skype para Business Server 2015](create-network-region-links.md).
    
5. Crear rutas de entre regiones de red, como se detalla en [interregionales rutas de red de crear en Skype para Business Server 2015](create-network-interregional-routes.md).
    
6. Crear directivas entre sitios de red, como se detalla en [directivas entre sitios de red crear en Skype para Business Server 2015](create-network-intersite-policies.md).
    
7. Habilitar control de admisión de llamadas, como se detalla en [Habilitar control de admisión de llamadas en Skype para Business Server 2015](enable-call-admission-control.md).
    
8. Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente. Para obtener información detallada, vea [implementación de control de admisión de llamadas: lista de comprobación de final de Skype para Business Server 2015](final-checklist.md).
    

