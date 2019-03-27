---
title: Eliminar una colección existente de opciones de configuración del tronco SIP en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 6a7c90bf7ff435b0936b34bc57d391e06093040a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879367"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminar una colección existente de opciones de configuración del tronco SIP en Skype para Business Server

Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo (RTCP) de control de transporte en tiempo real.
- Si se requiere cifrado del protocolo seguro en tiempo real (SRTP) en cada tronco.

Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el Skype para el Panel de ServerControl empresarial o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) "Restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.

Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:

- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
- Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.

**Para quitar las opciones de configuración de tronco con el Skype de Panel de Control de servidor empresarial** 

1. En Skype para el Panel de Control de servidor empresarial, haga clic en **Enrutamiento de voz**y, a continuación, haga clic en **Configuración del tronco**.
2. En la ficha **Configuración del tronco** , seleccione la colección de opciones de configuración de tronco SIP para eliminarse, haga clic en **Editar**y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.
3. La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.
4. En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.
5. En el cuadro de diálogo **Skype para el Panel de Control de servidor empresarial** , haga clic en **Aceptar**.
6. Si cambia de opinión y decide no eliminar la colección, haga clic en **Confirmar**y, a continuación, haga clic en **Cancelar todos los cambios no confirmados**. Cuando aparezca el cuadro de diálogo de **Skype para el Panel de Control de servidor empresarial** , haga clic en **Aceptar**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de tronco mediante el uso de cmdlets de Windows PowerShell


Puede eliminar las configuraciones de tronco mediante el uso de Windows PowerShell y el cmdlet **Remove-CsTrunkConfiguration** . Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

**Para quitar una recopilación concreta de opciones de configuración**

El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Quitar todas las recopilaciones aplicadas al ámbito del sitio**

Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Quitar todas las recopilaciones en las que la omisión de medios está habilitada**

El siguiente comando quita las configuraciones de tronco en las que la omisión de medios se ha habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
