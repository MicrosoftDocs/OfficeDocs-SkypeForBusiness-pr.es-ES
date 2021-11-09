---
title: Crear vínculos de región de red en Skype Empresarial Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Cree o modifique vínculos de región de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.
ms.openlocfilehash: 0d6d3fd1c3f432135352477051cab157e5979d33
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860897"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>Crear vínculos de región de red en Skype Empresarial Server
 
Cree o modifique vínculos de región de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server. 
  
Las regiones de una red se vinculan mediante conexiones de red WAN físicas. Un vínculo de región de red crea un vínculo entre dos regiones configuradas para el Control de admisión de llamadas (CAC) y establece las limitaciones de ancho de banda en el tráfico de audio y vídeo entre estas regiones.
  
La topología de ejemplo tiene un vínculo entre las regiones de Norteamérica y APAC, y uno entre las regiones de EMEA y APAC. Cada uno de estos vínculos de región está restringido por el ancho de banda wan, como se describe en la tabla Información de ancho de banda de vínculos regionales en [Ejemplo:](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)Recopilación de requisitos para el control de admisión de llamadas en Skype Empresarial Server .
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>Para crear vínculos de región de red mediante Skype Empresarial Server Shell de administración

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Ejecute el cmdlet New-CsNetworkRegionLink para crear vínculos de región de red y aplicar los correspondientes perfiles de directiva de ancho de banda. Por ejemplo, ejecute lo siguiente:
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>Para crear vínculos de región de red mediante Skype Empresarial Server Panel de control

1. Abra Skype Empresarial Server Panel de control.
    
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
    
## <a name="see-also"></a>Consulte también

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)