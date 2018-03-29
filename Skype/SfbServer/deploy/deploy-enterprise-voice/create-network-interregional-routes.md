---
title: Crear rutas entre regiones de red en Skype Empresarial Server 2015
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Crear o modificar las rutas interregional de red, que son utilizadas por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: 112c74c07956073fee3e51a6e0856d875b6268ff
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a>Crear rutas entre regiones de red en Skype Empresarial Server 2015
 
Crear o modificar las rutas interregional de red, que son utilizadas por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server. 
  
Una ruta de red interregional define la ruta entre un par de regiones de la red. Cada par de regiones de red de la implementación del servicio de control de admisión de llamadas precisa una ruta entre regiones de red. Esto permite que todas las regiones de red de la implementación obtengan acceso a cualquier otra región.
  
Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones, una ruta entre regiones determina la ruta de acceso vinculada que atravesará la conexión de una región a otra.
  
En el ejemplo de topología, hay que definir rutas entre regiones de red para cada uno de los tres pares de regiones: Norteamérica/EMEA, EMEA/APAC y Norteamérica/APAC. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>Crear red interregionales rutas mediante Skype para el Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el cmdlet **New-CsNetworkInterRegionRoute** para definir las rutas necesarias. Por ejemplo, ejecute:
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > La ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red debido a que no hay un vínculo de región de red directo entre ellas. 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>Crear red interregionales rutas mediante Skype para Panel de Control de servidor empresarial

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Ruta regional**.
    
4. Haga clic en **Nuevo**.
    
5. En la página **Nueva ruta regional**, haga clic en **Nombre** y escriba un nombre para la ruta entre regiones de red.
    
6. Haga clic en **Región de red #1** y, a continuación, haga clic en una región de red de la lista que desee enrutar a la Región de red #2.
    
7. Haga clic en **Región de red #2** y, en la lista, seleccione la región de red que desea enrutar a la Región de red #1.
    
8. Haga clic en **Agregar** junto al campo **Vínculos de región de red** y luego agregue un vínculo de región de red que se usará en la ruta entre regiones de red.
    
    > [!NOTE]
    > Si está creando una ruta para dos regiones de red que no tengan ningún vínculo de región de red directo entre ellas, tendrá que agregar todos los vínculos necesarios para completar la ruta. Por ejemplo, la ruta entre regiones de red Norteamérica/APAC requiere dos vínculos de región de red, debido a que no hay un vínculo de región de red directo entre ellas. 
  
9. Haga clic en **Confirmar**.
    
10. Para finalizar la creación de rutas entre regiones de red de la topología, repita los pasos del 4 al 9 con la configuración para otras rutas entre regiones de red.
    
## <a name="see-also"></a>Vea también

#### 

[Nueva CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Conjunto de CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Quitar CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

