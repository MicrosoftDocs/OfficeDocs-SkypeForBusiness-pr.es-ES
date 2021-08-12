---
title: 'Skype Empresarial Server: eliminar una colección existente de opciones de configuración de tronco SIP'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Summary: Learn how to delete a collection of trunk configuration settings by using the Skype Empresarial Server Control Panel.'
ms.openlocfilehash: 8927b06c3945be48685f13f33dcee83ff08ae653ade5b2d51228407a3554ef70
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307851"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype Empresarial Server: eliminar una colección existente de opciones de configuración de tronco SIP 
 
**Resumen:** Obtenga información sobre cómo eliminar una colección de opciones de configuración de tronco mediante el panel Skype Empresarial Server control.
  
Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de sucursal de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:
  
- Si la omisión de medios debe habilitarse en los troncos
    
- Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP)
    
- Si es necesario o no el cifrado del Protocolo de transporte en tiempo real seguro (SRTP) en cada tronco
    
Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el Panel de control Skype Empresarial Server o el cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) para "restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer como True, cuando restablece la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.
  
Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al quitar esta configuración personalizada, tenga en cuenta lo siguiente:
  
- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
    
- Si quita la configuración de ámbito de sitio, la colección global de opciones de configuración de troncos administrará los troncos SIP administrados por dicha configuración.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Para quitar las opciones de configuración de tronco Skype Empresarial Server Panel de control

1. En Skype Empresarial Server panel de control, haga clic en **Enrutamiento de** voz y, a continuación, haga clic en Configuración **del tronco**.
    
2. En la **pestaña Configuración de** tronco, seleccione la colección de opciones de configuración de tronco SIP que se eliminarán, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias colecciones en la misma operación, haga clic en la primera colección que se eliminará, mantenga presionada la tecla Ctrl y haga clic en cualquier otra colección que desee quitar.
    
3. La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.
    
4. En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.
    
5. En el **cuadro Skype Empresarial Server panel de control,** haga clic en **Aceptar**.
    
6. Si cambia de opinión y decide no eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar todos los cambios no confirmados**. Cuando aparezca Skype Empresarial Server cuadro de diálogo Panel de **control,** haga clic en **Aceptar**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Quitar la configuración de tronco Configuración mediante cmdlets Skype Empresarial Server Shell de administración

Puede eliminar las opciones de configuración de tronco mediante Skype Empresarial Server Shell de administración y el cmdlet **Remove-CsTrunkConfiguration.** Puede ejecutar este cmdlet desde el Shell Skype Empresarial Server administración o desde una sesión remota de Skype Empresarial Server Shell de administración.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Para quitar una colección especificada de opciones

- El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Para quitar todas las colecciones aplicadas al ámbito del sitio

- Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Para quitar todas las colecciones donde está habilitada la omisión de medios

- El siguiente comando elimina las configuraciones de tronco en las que el desvío de medios se ha habilitado:
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/remove-cstrunkconfiguration)
