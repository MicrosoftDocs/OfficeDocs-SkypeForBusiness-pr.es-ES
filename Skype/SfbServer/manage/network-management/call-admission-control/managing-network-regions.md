---
title: Administración de regiones de red
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La región de red* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, E9-1-1 y la omisión de medios.
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816420"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Administrar regiones de red en Skype Empresarial Server

Las *regiones de red* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios. Siga los siguientes procedimientos para ver, crear o modificar regiones de red. Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario que cree nuevas regiones de red; otras características avanzadas de Enterprise Voice usarán las mismas regiones de red. Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central. 

Use los procedimientos de este artículo para ver información de región de red o crear, modificar o eliminar regiones de red. 

## <a name="view-network-region-information"></a>Ver información de región de red 


Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas). Puede usar el Panel de control de Skype Empresarial Server para ver las regiones de red. Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo. Use este tema para ver las regiones de red existentes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Para ver información sobre una región de red con el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, en **Región.**

4.  En la **página Región,** haga clic en la región que desea ver.
  
    > [!NOTE]  
    > Solo puede ver una región a la vez.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de región de red mediante cmdlets Windows PowerShell de red

Puede ver información de región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegion.** Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Para ver información de región de red

  - Para ver información sobre todas las regiones de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkRegion
    
    Devolverá información similar a la siguiente:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)


## <a name="create-or-modify-network-regions"></a>Crear o modificar regiones de red 

Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas). Puede usar el Panel de control de Skype Empresarial Server para configurar regiones de red. Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo. Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una región de red. Siga este tema para crear y modificar regiones de red. 

### <a name="to-create-a-network-region"></a>Para crear una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, en **Región.**

4.  En la página **Región**, haga clic en **Nuevo**.

5.  En la página **Región nueva**, escriba un valor en el campo **Nombre**. Este valor debe ser único en la implementación de Skype Empresarial Server.

6.  En la lista desplegable **Sitio central**, seleccione el sitio central para esta región de red.

7.  La casilla  **Habilitar ruta alternativa de audio** está activada de forma predeterminada. Este campo determina si las llamadas de audio se enrutarán a través de una ruta de acceso alternativa cuando no exista un ancho de banda adecuado en la ruta de acceso principal. Desactívela solamente si necesita cancelar la descarga de Internet. Si alguna de las llamadas que realice se hará por Internet, esta casilla debe estar marcada, independientemente del ancho de banda.

8.  La casilla  **Habilitar ruta alternativa de vídeo** está activada de forma predeterminada. Este campo determina si las llamadas de vídeo se enrutarán a través de una ruta de acceso alternativa cuando no exista un ancho de banda adecuado en la ruta de acceso principal. Desactívela solamente si necesita cancelar la descarga de Internet. Si alguna de las llamadas que realice se hará por Internet, esta casilla debe estar marcada, independientemente del ancho de banda.

9.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta región aparte de lo que se pueda deducir de su nombre.

10. Haga clic en **Confirmar**.

La tabla **Sitios asociados** no se usa para crear una región de red. Un sitio se asocia a una región cuando se crea o modifica el sitio. Para obtener más información, consulte [Administración del control de admisión de llamadas para sitios.](managing-call-admission-control-for-sites.md)

### <a name="to-modify-a-network-region"></a>Para modificar una región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, en **Región.**

4.  En la página **Región**, haga clic en el vínculo regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar región**, puede modificar la configuración para habilitar y deshabilitar las rutas alternativas de audio y vídeo y modificar la descripción (para obtener información detallada, consulte la sección "Para crear una sección de red" de más arriba en este tema).

7.  Haga clic en **Confirmar**.

En esta página, no se pueden modificar los **Sitios asociados**. La lista de sitios asociados se proporciona a modo de referencia, de forma que pueda saber los sitios que se verán afectados cuando modifique la configuración de la región.


## <a name="delete-existing-network-regions"></a>Eliminar regiones de red existentes 

Una región de red interconecta varias partes de una red a través de varias zonas geográficas. Cada región de red debe asociarse con un sitio central. El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas). Puede usar el Panel de control de Skype Empresarial Server para configurar regiones de red. Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo. Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una región de red. Use este tema para eliminar las regiones de red existentes. 

### <a name="to-delete-a-network-region"></a>Para eliminar una región de red:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, en **Región.**

4.  En la página **Región**, haga clic en la región que desea eliminar.
  
    > [!NOTE]  
    > Si lo desea, puede eliminar varias regiones en la misma operación. Para ello, presione Ctrl y seleccione varias regiones mientras mantiene presionada esta tecla. O bien, para seleccionar todas las regiones, haga clic en **Seleccionar todo** en el menú **Editar**.

5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.


    > [!WARNING]  
    > No se puede quitar una región si está asociada a un sitio de red. Si intenta quitar una región asociada a un sitio, recibirá un mensaje de error. Para ver si una región está asociada a algún sitio, seleccione la región y haga clic en **Mostrar detalles** en el menú **Editar**.


## <a name="see-also"></a>Consulte también

[Administración de rutas de región de red](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
