---
title: Implementar regiones de red, sitios y las subredes de Skype para la empresa
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Crear o modificar regiones de red, sitios de red y asociar subredes de red en Skype para Business Server. Todas estas se usan para las características avanzadas de Enterprise Voice: desvío de medios, el control de admisión y enrutamiento basado en la ubicación de llamadas.'
ms.openlocfilehash: c4598a1a8ffd46412ce16992788af060e5df0b98
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260408"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Implementar regiones de red, sitios y las subredes de Skype para la empresa

Crear o modificar regiones de red, sitios de red y asociar subredes de red en Skype para Business Server. Todas estas se usan para las características avanzadas de Enterprise Voice: desvío de medios, el control de admisión y enrutamiento basado en la ubicación de llamadas.

Las características avanzadas de Telefonía IP empresarial son [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) y [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Para todas estas características, es necesario crear regiones de red, sitios de red y subredes. Por ejemplo, todas estas características requieren que cada una de las subredes de la topología estén asociadas a un sitio de red específico, y cada uno de los sitios de red debe estar asociado a una región de red. Para obtener más información acerca de estos términos, vea [configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)

El control de admisión de llamadas y E9-1-1 tienen requisitos de configuración adicionales para los sitios de red:

- El control de admisión de llamadas requiere que se especifique un   perfil de directiva de ancho de banda para cada uno de los sitios restringidos con limitaciones de ancho de banda WAN. Si tiene previsto implementar el control de admisión de llamadas, debe [crear perfiles de directiva de ancho de banda en Skype para Business Server](create-bandwidth-policy-profiles.md) antes de configurar los sitios de red.

- E9-1-1 requiere que se especifique una directiva de ubicación para cada uno de los sitios. Si planea implementar E9-1-1, debe [crear las directivas de ubicación en Skype para Business Server](create-location-policies.md) antes de configurar los sitios de red.

## <a name="create-or-modify-a-network-region"></a>Crear o modificar una región de red

Si ya ha creado las regiones de red para una de estas características, no es necesario crear nuevas regiones de red; otras características avanzadas de Enterprise Voice utilizará esas mismos regiones de red.

Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Para crear una región de red mediante Skype para Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Por ejemplo:

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    En este ejemplo, ha creado una región de red denominada "NorthAmerica" que está asociado a un sitio central con identificador de sitio CHICAGO.

3. Para terminar de crear regiones de red para la topología, repita el paso 2 con parámetros para cada región de red.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Para crear una región de red mediante Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Configuración de red**.

3. Haga clic en **Región**

4. Haga clic en **Nuevo**.

5. En la página **Región nueva**, haga clic en **Nombre** y escriba un nombre para la región de red.

6. Haga clic en **Sitio central** y, a continuación, haga clic en un sitio central de la lista.

7. Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.

8. Haga clic en **Confirmar**.

9. Para terminar de crear regiones de red para la topología, repita los pasos del 4 al 8 con parámetros para otras regiones.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Para modificar una región de red mediante Skype para Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Por ejemplo:

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    En este ejemplo, se modifica una región de red existente denominada "NorthAmerica" (creada mediante los procedimientos descritos anteriormente en este tema) cambiando la descripción. Si existía una descripción para el área de "NorthAmerica", este comando sobrescribe con este valor; Si no se establecieron ninguna descripción, a continuación, este comando establece.

3. Para modificar otras regiones de red, repita el paso 2 con parámetros para otras regiones.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Para modificar una región de red mediante Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Configuración de red**.

3. Haga clic en el botón de navegación **Región**.

4. En la tabla, haga clic en la región de red que desee modificar.

5. Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.

6. En la página **Editar región** , cambie los valores de configuración de la región de red según corresponda.

7. Haga clic en **Confirmar**.

8. Para terminar de modificar regiones de red, repita los pasos del 4 al 7 con parámetros para otras regiones.

## <a name="create-or-modify-a-network-site"></a>Crear o modificar un sitio de red

Si ya ha creado los sitios de red para una de estas características, no es necesario crear nuevos sitios de red; otras características avanzadas de Enterprise Voice usarán los mismos sitios de red. Con todo, puede que sea necesario modificar una definición de sitio de red existente para aplicar una configuración específica de una característica. Así, si ha creado un sitio de red para E9-1-1, deberá modificar el sitio de red durante la implementación de un control de admisión de llamadas con objeto de aplicar un perfil de directiva de ancho de banda.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para crear un sitio de red mediante el uso de Skype para Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Ejecute el cmdlet New-CsNetworkSite para crear sitios de red:

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Por ejemplo:

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    En este ejemplo, ha creado un sitio de red denominado "Chicago" que se encuentra en la región de red "NorthAmerica".

    > [!NOTE]
    > Esta región de red ya debe existir para que este comando se ejecute correctamente.

3. Para terminar de crear sitios de red en su topología, repita el paso 2 con la configuración pertinente del resto de sitios.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para crear un sitio de red mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Configuración de red**.

3. Haga clic en el botón de navegación **Sitio**.

4. Haga clic en **Nuevo**.

5. En la página **Nuevo sitio**, haga clic en **Nombre** y, a continuación, escriba un nombre para el sitio de red.

6. Haga clic en **Región**y, a continuación, en una región de la lista.

7. Si lo desea, también puede hacer clic en **Directiva de ancho de banda** y hacer clic en una directiva de ancho de banda de la lista.

    > [!NOTE]
    > Las directivas de ancho de banda solo son necesarias cuando se implementa el control de admisión de llamadas en el sitio.

8. Si lo desea, también puede hacer clic en **Directiva de ubicación** y hacer clic en una directiva de ubicación de la lista.

    > [!NOTE]
    > Las directivas de ubicación solo son necesarias cuando se implementa E9-1-1 en el sitio.

9. Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.

10. Haga clic en **Confirmar**.

11. Para terminar de crear sitios de red en su topología, repita los pasos 4 a 10 con la configuración pertinente del resto de sitios.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para modificar un sitio de red mediante el uso de Skype para Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Ejecute el cmdlet Set-CsNetworkSite para modificar sitios de red:

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    Por ejemplo:

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    En este ejemplo, se mueve el sitio denominado a "Albuquerque" a la región de red "NorthAmerica". Para modificar la configuración de sitio de red a fin de implementar el control de admisión de llamadas, E9-1-1 o el desvío de medios, cambie la configuración del sitio de red ejecutando el cmdlet Set-CsNetworkSite con los parámetros BWPolicyProfileID o LocationPolicy respectivamente.

    > [!NOTE]
    > En el caso del desvío de medios, existe un parámetro BypassID, si bien se recomienda encarecidamente no invalidar automáticamente los identificadores de desvío generados. No es necesario especificar más parámetros para configurar un sitio de red para el desvío de medios.

3. Para terminar de modificar sitios de red en su topología, repita el paso 2 con la configuración pertinente del resto de sitios.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para modificar un sitio de red mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Configuración de red**.

3. Haga clic en el botón de navegación **Sitio**.

4. En la tabla, haga clic en el sitio de red que desee modificar.

5. Haga clic en **Editar** y, a continuación, en **Mostrar detalles…**.

6. En la página **Modificar sitio** , cambie los valores de configuración de este sitio de red según corresponda.

7. Haga clic en **Confirmar**.

8. Para terminar de modificar sitios de red, repita los pasos 4 a 7 con la configuración pertinente del resto de sitios.

## <a name="associate-a-subnet-with-a-network-site"></a>Asociar una subred a un sitio de red
<a name="BKMK_AssociateSubnets"> </a>

Cada subred de la red debe estar asociado a un sitio de red específico, debido a que la información de la subred se utiliza para determinar el sitio de red en el que se encuentra un extremo mientras se inicia una nueva sesión. Cuando se conoce la ubicación de cada parte en una sesión, pueden aplicar las características de Enterprise Voice esa información avanzada para determinar cómo controlar la configuración de llamadas o enrutamiento.

Todas las direcciones IP públicas de los servidores perimetrales de audio y vídeo en la implementación deben incluirse en los parámetros de configuración de red. Estas direcciones IP se agregan como subredes con una máscara de 32. El sitio de red asociado debe corresponder con el sitio de red configurado adecuado. Por ejemplo, en la dirección IP pública que se corresponde con el servicio perimetral A/v en el sitio central Chicago debería ser NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para asociar una subred a un sitio de red mediante el uso de Skype para Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

2. Ejecute el cmdlet **New-CsNetworkSubnet** para asociar una subred a un sitio de red:

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Por ejemplo:

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    En este ejemplo, ha creado una asociación entre la subred 172.11.12.13 y el sitio de red "Chicago".

3. Repita el paso 2 para todas las subredes de la topología.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Para asociar subredes a sitios de red mediante la importación de un archivo CSV

1. Cree un archivo CSV que incluya todas las subredes que quiera agregar. Por ejemplo, cree un archivo denominado   **subnet.csv** con el contenido siguiente:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

3. Ejecute el siguiente cmdlet para importar **subnet.csv**y, a continuación, almacenar su contenido en el almacén de administración de Lync Server:

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para asociar una subred a un sitio de red mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.

2. En la barra de navegación izquierda, haga clic en **Configuración de red**.

3. Haga clic en el botón de navegación **Subred**.

4. Haga clic en **Nuevo**.

5. En la página **Nueva subred**, haga clic en **Id. de subred** y escriba la primera dirección en el intervalo de direcciones IP definido mediante la subred que quiere asociar al sitio de red.

6. Haga clic en **Máscara** y escriba la máscara de bits que quiere aplicar a la subred.

7. Haga clic en **Id. de sitio de red** y seleccione el identificador de sitio del sitio al que agrega esta subred.

    > [!NOTE]
    > Si todavía no ha creado sitios de red, esta lista estará vacía. Para obtener información detallada sobre el procedimiento, vea [creación o modificación de un sitio de red](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx). También puede recuperar los identificadores de sitio para la implementación mediante la ejecución del cmdlet **Get-CsNetworkSite** . Para obtener información detallada, vea el Skype para la documentación del Shell de administración de servidor empresarial.

8. Si lo desea, haga clic en **Descripción** y escriba información adicional para describir esta subred.

9. Haga clic en **Confirmar**.

Repita estos pasos para agregar otras subredes a un sitio de red.
> [!NOTE]
> Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas.

A continuación se ofrece la información de alerta relevante y un ejemplo:

 **Origen**: servicio de directivas de ancho de banda CS (principal)

 **Número de evento**: 36034

 **Nivel**: 2

 **Descripción**: las subredes de las siguientes direcciones IP: \<lista de direcciones IP\> no son está configurada o las subredes no están asociadas a un sitio de red.

 **Causa**: las subredes de las correspondientes direcciones IP faltan en las opciones de configuración de la red o las subredes no están asociadas a un sitio de red.

 **Solución**: agregue subredes correspondientes a la lista de direcciones IP en los parámetros de configuración de red y asocie todas las subredes a un sitio de red.

Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:

1. Asegúrese de que la dirección IP 10.121.248.226 esté asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 esté asociada a la subred 10.121.249.0/24.

2. Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 esté asociada a un sitio de red.

## <a name="see-also"></a>Vea también
<a name="BKMK_AssociateSubnets"> </a>


[Nueva CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

