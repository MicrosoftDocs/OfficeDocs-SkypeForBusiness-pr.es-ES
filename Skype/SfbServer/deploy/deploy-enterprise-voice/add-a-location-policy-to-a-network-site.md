---
title: Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server 2015
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asignar directivas de ubicación de E9-1-1 a los sitios de la red de Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server 2015
 
Asignar directivas de ubicación de E9-1-1 a los sitios de la red de Skype para Telefonía IP empresarial de Business Server. 
  
Los ejemplos siguientes muestran cómo agregar la directiva de ubicación de **Redmond** definida en [las políticas de ubicación de crear en Skype para Business Server 2015](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que utiliza la ubicación de **Redmond** Directiva.
  
Para obtener más información acerca de cómo trabajar con sitios de red, consulte la documentación de Shell de administración de Lync Server para los siguientes cmdlets:
  
- **Nueva CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Conjunto de CsNetworkSite**
    
- **Quitar CsNetworkSite**
    
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


