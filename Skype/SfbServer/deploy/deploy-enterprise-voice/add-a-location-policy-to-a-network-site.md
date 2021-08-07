---
title: Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asigne directivas de ubicación de E9-1-1 a sitios de red en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: bdb34209a164375b1e21f9e896ec53d7d242c006ec4df4053634918857f8ea4e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305942"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server
 
Asigne directivas de ubicación de E9-1-1 a sitios de red en Skype Empresarial Server Telefonía IP empresarial. 
  
En los ejemplos siguientes se muestra cómo agregar la directiva de ubicación **redmond** definida en Crear directivas de ubicación en [Skype Empresarial Server](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que use la directiva de ubicación **redmond.**
  
Para obtener más información sobre cómo trabajar con sitios de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Para asignar una directiva de ubicación a un sitio de red existente

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Ejecute los siguientes cmdlets para modificar un sitio de red existente.
    
    Asigne la **directiva de ubicación etiquetada redmond** a un sitio de red existente denominado **Redmond**.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Para asignar una directiva de ubicación a un nuevo sitio de red

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Ejecute el siguiente cmdlet para crear un sitio de red.
    
    Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


