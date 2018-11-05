---
title: Crear o modificar subredes de red
TOCTitle: Crear o modificar subredes de red
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48274597
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar subredes de red

 

_**Última modificación del tema:** 2013-02-21_

Cada subred de red debe asociarse a un sitio de red para poder determinar la ubicación geográfica del host que pertenece a esta subred. Puede usar Panel de control de Lync Server para configurar subredes. Desde Panel de control de Lync Server, puede crear, modificar o eliminar una subred de red. Para obtener información detallada sobre la eliminación de subredes de red, consulte [Eliminación de subredes de red](lync-server-2013-deleting-network-subnets.md)

En la mayoría de las implementaciones de Microsoft Lync Server 2013 que implementen el control de admisión de llamadas (CAC) habrá normalmente una gran cantidad de subredes. Por ese motivo, suele ser recomendable configurar subredes desde el Shell de administración de Lync Server. De ese modo podrá llamar a **New-CsNetworkSubnet** junto con el cmdlet **Import-CSV** de Windows PowerShell. Usando estos cmdlet juntos, puede leer la configuración de subred en un archivo de valores separados por comas (.csv) y crear varias subredes al mismo tiempo. Para consultar ejemplos sobre cómo crear subredes a partir de un archivo .csv, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

## Para crear una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Subred**.

4.  En la página **Subred**, haga clic en **Nueva**.

5.  En **Nueva subred**, especifique un valor en el campo **ID de subred**. Debe ser una dirección IP (por ejemplo, 174.11.12.0) y debe estar ubicada en primer lugar en el intervalo de direcciones IP definido por la subred.

6.  En el campo **Máscara**, especifique un valor numérico del 1 al 32.
    

    > [!NOTE]
    > Este valor es la máscara de bits que se aplicará a la subred que se está creando.



7.  En **Id. del sitio de red**, seleccione el sitio al que pertenece la subred.

8.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta subred más allá de lo que se pueda deducir de su nombre.

9.  Haga clic en **Confirmar**.

## Para modificar una subred de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y luego en **Subred**.

4.  En la página **Subred**, haga clic en la subred que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar subred**, puede modificar la máscara de bits, el sitio de red asociado o la descripción. Si modifica la máscara de bits, recuerde que el ID de subred debe seguir siendo la primera dirección del intervalo de dirección IP definido en la subred.

7.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Eliminación de subredes de red](lync-server-2013-deleting-network-subnets.md)  

#### Conceptos

[Acerca de las regiones de red, sitios y subredes en Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  

#### Otros recursos

[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

