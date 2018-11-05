---
title: "Eliminar opciones de configuración existentes de troncos SIP en Lync Server 2013"
TOCTitle: "Supp. d’une collection existante de par. de conf. de jonction SIP dans LS 2013"
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49889046
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un conjunto existente de opciones de configuración de troncos SIP en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-22_

Los parámetros de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), la central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos parámetros especifican, por ejemplo, lo siguiente:

  - Si el desvío de medios debe habilitarse en los troncos.

  - Las condiciones bajo las cuales se envían los paquetes del protocolo de transporte en tiempo real (RTCP).

  - Si se requiere o no el cifrado del protocolo de transporte seguro en tiempo real (SRTP) en cada tronco.

Al instalar Microsoft Lync Server 2013, se crea una recopilación global de configuraciones de tronco SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede utilizar el Panel de control de Lync Server o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) para "restablecer" las propiedades de la recopilación global a los valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer como True, cuando restablece la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.

Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:

  - Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.

  - Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.

## Eliminar las configuraciones de tronco utilizando el Panel de control de Lync Server

1.  En Panel de control de Lync Server, haga clic en **Enrutamiento de voz** y, a continuación, haga clic en **Configuración del tronco**.

2.  En la pestaña **Configuración del tronco**, seleccione la recopilación de configuraciones de tronco SIP que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.

3.  La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.

4.  En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.

5.  En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013**, haga clic en **Aceptar**.

6.  Si cambia de opinión y decide no eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar todos los cambios no confirmados**. Cuando aparece el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013**, haga clic en **Aceptar**.

## Eliminar las configuraciones del tronco utilizando los cmdlets de Lync Server PowerShell

Las configuraciones del tronco también pueden eliminarse utilizando Windows PowerShell y el cmdlet Remove-CsTrunkConfiguration. Este cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Eliminar una recopilación específica de configuraciones

  - El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

## Eliminar todas las recopilaciones aplicadas al ámbito del sitio

  - Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

## Eliminar todas las recopilaciones en las que el desvío de medios está habilitado

  - El siguiente comando elimina las configuraciones de tronco en las que el desvío de medios se ha habilitado:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration).

