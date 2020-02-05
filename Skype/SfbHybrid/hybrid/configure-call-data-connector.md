---
title: Configurar el conector de datos de llamada
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para configurar el conector de datos de llamada, que permite ver la telemetría de Skype empresarial local con el uso de herramientas de Skype empresarial online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726930"
---
# <a name="configure-call-data-connector"></a>Configurar el conector de datos de llamada

En este artículo se describe cómo configurar el conector de datos de llamada, un conjunto de herramientas único que permite ver datos de calidad de llamadas de Skype empresarial Server mediante las herramientas del panel de calidad de llamadas de Skype empresarial online (CQD) y el análisis de llamadas (CA).

Para obtener más información acerca de las ventajas y los requisitos previos de los conectores de datos de llamada, como los requisitos de roles y la configuración de la conectividad híbrida, vea [plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitar la supervisión
 
Debe configurar la recopilación de datos de grabación de datos de llamadas (CDR) y calidad de la experiencia (QoE) en la supervisión del grupo de servidores front-end con bases de datos de LCSCdr y QoEMetrics locales; de lo contrario, los paneles análisis de llamadas y calidad de llamadas no recibirán los datos con los que trabajar. Antes de configurar el conector de datos de llamada, siga los pasos que se indican en [deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar tanto CDR como QoE, así como la supervisión básica.

> [!IMPORTANT]
> Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.

## <a name="enable-call-data-connector"></a>Habilitar el conector de datos de llamada

Para configurar y habilitar el conector de datos de llamada, deberá usar los siguientes cmdlets:

| Cmdlet| Descripción|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Un cmdlet en línea que establece un recopilador de datos en línea.|
| Get-CsCloudCallDataConnection | Un cmdlet en línea que recupera un recopilador de datos en línea existente.|  
| Get-CsCloudCallDataConnector | Un cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Un cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Un cmdlet local que permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.|

> [!NOTE]
> Para borrar la configuración y comenzar de nuevo, use el cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurar el entorno 

Para configurar el entorno para habilitar un recopilador de datos en línea, primero debe iniciar sesión en PowerShell de Skype empresarial online como administrador. Para obtener más información, consulte [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Hay dos métodos para iniciar sesión en PowerShell de Skype empresarial online:

- Desde el shell de administración de Skype empresarial Server 2019 (método recomendado)
- Desde otra sesión de PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Iniciar sesión en PowerShell de Skype empresarial online desde el shell de administración de Skype empresarial Server (método recomendado)

1. Si habilita el conector por primera vez, ejecute el siguiente comando:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si recibe un error que indica que la conexión ya existe, significa que la conexión de datos de llamada ya existe para su espacio empresarial. En este caso, ejecute el comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Iniciar sesión en PowerShell de Skype empresarial online desde otra sesión de PowerShell (método opcional)

1.  Si habilita el conector por primera vez, ejecute el siguiente comando: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Si recibe un error que indica que la conexión ya existe, significa que la conexión de datos de llamada ya existe para su espacio empresarial. En este caso, ejecute el comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

El resultado de los comandos anteriores contiene un valor de token, que necesitará para configurar el entorno local de la siguiente manera:

En el shell de administración de Skype empresarial Server, especifique el siguiente comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar el ámbito

Puede habilitar el conector de datos de llamada para un sitio en particular o para toda la implementación de Skype empresarial Server usando el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype empresarial Server. Por ejemplo, el siguiente comando habilita el conector de datos de llamada en el ámbito global:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Además de la configuración global, las opciones de configuración del conector de datos de llamadas se pueden asignar al ámbito del sitio. Esto proporciona una flexibilidad de administración adicional cuando se trata de la supervisión. Por ejemplo, un administrador puede habilitar el reenvío del conector de datos de llamada para el sitio de Redmond, pero deshabilitar el reenvío del conector de datos de llamada para el sitio de Dublin, tal como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Por ejemplo, supongamos que el reenvío del conector de datos de llamada está habilitado en el ámbito global, pero deshabilitado en el ámbito del sitio (para el sitio de Redmond). Esto significa que el registro detallado de llamadas y la información de QoE no se reenviarán a los usuarios en el sitio de Redmond. Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio de Redmond) tendrán su registro detallado de llamadas y la información de QoE reenviada.

En la tabla siguiente se muestran los valores de las opciones más usadas por el conector de datos de llamada que se usan con más frecuencia:  

|Propiedad|Descripción|Valor predeterminado|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica si el conector de datos de llamada está habilitado. Si es true, los registros de supervisión se reenviarán a la supervisión en línea.  <br/> |$False  <br/> |
| Identidad | Determina el nivel de ámbito del comando: global o de sitio.   | globales  |

## <a name="disable-call-data-connector"></a>Deshabilitar el conector de datos de llamada

Al deshabilitar el conector de datos de llamada, no se desvincula el almacén de supervisión del grupo de servidores front-end, ni se desinstala o afecta de algún otro modo a la base de datos de supervisión back-end. Cuando deshabilita el conector de datos de llamada, deja que Skype empresarial Server cargue los datos de llamada en la nube. 

Deshabilite llamar a Data Connector usando el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype empresarial Server. Por ejemplo, el siguiente comando deshabilita el conector de datos de llamada en el ámbito global al establecer la propiedad EnableCallDataConnector en $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si desea reanudar la carga de datos de llamada en la nube, vuelva a establecer la propiedad EnableCallDataConnector en $True, como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Ver datos locales a través del panel en línea

 Una vez habilitado el conector de datos de llamadas, puede ver los datos de las llamadas locales en el panel del análisis de llamadas o en el panel de calidad de llamadas, como se describe en [use análisis de llamadas para solucionar problemas de mala calidad](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) y [activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype empresarial online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Más información

Para obtener más información sobre los cmdlets, puede usar el comando Get-Help desde el shell de administración de Skype empresarial Server. Por ejemplo:

Get-Help Get-CsCloudCallDataConnector | adicional

Get-Help Set-CsCloudCallDataConnector | adicional

Get-Help Set-CsCloudCallDataConnectorConfiguration | adicional
