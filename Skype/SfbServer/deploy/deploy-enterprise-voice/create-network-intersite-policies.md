---
title: Crear directivas entre sitios de red en Skype Empresarial Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Cree directivas entre sitios de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.
ms.openlocfilehash: 8e5fb020ece1762868f9d943eb2aad955903b91329d636a981e644b2e9892b67
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338758"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Crear directivas entre sitios de red en Skype Empresarial Server
 
Cree directivas entre sitios de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server. 
  
Una directiva entre sitios de red define las limitaciones de ancho de banda entre sitios que tienen vínculos WAN directos entre ellos.
  
> [!IMPORTANT]
> Solo se requiere una  directiva entre sitios de red si hay un vínculo directo entre dos sitios de red.
  
En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque. Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado. En el siguiente ejemplo se aplica el perfil 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Para crear una directiva entre sitios de red

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tienen un vínculo cruzado directo. Por ejemplo, ejecute:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Repita el paso 2 según sea necesario para crear directivas entre sitios de red para todos los pares de sitios de red que tengan un vínculo cruzado directo.
    
## <a name="see-also"></a>Consulte también

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)