---
title: Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server 2015
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asignar directivas de ubicación de E9-1-1 a los sitios de red de Skype para Business Server Enterprise Voice.
ms.openlocfilehash: d167fb40e4a6318ce0621d365782cab3848cf284
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568266"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server 2015
 
Asignar directivas de ubicación de E9-1-1 a los sitios de red de Skype para Business Server Enterprise Voice. 
  
Los siguientes ejemplos muestran cómo agregar la directiva de ubicación de **Redmond** definida en [las directivas de ubicación de crear de Skype para Business Server 2015](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que usa la ubicación de **Redmond** Directiva.
  
Para obtener información detallada sobre cómo trabajar con sitios de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Para asignar una directiva de ubicación a un sitio de red existente

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute los siguientes cmdlets para modificar un sitio de red existente.
    
    Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Para asignar una directiva de ubicación a un nuevo sitio de red

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el siguiente cmdlet para crear un sitio de red.
    
    Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


