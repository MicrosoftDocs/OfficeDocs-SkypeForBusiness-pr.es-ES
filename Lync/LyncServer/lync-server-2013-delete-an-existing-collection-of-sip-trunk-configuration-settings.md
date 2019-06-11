---
title: Eliminar un conjunto existente de opciones de configuración de troncos SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Eliminar una colección existente de parámetros de configuración del tronco de SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

  - Si se debe activar la omisión de medios en los troncos.

  - Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.

  - Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Microsoft Lync Server 2013, se crea una colección global de parámetros de configuración del tronco del SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el panel de control de Lync Server o el cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) para "restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.

Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:

  - Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.

  - Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Para quitar la configuración de troncal con el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **enrutamiento de voz** y luego en **configuración troncal**.

2.  En la pestaña **Configuración de tronco**, seleccione la recopilación de configuraciones de tronco SIP que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.

3.  La propiedad **Estado** para la recopilación se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la recopilación, haga clic en **Confirmar** y luego en **Confirmar todo**.

4.  En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.

5.  En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013** , haga clic en **Aceptar**.

6.  If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. Cuando aparezca el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013** , haga clic en **Aceptar**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de troncal mediante cmdlets de Windows PowerShell

Puede eliminar las opciones de configuración del tronco mediante Windows PowerShell y el cmdlet **Remove-CsTrunkConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Para quitar una recopilación concreta de opciones de configuración

  - El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Quitar todas las recopilaciones aplicadas al ámbito del sitio

  - Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Quitar todas las recopilaciones en las que la omisión de medios está habilitada

  - El siguiente comando quita las configuraciones de tronco en las que la omisión de medios se ha habilitado:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

