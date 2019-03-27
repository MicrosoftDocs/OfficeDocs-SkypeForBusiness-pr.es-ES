---
title: Administración de regiones de red
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Región de red * son los concentradores de red o redes troncales utilizados en la configuración de desvío de medios, E9-1-1 y control de admisión llamada.
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877632"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Administrar regiones de red en Skype Empresarial Server

*Regiones de red* son los concentradores de red o redes troncales utilizados en la configuración de desvío de medios, E9-1-1 y control de admisión llamada. Use los siguientes procedimientos para ver, crear o modificar regiones de red. Por ejemplo, si ya ha creado las regiones de red para una característica de voz, no es necesario crear nuevas regiones de red; otras características avanzadas de Enterprise Voice utilizará esas mismos regiones de red. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central. 

Use los procedimientos de este artículo para ver la información de la región de red o crear, modificar o eliminar regiones de red. 

## <a name="view-network-region-information"></a>Ver información de región de red 


Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas. Cada región de red debe estar asociado a un sitio central. El sitio central es el sitio del centro de datos en el que se ejecuta el servicio de directiva de ancho de banda de llamada admisión control (CAC). Puede usar Skype para el Panel de Control de servidor empresarial para ver las regiones de red. Regiones de red incluyen opciones de configuración que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeos. Use este tema para ver las regiones de red existente. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Para ver información acerca de una región de red con Skype de Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.

4.  En la página **región** , haga clic en la región que desea ver.
  
    > [!NOTE]  
    > Sólo se puede ver una región a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de región de red mediante el uso de cmdlets de Windows PowerShell

Puede ver información de la región de red mediante el uso de Windows PowerShell y el cmdlet **Get-CsNetworkRegion** . Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Para ver la información de la región de red

  - Para ver información acerca de todas las regiones de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegion
    
    Devolverá información similar a la siguiente:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Creación o modificación de regiones de red 

Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas. Cada región de red debe estar asociado a un sitio central. El sitio central es el sitio del centro de datos en el que se ejecuta el servicio de directiva de ancho de banda de llamada admisión control (CAC). Puede usar el Skype para el Panel de Control de servidor empresarial para configurar regiones de red. Regiones de red incluyen opciones de configuración que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeos. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una región de red. Use este tema para crear y modificar regiones de red. 

### <a name="to-create-a-network-region"></a>Para crear una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.

4.  En la página **región** , haga clic en **nuevo**.

5.  En la página **Región nueva** , escriba un valor en el campo **nombre** . Este valor debe ser único dentro de su Skype para la implementación de Business Server.

6.  En la lista desplegable **sitio Central** , seleccione el sitio central para esta región de red.

7.  La casilla de verificación **Habilitar la ruta de acceso alternativa audio** está activada de forma predeterminada. Este campo determina si se van a enrutar las llamadas de audio a través de una ruta de acceso alternativa si no existe ancho de banda adecuado en la ruta de acceso principal. Desactive esta casilla de verificación sólo si necesita desactivar la descarga de Internet. Si alguna de las llamadas va a ser llamadas por Internet, esta casilla de verificación debe ser activado, independientemente de la configuración de ancho de banda.

8.  La casilla de verificación **Habilitar la ruta de acceso alternativa vídeo** está activada de forma predeterminada. Este campo determina si se van a enrutar las llamadas de vídeo a través de una ruta de acceso alternativa si no existe ancho de banda adecuado en la ruta de acceso principal. Desactive esta casilla de verificación sólo si necesita desactivar la descarga de Internet. Si alguna de las llamadas va a ser llamadas por Internet, esta casilla de verificación debe ser activado, independientemente de la configuración de ancho de banda.

9.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de esta región que se pueda deducir de su nombre.

10. Haga clic en **Confirmar**.

La tabla de **sitios asociados** no se usa para la creación de una región de red. Asociar un sitio con una región al crear o modificar el sitio. Para obtener información detallada, vea [Managing control de admisión de llamadas para los sitios](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Para modificar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.

4.  En la página **región** , haga clic en la región que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar región** , puede modificar la configuración para habilitar y deshabilitar audio y vídeo alternan de rutas de acceso y cambiar la descripción (para obtener información detallada, vea la sección "para crear una región de red" anteriormente en este tema.

7.  Haga clic en **Confirmar**.

No se puede modificar los **sitios asociados** en esta página. La lista de sitios asociados se proporciona para referencia para que conozcan de los sitios que se verán afectados cuando se modifica la configuración de la región.


## <a name="delete-existing-network-regions"></a>Eliminación de regiones de red existentes 

Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas. Cada región de red debe estar asociado a un sitio central. El sitio central es el sitio del centro de datos en el que se ejecuta el servicio de directiva de ancho de banda de llamada admisión control (CAC). Puede usar el Skype para el Panel de Control de servidor empresarial para configurar regiones de red. Regiones de red incluyen opciones de configuración que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeos. De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una región de red. Use este tema para eliminar las regiones de red existente. 

### <a name="to-delete-a-network-region"></a>Para eliminar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.

4.  En la página **región** , haga clic en la región que desea eliminar.
  
    > [!NOTE]  
    > Puede eliminar más de una región a la vez. Para ello, presione la tecla CTRL y seleccione varias regiones mientras mantiene presionada la tecla CTRL. O bien, para seleccionar todas las regiones, haga clic en **Seleccionar todo** en el menú **Edición** .

5.  En el menú **Edición** , haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.


    > [!WARNING]  
    > No se puede quitar una región de red si está asociada con un sitio de red. Si intenta quitar una región asociada con un sitio, recibirá un mensaje de error. Para ver si una región está asociada con todos los sitios, seleccione la región y, a continuación, haga clic en **Mostrar detalles** en el menú **Edición** .


## <a name="see-also"></a>Consulte también

[Administración de rutas de región de red](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
