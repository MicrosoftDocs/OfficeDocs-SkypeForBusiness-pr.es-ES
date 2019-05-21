---
title: Eliminar una colección existente de parámetros de configuración del tronco de SIP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274936"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminar una colección existente de parámetros de configuración del tronco de SIP en Skype empresarial Server

Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.
- Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el panel de ServerControl de Skype empresarial o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) para "restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.

Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:

- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
- Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.

**Para quitar la configuración de troncal con el panel de control de Skype empresarial Server** 

1. En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración troncal**.
2. En la pestaña **configuración de tronco** , seleccione la colección de parámetros de configuración del tronco del SIP que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.
3. La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.
4. En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.
5. En el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.
6. Si cambia de opinión y decide no eliminar la colección, haga clic en **confirmar**y, a continuación, haga clic en **cancelar todos los cambios**no confirmados. Cuando aparezca el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de troncal mediante cmdlets de Windows PowerShell


Puede eliminar las opciones de configuración del tronco mediante Windows PowerShell y el cmdlet **Remove-CsTrunkConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

**Para quitar una recopilación concreta de opciones de configuración**

El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Quitar todas las recopilaciones aplicadas al ámbito del sitio**

Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Quitar todas las recopilaciones en las que la omisión de medios está habilitada**

El siguiente comando quita las configuraciones de tronco en las que la omisión de medios se ha habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
