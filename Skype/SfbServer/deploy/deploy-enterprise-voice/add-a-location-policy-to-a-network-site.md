---
title: Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asignar directivas de ubicación E9-1-1 a los sitios de red en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768283"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server
 
Asignar directivas de ubicación E9-1-1 a los sitios de red en la telefonía IP empresarial de Skype empresarial. 
  
En los siguientes ejemplos se muestra cómo agregar la Directiva de ubicación de **Redmond** definida en [crear directivas de ubicación en Skype empresarial Server](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que use la Directiva de ubicación de **Redmond** .
  
Para obtener más información sobre cómo trabajar con sitios de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Para asignar una directiva de ubicación a un sitio de red existente

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute los siguientes cmdlets para modificar un sitio de red existente.
    
    Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Para asignar una directiva de ubicación a un nuevo sitio de red

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el siguiente cmdlet para crear un sitio de red.
    
    Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


