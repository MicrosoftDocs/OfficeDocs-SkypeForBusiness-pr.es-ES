---
title: Implementar el control de admisión de llamadas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: El control de admisión de llamadas es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre.
ms.openlocfilehash: f7d813d85a3c3eadd770c1dc939358506c230d44
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861907"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Implementar el control de admisión de llamadas en Skype Empresarial Server
 
El control de admisión de llamadas es una solución que determina si puede establecerse una sesión en tiempo real según el ancho de banda disponible para impedir que los usuarios de redes congestionadas obtengan una calidad de audio y vídeo pobre. Para obtener más información, vea [Plan for call admission control in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Para implementar el control de admisión de llamadas

1.  Recopile toda la información necesaria para la topología de red empresarial, como se describe en [Ejemplo:](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)Recopilación de requisitos para el control de admisión de llamadas en Skype Empresarial Server .
    
2. Si aún no lo ha hecho, debe definir regiones y sitios de red y asociar subredes con sitios de red. Para obtener más información, vea [Deploy network regions, sites and subnets in Skype Empresarial](deploy-network.md).
    
3. Cree perfiles de directiva de ancho de banda, como se detalla en [Crear perfiles](create-bandwidth-policy-profiles.md) de directiva de ancho de banda en Skype Empresarial Server
    
4. Cree vínculos de región de red, como se detalla en Crear vínculos [de región de](create-network-region-links.md)red en Skype Empresarial Server .
    
5. Cree rutas entre regiones de red, como se detalla en [Crear rutas interregionales de red en Skype Empresarial Server](create-network-interregional-routes.md).
    
6. Cree directivas entre sitios de red, como se detalla en [Crear directivas entre](create-network-intersite-policies.md)sitios de red en Skype Empresarial Server .
    
7. Habilite el control de admisión de llamadas, tal como se detalla en Habilitar el control de admisión [de llamadas en Skype Empresarial Server](enable-call-admission-control.md).
    
8. Comprueba algunas configuraciones finales para asegurarte de que todo esté configurado correctamente. Para obtener más información, vea [Implementación del control de admisión de llamadas: lista de comprobación final para Skype Empresarial Server](final-checklist.md).
    

