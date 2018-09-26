---
title: Configurar el conector de datos de llamada
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para configurar el conector de datos de llamadas, que permite la telemetría de Skype para empresarial local para verse mediante Skype para herramientas profesionales en línea.
ms.openlocfilehash: 38e74e76e09d03036419f16807841a67fdf3433a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030577"
---
# <a name="configure-call-data-connector"></a>Configurar el conector de datos de llamada

[!INCLUDE [disclaimer](../disclaimer.md)]

En este artículo se describe cómo configurar el conector de datos de llamadas--un único conjunto de herramientas que permite ver Skype para datos de calidad de llamadas de negocio Server mediante Skype para herramientas de negocio Online llamada calidad panel (CQD) y análisis de llamadas (CA). 

> [!NOTE]
> En la versión preliminar pública, panel de análisis de llamadas sólo está disponible.

Para obtener más información acerca de las ventajas de conector de datos de llamadas y los requisitos previos, como los requisitos de las funciones y la configuración de conectividad híbrida, consulte [Planeación de conector de datos de llamada](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitar la supervisión 

Debe configurar el registro de datos de llamadas (CDR) y recopilación de datos de calidad de la experiencia (QoE); de lo contrario, el análisis de llamadas y paneles de calidad de llamadas no obtienen información para mostrar. Antes Configure conector de datos de llamada, siga los pasos proporcionados en [Deploy supervisión en Skype para Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR y QoE.


## <a name="enable-call-data-connector"></a>Habilitar conector de datos de llamada

Para configurar y habilitar el conector de datos de llamadas, va a usar los cmdlets siguientes:

| Cmdlet| Descripción|
| :-----------------|---------------:|
| Nueva CsCloudCallDataConnection | Un cmdlet en línea que establece un recopilador de datos en línea.|
| Get-CsCloudCallDataConnection | Un cmdlet en línea que recupera un recopilador de datos en línea existente.|  
| Get-CsCloudCallDataConnector | Un cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Un cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Un cmdlet local que le permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.|

### <a name="configure-your-environment"></a>Configurar el entorno 

Para configurar el entorno para habilitar a un recopilador de datos en línea, debe primero inicie sesión en Skype para profesionales Online PowerShell como administrador. Para obtener más información, vea [Administrar Skype para profesionales en línea con Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Existen dos métodos para iniciar sesión en Skype para PowerShell en línea de negocio:

- Desde el Skype para shell de administración de Business Server 2019 (método recomendado)
- Desde otra sesión de PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Inicie sesión Skype para PowerShell en línea de negocio desde la Skype para Business Server management shell (método recomendado)

1. Si habilita el conector por primera vez, ejecute el siguiente comando:

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si recibe un error que la conexión ya existe, esto significa que la conexión de datos llamada ya existe para el inquilino. En este caso, ejecute el comando: 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Inicie sesión Skype para PowerShell en línea de negocio desde otra sesión de PowerShell (método opcional)

1.  Si habilita el conector por primera vez, ejecute el siguiente comando: 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Si recibe un error que la conexión ya existe, esto significa que la conexión de datos llamada ya existe para el inquilino. En este caso, ejecute el comando: 

    ```
    Get-CsCloudCallDataConnection  
    ```

El resultado de los comandos anteriores contiene un valor de símbolo (token) que necesitará al configurar su entorno local de la siguiente manera:

Desde dentro de la Skype para shell de administración de Business Server, especifique el siguiente comando:

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar el ámbito

Puede habilitar llame al conector de datos para un sitio concreto o para su Skype completo para la implementación de servidor empresarial mediante el cmdlet Set-CsCloudCallDataConnectorConfiguration desde dentro de la Skype para shell de administración de Business Server. Por ejemplo, el siguiente comando permite llamar al conector de datos en el ámbito global:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Además de la configuración global, opciones de configuración del conector de datos de llamadas pueden asignarse al ámbito del sitio. Esto proporciona mayor flexibilidad de administración, lo que respecta a la supervisión. Por ejemplo, un administrador puede habilitar el reenvío de llamadas de conector de datos para el sitio de Redmond, pero deshabilitar el reenvío de llamadas conector de datos para el sitio de Dublin, tal como se muestra en el ejemplo siguiente:
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Por ejemplo, suponga que el desvío de llamadas de conector de datos está habilitado en el ámbito global, pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond). Esto significa que información de QoE y registro de detalles de llamadas no se desviarán para los usuarios en el sitio de Redmond. Sin embargo, los usuarios en otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio Redmond) tendrán sus detalles de las llamadas y la información de QoE reenviado.

Los valores para la configuración usada con más frecuencia utilizado por el conector de datos de llamadas se muestran en la tabla siguiente:  
|Propiedad|Descripción|Valor predeterminado|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica si está habilitado el conector de datos de llamada. Si es True, los registros de supervisión se desviarán a la supervisión en línea.  <br/> |$False  <br/> |
| Identity  | Determina el nivel de ámbito para el comando: global o sitio.   | global  |

## <a name="disable-call-data-connector"></a>Deshabilitar el conector de datos de llamada

Deshabilitar el conector de datos de llamadas no desasociar al almacén de supervisión desde el grupo de servidores Front-End, ni desinstalar o en caso contrario, afectan a la base de datos de supervisión de back-end. Cuando se deshabilita el conector de datos de llamadas, detenga Skype para Business Server de carga de datos de la llamada a la nube. 

Deshabilitar el conector de datos de llamadas usando el cmdlet Set-CsCloudCallDataConnectorConfiguration desde dentro de la Skype para shell de administración de Business Server. Por ejemplo, el siguiente comando deshabilita el conector de datos de llamadas en el ámbito global estableciendo la propiedad EnableCallDataConnector en $False:
  
```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si desea reanudar la carga de datos de la llamada a la nube, Establece la propiedad EnableCallDataConnector atrás en $True, tal como se muestra en el ejemplo siguiente:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Vista de datos locales a través del panel en línea

 Después de llamar al conector de datos está habilitado, puede ver los datos de llamada local en el panel de análisis de llamadas, tal como se describe en el [Análisis de uso de llamadas para solucionar problemas de calidad deficiente](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).


## <a name="for-more-information"></a>Más información

Para obtener más información sobre los cmdlets, puede usar el comando Get-Help desde el Skype para Shell de administración de servidor empresarial. Por ejemplo:
  
Get-Help Get-CsCloudCallDataConnector | más

Get-Help Set-CsCloudCallDataConnector | más

Get-Help Set-CsCloudCallDataConnectorConfiguration | más