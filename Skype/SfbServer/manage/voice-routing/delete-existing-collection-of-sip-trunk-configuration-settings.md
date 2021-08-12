---
title: 'Skype Empresarial Server: eliminar una colección existente de opciones de configuración de tronco SIP'
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
description: 'Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 1fb551505f52980e884a78278d33e282510b3388aa636ee3a37018267e5e612d
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849935"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype Empresarial Server: eliminar una colección existente de opciones de configuración de tronco SIP

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:

- Si se debe habilitar el desvío de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
- Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el panel Skype Empresarial ServerControl o el cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) para "restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer como True, cuando restablece la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.

Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:

- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
- Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.

**Para quitar las opciones de configuración de tronco con Skype Empresarial Server Panel de control** 

1. En el Panel Skype Empresarial Server control, haga clic en **Enrutamiento** de voz y, a continuación, haga clic en **Configuración de tronco.**
2. En la **pestaña Configuración de** tronco, seleccione la colección de opciones de configuración de tronco SIP que se eliminarán, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.
3. La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.
4. En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.
5. En el **cuadro Skype Empresarial Server panel de control,** haga clic en **Aceptar**.
6. Si cambia de opinión y decide no eliminar la colección, haga clic en **Confirmar** y, a continuación, haga clic en Cancelar todos **los cambios no confirmados**. Cuando aparezca Skype Empresarial Server cuadro de diálogo Panel de **control,** haga clic en **Aceptar**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de tronco mediante Windows PowerShell cmdlets


Puede eliminar las opciones de configuración de tronco mediante Windows PowerShell y el cmdlet **Remove-CsTrunkConfiguration.** Puede ejecutar este cmdlet desde el Shell de administración Skype Empresarial Server desde una sesión remota de Windows PowerShell. 

**Para quitar una colección especificada de opciones**

El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**Para quitar todas las colecciones aplicadas al ámbito del sitio**

Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**Para quitar todas las colecciones donde está habilitada la omisión de medios**

El siguiente comando elimina las configuraciones de tronco en las que el desvío de medios se ha habilitado:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/Remove-CsTrunkConfiguration)
