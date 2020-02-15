---
title: Eliminación de una colección existente de opciones de configuración de tronco SIP en Skype empresarial Server
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
description: 'Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 09f5e7fda03c5e0e5221661f87482b67192ce302
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045062"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminación de una colección existente de opciones de configuración de tronco SIP en Skype empresarial Server

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:

- Si se debe habilitar el desvío de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
- Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el panel de ServerControl de Skype empresarial o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) para "restablecer" las propiedades de la recopilación global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer como True, cuando restablece la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.

Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:

- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
- Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.

**Para quitar las opciones de configuración del tronco con el panel de control de Skype empresarial Server** 

1. En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración de tronco**.
2. En la pestaña **configuración de tronco** , seleccione la colección de opciones de configuración de tronco SIP que se van a eliminar, haga clic en **Editar**y, a continuación, haga clic en **eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.
3. La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.
4. En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.
5. En el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.
6. Si cambia de opinión y decide no eliminar la colección, haga clic en **confirmar**y, a continuación, haga clic en **cancelar todos los cambios no confirmados**. Cuando aparezca el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminación de las opciones de configuración del tronco mediante cmdlets de Windows PowerShell


Puede eliminar las opciones de configuración del tronco con Windows PowerShell y el cmdlet **Remove-CsTrunkConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

**Para quitar una colección de opciones de configuración especificada**

El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Para quitar todas las recopilaciones aplicadas al ámbito del sitio**

Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Para quitar todas las colecciones en las que está habilitada la omisión de medios**

El siguiente comando elimina las configuraciones de tronco en las que el desvío de medios se ha habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) .
