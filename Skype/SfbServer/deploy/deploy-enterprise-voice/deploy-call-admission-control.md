---
title: Implementación de control de admisión de llamadas en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.
ms.openlocfilehash: 6ea527bc48f4a61bfe128eb935231200bb88b29f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892765"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implementación de control de admisión de llamadas en Skype para Business Server
 
El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, consulte [Plan para el control de admisión de llamadas en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implementar el control de admisión de llamadas

1.  Recopilar toda la información necesaria para la topología de red de empresa, tal como se describe en [ejemplo: recopilación de requisitos de control de admisión de llamadas en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red. Para obtener información detallada, consulte [Deploy regiones de red, sitios y las subredes de Skype para la empresa](deploy-network.md).
    
3. Crear perfiles de directiva, como se detalla en [crear perfiles de directiva de ancho de banda en Skype para Business Server](create-bandwidth-policy-profiles.md) de ancho de banda
    
4. Crear vínculos de región de red, como se detalla en [crear vínculos de región de red en Skype para Business Server](create-network-region-links.md).
    
5. Crear rutas de entre regiones de red, como se detalla en [interregionales rutas de red de crear en Skype para Business Server](create-network-interregional-routes.md).
    
6. Crear directivas entre sitios de red, como se detalla en [directivas entre sitios de red crear en Skype para Business Server](create-network-intersite-policies.md).
    
7. Habilitar el control de admisión de llamadas, como se detalla en [Habilitar control de admisión de llamadas en Skype para Business Server](enable-call-admission-control.md).
    
8. Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente. Para obtener información detallada, vea [implementación de control de admisión de llamadas: lista de comprobación de final de Skype para Business Server](final-checklist.md).
    

