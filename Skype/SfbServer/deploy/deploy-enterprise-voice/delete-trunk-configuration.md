---
title: Eliminar una colección existente de parámetros de configuración del tronco de SIP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumen: Aprenda a eliminar una colección de parámetros de configuración de troncal con el panel de control de Skype empresarial Server.'
ms.openlocfilehash: 830f5c42e26c4ef7a5ffca0a57fc7e70c2509f83
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280463"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminar una colección existente de parámetros de configuración del tronco de SIP en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo eliminar una colección de valores de configuración del tronco con el panel de control de Skype empresarial Server.
  
Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
  
- Si se debe activar la omisión de medios en los troncos.
    
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
    
- Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.
    
Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el panel de control de Skype empresarial Server o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) para "restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.
  
Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:
  
- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
    
- Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Para quitar la configuración de Troncalización con el panel de control de Skype empresarial Server

1. En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz** y luego en **configuración troncal**.
    
2. En la pestaña **Configuración de tronco**, seleccione la recopilación de configuraciones de tronco SIP que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.
    
3. La propiedad **Estado** para la recopilación se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la recopilación, haga clic en **Confirmar** y luego en **Confirmar todo**.
    
4. En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.
    
5. En el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.
    
6. If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. Cuando aparezca el cuadro de diálogo **Panel de control de Skype empresarial Server** , haga clic en **Aceptar**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Quitar las opciones de configuración de troncal con los cmdlets del shell de administración de Skype empresarial Server

Puede eliminar los ajustes de configuración del tronco mediante el shell de administración de Skype empresarial Server y el cmdlet **Remove-CsTrunkConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de la consola de administración de Skype empresarial Server.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Para quitar una recopilación concreta de opciones de configuración

- El siguiente comando elimina las configuraciones de tronco aplicadas al sitio Redmond:
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Quitar todas las recopilaciones aplicadas al ámbito del sitio

- Este comando elimina todas las configuraciones de tronco aplicadas al ámbito del servicio:
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Quitar todas las recopilaciones en las que la omisión de medios está habilitada

- El siguiente comando quita las configuraciones de tronco en las que la omisión de medios se ha habilitado:
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .
  

