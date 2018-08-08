---
title: Eliminar una colección existente de opciones de configuración del tronco SIP en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumen: Obtenga información sobre cómo eliminar una colección de configuraciones de tronco mediante el Skype para el Panel de Control de servidor empresarial.'
ms.openlocfilehash: 94f6e24c645a85bf2ed9ba5ded2f8eb4f207209f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968834"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Eliminar una colección existente de opciones de configuración del tronco SIP en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo eliminar una colección de configuraciones de tronco mediante el Skype para el Panel de Control de servidor empresarial.
  
Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
  
- Si se debe activar la omisión de medios en los troncos.
    
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
    
- Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.
    
Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted. Esta recopilación global de configuraciones no puede eliminarse. Sin embargo, puede usar el Skype para el Panel de Control de servidor empresarial o el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) "Restablecer" las propiedades de la colección global a sus valores predeterminados. Por ejemplo, si ha definido el parámetro Enable3pccRefer en True, al restablecer la recopilación global el parámetro Enable3pccRefer volverá al valor predeterminado False.
  
Los Administradores también pueden crear configuraciones de tronco personalizadas en el ámbito del sitio o en el ámbito del servicio (para una puerta de enlace PSTN individual); estas configuraciones personalizadas pueden eliminarse. Al eliminar estas configuraciones personalizadas tenga en cuenta lo siguiente:
  
- Si elimina la configuración del ámbito del servicio, el tronco SIP administrado por esas configuraciones será administrado por las configuraciones aplicadas a su sitio, si existieran. Si no existen las configuraciones del sitio, esos troncos serán administrados por la recopilación global de configuraciones de tronco.
    
- Si elimina las configuraciones del ámbito del sitio, cualquier tronco SIP administrado por esas configuraciones será entonces administrado por la recopilación global de configuraciones de tronco.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Para quitar las opciones de configuración de tronco con Skype de Panel de Control de servidor empresarial

1. En Skype para el Panel de Control de servidor empresarial, haga clic en **Enrutamiento de voz** y, a continuación, haga clic en **Configuración del tronco**.
    
2. En la pestaña **Configuración de tronco**, seleccione la recopilación de configuraciones de tronco SIP que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**. Para eliminar varias recopilaciones en la misma operación, haga clic en la primera recopilación que desea eliminar, luego mantenga presionada la tecla Ctrl y haga clic en cualquier otra recopilación que desee eliminar.
    
3. La propiedad **Estado** para la recopilación se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la recopilación, haga clic en **Confirmar** y luego en **Confirmar todo**.
    
4. En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en haga clic en **Aceptar**.
    
5. En el cuadro de diálogo de **Skype para el Panel de Control de Business Server** haga clic en **Aceptar**.
    
6. Si cambia de opinión y decide no eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Cancelar todos los cambios no confirmados**. Cuando aparezca el cuadro de diálogo de **Skype para el Panel de Control de servidor empresarial** , haga clic en **Aceptar**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Eliminación de opciones de configuración de tronco utilizando Skype para Cmdlets de Shell de administración de servidor empresarial

Puede eliminar las configuraciones de tronco con Skype para Shell de administración de servidor empresarial y el cmdlet **Remove-CsTrunkConfiguration** . Puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Skype para Shell de administración de servidor empresarial.
  
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

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .
  

