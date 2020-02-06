---
title: Administrar regiones de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Región de red * son los concentradores de red o las redes troncales que se usan en la configuración de control de admisión de llamadas, E9-1-1 y omisión de medios.
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817489"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Administrar regiones de red en Skype Empresarial Server

Las *regiones de red* son los concentradores de red o las redes troncales que se usan en la configuración de control de admisión de llamadas, E9-1-1 y omisión de medios. Use los procedimientos siguientes para ver, crear o modificar regiones de red. Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario crear regiones de red nuevas; otras características avanzadas de telefonía empresarial usarán esas mismas regiones de red. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central. 

Use los procedimientos de este artículo para ver información sobre la región de red o crear, modificar o eliminar regiones de red. 

## <a name="view-network-region-information"></a>Ver información de la región de red 


Una región de red interconecta varias partes de una red en varias áreas geográficas. Cada región de la red debe estar asociada con un sitio central. El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC). Puede usar el panel de control de Skype empresarial Server para ver las regiones de red. Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo. Use este tema para ver las regiones de red existentes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Para ver información sobre una región de red con el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.

4.  En la página **región** , haga clic en la región que desea ver.
  
    > [!NOTE]  
    > Solo puedes ver una región a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Ver información de la región de red mediante cmdlets de Windows PowerShell

Puede ver la información de la región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegion** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Para ver la información de la región de red

  - Para ver información sobre todas las regiones de la red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegion
    
    Devolverá información similar a la siguiente:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Crear o modificar regiones de red 

Una región de red interconecta varias partes de una red en varias áreas geográficas. Cada región de la red debe estar asociada con un sitio central. El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC). Puede usar el panel de control de Skype empresarial Server para configurar las regiones de red. Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una región de red. Use este tema para crear y modificar regiones de red. 

### <a name="to-create-a-network-region"></a>Para crear una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.

4.  En la página **región** , haga clic en **nuevo**.

5.  En la página **nueva región** , escriba un valor en el campo **nombre** . Este valor debe ser único dentro de la implementación de Skype empresarial Server.

6.  En la lista desplegable **sitio central** , seleccione el sitio central de esta región de red.

7.  La casilla de verificación **Habilitar ruta alternativa de audio** está activada de forma predeterminada. Este campo determina si las llamadas de audio se redirigirán a través de una ruta de acceso alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal. Desactive esta casilla solo si necesita desactivar la descarga en Internet. Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.

8.  La casilla de verificación **Habilitar ruta alternativa de vídeo** está activada de forma predeterminada. Este campo determina si las videollamadas se redirigirán a través de una ruta alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal. Desactive esta casilla solo si necesita desactivar la descarga en Internet. Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.

9.  Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta región que no puede expresarse solo por el nombre.

10. Haga clic en **Confirmar**.

La tabla de **sitios asociados** no se usa para crear una región de red. Al crear o modificar el sitio, se asocia un sitio con una región. Para obtener más información, consulte [administrar el control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Para modificar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.

4.  En la página **región** , haga clic en la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar región** , puede modificar la configuración para habilitar y deshabilitar rutas de audio y vídeo alternativas, y cambiar la descripción (para obtener información detallada, consulte la sección "para crear una región de red" anteriormente en este tema.

7.  Haga clic en **Confirmar**.

No puede modificar los **sitios asociados** en esta página. La lista de sitios asociados se proporciona como referencia para que usted sepa qué sitios se verán afectados al modificar la configuración de la región.


## <a name="delete-existing-network-regions"></a>Eliminar regiones de red existentes 

Una región de red interconecta varias partes de una red en varias áreas geográficas. Cada región de la red debe estar asociada con un sitio central. El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC). Puede usar el panel de control de Skype empresarial Server para configurar las regiones de red. Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo. Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una región de red. Use este tema para eliminar regiones de red existentes. 

### <a name="to-delete-a-network-region"></a>Para eliminar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.

4.  En la página **región** , haga clic en la región que desea eliminar.
  
    > [!NOTE]  
    > Puedes eliminar más de una región a la vez. Para ello, presione CTRL y seleccione varias regiones mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las regiones, haga clic en **seleccionar todo** en el menú **edición** .

5.  En el menú **Editar** , haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.


    > [!WARNING]  
    > No se puede quitar una región de red si está asociada a un sitio de red. Si intenta quitar una región asociada a un sitio, recibirá un mensaje de error. Para ver si una región está asociada a algún sitio, seleccione la región y, a continuación, haga clic en **Mostrar detalles** en el menú **edición** .


## <a name="see-also"></a>Vea también

[Administrar rutas de regiones de red](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
