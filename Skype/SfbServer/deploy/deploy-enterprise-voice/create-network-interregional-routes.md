---
title: Crear rutas interregionales de red en Skype Empresarial Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Cree o modifique rutas interregionales de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093128"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>Crear rutas interregionales de red en Skype Empresarial Server
 
Cree o modifique rutas interregionales de red, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server. 
  
Una ruta interregional de red define la ruta entre un par de regiones de red. Cada par de regiones de red de la implementación del control de admisión de llamadas requiere una ruta interregional de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.
  
Aunque los vínculos de región establecen limitaciones de ancho de banda en las conexiones entre regiones, una ruta interregional determina qué ruta vinculada recorrerá la conexión de una región a otra.
  
En la topología de ejemplo, las rutas interregionales de red deben definirse para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Para crear rutas interregionales de red mediante el Shell de administración de Skype Empresarial Server

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
2. Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias. Por ejemplo, ejecute:
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > La ruta interregional de red de Norteamérica/APAC requiere dos vínculos de región de red porque no hay ningún vínculo de región de red directo entre ellos. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Para crear rutas interregionales de red mediante el Panel de control de Skype Empresarial Server

1. Abra el Panel de control de Skype Empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Ruta regional**.
    
4. Haga clic en **Nuevo**.
    
5. En la **página Nueva ruta de** región, haga clic en **Nombre** y, a continuación, escriba un nombre para la ruta interregional de red.
    
6. Haga clic en **Región de red #1** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #2.
    
7. Haga clic en **Región de red #2** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #1.
    
8. Haga **clic en** Agregar junto al campo **Vínculos de región** de red y, a continuación, agregue un vínculo de región de red que se usará en la ruta interregional de red.
    
    > [!NOTE]
    > Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta interregional de red Norteamérica/APAC requiere dos vínculos de región de red porque no hay un vínculo de región de red directo entre ellos. 
  
9. Haga clic en **Confirmar**.
    
10. Para terminar de crear rutas interregionales de red para la topología, repita los pasos del 4 al 9 con la configuración de otras rutas interregionales de red.
    
## <a name="see-also"></a>Ver también

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)