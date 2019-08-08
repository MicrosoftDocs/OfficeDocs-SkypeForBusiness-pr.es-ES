---
title: Implementar el control de admisión de llamadas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233193"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implementar el control de admisión de llamadas en Skype empresarial Server
 
El control de admisión de llamadas (CAC) es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, consulte [planear el control de admisión de llamadas en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implementar el control de admisión de llamadas

1.  Reúna toda la información necesaria para la topología de red de su empresa, como se describe en [ejemplo: recopilación de requisitos para el control de admisión de llamadas en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si todavía no lo ha hecho, debe definir los sitios y las regiones de red, y asociar subredes a sitios de red. Para obtener más información, consulte [implementar regiones, sitios y subredes de la red en Skype empresarial](deploy-network.md).
    
3. Crear perfiles de directiva de ancho de banda, como se detalla en [crear perfiles de directiva de ancho de banda en Skype empresarial Server](create-bandwidth-policy-profiles.md)
    
4. Cree vínculos de región de red, como se describe en [vínculos a regiones de red en Skype empresarial Server](create-network-region-links.md).
    
5. Cree rutas entre regiones de red, como se detalla en [crear rutas interregional de red en Skype empresarial Server](create-network-interregional-routes.md).
    
6. Cree directivas de intersitios de red, como se detalla en [crear directivas entre sitios de red en Skype empresarial Server](create-network-intersite-policies.md).
    
7. Habilite el control de admisión de llamadas, como se detalla en [Habilitar el control de admisión de llamadas en Skype empresarial Server](enable-call-admission-control.md).
    
8. Realice unas comprobaciones finales de la configuración para asegurarse de que todo funciona correctamente. Para obtener más información, consulte [llamar a la implementación de control de admisión: lista de comprobación final para Skype empresarial Server](final-checklist.md).
    

