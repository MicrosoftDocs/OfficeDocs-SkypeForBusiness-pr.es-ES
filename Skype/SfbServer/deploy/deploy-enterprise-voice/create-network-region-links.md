---
title: Crear vínculos de regiones de red en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Crear o modificar vínculos de región de red, que son utilizados por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: f2b9ba5d6ccf2c2648bf755306001350f82c2931
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a>Crear vínculos de regiones de red en Skype Empresarial Server 2015
 
Crear o modificar vínculos de región de red, que son utilizados por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server. 
  
Las regiones de una red se vinculan mediante conexiones de red WAN físicas. Un vínculo de la región de red crea un vínculo entre dos regiones configurado para Control de admisión llamar (CAC) y establece las limitaciones de ancho de banda en el tráfico de audio y vídeo entre estas regiones.
  
La topología de ejemplo tiene un vínculo entre las regiones de Norteamérica y APAC, y uno entre las regiones de EMEA y APAC. Cada uno de estos vínculos de región está limitado por el ancho de banda WAN, como se describe en la tabla de información de ancho de banda del vínculo de región en [ejemplo: recopilación de requisitos para el control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Para crear vínculos de red de área mediante Skype para el Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el cmdlet New-CsNetworkRegionLink para crear vínculos de región de red y aplicar los correspondientes perfiles de directiva de ancho de banda. Por ejemplo, ejecute lo siguiente:
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Para crear vínculos de red de área mediante Skype para Panel de Control de servidor empresarial

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Vínculo de región**.
    
4. Haga clic en **Nuevo**.
    
5. En la página **Nuevo vínculo de región**, haga clic en **Nombre** y asigne un nombre al vínculo de región de red.
    
6. Haga clic en **Región de red #1** y, en la lista, seleccione la región de red que desea vincular con Región de red #2.
    
7. Haga clic en **Región de red #2** y, en la lista, seleccione la región de red que desea vincular con Región de red #1.
    
8. También puede hacer clic en **Directiva de ancho de banda** y seleccionar el perfil de directiva de ancho de banda que desea aplicar al vínculo de región de red.
    
    > [!NOTE]
    > Aplique una directiva de ancho de banda únicamente si el vínculo de región de red tiene restricciones de ancho de banda y desea usar control de admisión de llamadas para controlar el tráfico de medios en ese vínculo. 
  
9. Haga clic en **Confirmar**.
    
10. Para terminar de crear vínculos de región de red para la topología, repita los pasos del 4 al 9 con parámetros para otras regiones.
    
## <a name="see-also"></a>Vea también

#### 

[Nueva CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Conjunto de CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Quitar CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

