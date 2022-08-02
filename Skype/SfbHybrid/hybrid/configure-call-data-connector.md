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
ms.localizationpriority: medium
ms.collection: ''
description: Instrucciones para configurar el conector de datos de llamadas, que permite ver la telemetría de Skype Empresarial local mediante Skype Empresarial herramientas en línea.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156938"
---
# <a name="configure-call-data-connector"></a>Configurar el conector de datos de llamada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


En este artículo se describe cómo configurar El conector de datos de llamadas, un único conjunto de herramientas que permite ver Skype Empresarial Server datos de calidad de llamadas mediante herramientas de Microsoft Call Quality Dashboard (CQD) y Call Analytics (CA).

Para obtener más información sobre las ventajas y los requisitos previos de Call Data Connector, como los requisitos de rol y la configuración de la conectividad híbrida, consulte [Planear el conector de datos de llamadas](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitación de la supervisión
 
Debe configurar la recopilación de datos de grabación de datos de llamadas (CDR) y calidad de experiencia (QoE) en la supervisión del grupo de servidores front-end con bases de datos locales LCSCdr y QoEMetrics; De lo contrario, los paneles de análisis de llamadas y calidad de llamadas no obtendrán datos con los que trabajar. Antes de configurar el conector de datos de llamadas, siga los pasos que se proporcionan [en Implementación de la supervisión en Skype Empresarial Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR y QoE, así como la supervisión básica.

> [!IMPORTANT]
> Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.

## <a name="enable-call-data-connector"></a>Habilitar el conector de datos de llamadas

Para configurar y habilitar El conector de datos de llamadas, usará los siguientes cmdlets:

| Cmdlet| Descripción|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet en línea que establece un recopilador de datos en línea.|
| Get-CsCloudCallDataConnection | Cmdlet en línea que recupera un recopilador de datos en línea existente.|  
| Get-CsCloudCallDataConnector | Cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Cmdlet local que permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.|

> [!NOTE]
> Para borrar la configuración y empezar de nuevo, use el cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configuración del entorno 

Para configurar el entorno para habilitar un recopilador de datos en línea, primero debe iniciar sesión en el módulo de PowerShell de Microsoft Teams como administrador. Para obtener más información, consulte [Introducción a PowerShell de Microsoft Teams](/microsoftteams/teams-powershell-overview).

Hay dos métodos para iniciar sesión en el módulo de PowerShell de Microsoft Teams:

- Desde el shell de administración de Skype Empresarial Server 2019 (método recomendado)
- Desde otra sesión de PowerShell

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Inicie sesión en el módulo de PowerShell de Microsoft Teams desde el shell de administración de Skype Empresarial Server (método recomendado)

1. Si habilita el conector por primera vez, ejecute el siguiente comando:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si recibe un error que indica que la conexión ya existe, esto significa que la conexión de datos de llamada ya existe para el inquilino. En este caso, ejecute el comando : 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>Inicie sesión en el módulo de PowerShell de Microsoft Teams desde otra sesión de PowerShell (método opcional)

1.  Si habilita el conector por primera vez, ejecute el siguiente comando: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Si recibe un error que indica que la conexión ya existe, esto significa que la conexión de datos de llamada ya existe para el inquilino. En este caso, ejecute el comando : 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

La salida de los comandos anteriores contiene un valor de token, que necesitará al configurar el entorno local de la siguiente manera:

Desde dentro del shell de administración de Skype Empresarial Server, especifique el siguiente comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar el ámbito

Puede habilitar El conector de datos de llamadas para un sitio determinado o para toda la implementación de Skype Empresarial Server mediante el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype Empresarial Server. Por ejemplo, el siguiente comando habilita El conector de datos de llamada en el ámbito global:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Además de la configuración global, los valores de configuración del conector de datos de llamada se pueden asignar al ámbito del sitio. Esto proporciona flexibilidad de administración adicional en lo que respecta a la supervisión. Por ejemplo, un administrador puede habilitar el reenvío del conector de datos de llamadas para el sitio de Redmond, pero deshabilitar el reenvío del conector de datos de llamada para el sitio de Dublín, como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Por ejemplo, supongamos que el reenvío del conector de datos de llamadas está habilitado en el ámbito global, pero deshabilitado en el ámbito del sitio (para el sitio de Redmond). Esto significa que la grabación de detalles de llamadas y la información de QoE no se reenviarán para los usuarios en el sitio de Redmond. Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio de Redmond) tendrán su registro de detalles de llamada y la información de QoE reenviada.

En la tabla siguiente se muestran los valores de la configuración más usada por El conector de datos de llamadas:  

|Propiedad|Descripción|Valor predeterminado|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica si el conector de datos de llamada está habilitado. Si es True, los registros de supervisión se reenviarán a la supervisión en línea.  <br/> |$False  <br/> |
| Identidad | Determina el nivel de ámbito del comando: global o de sitio.   | global  |

## <a name="disable-call-data-connector"></a>Deshabilitar el conector de datos de llamadas

Deshabilitar el conector de datos de llamada no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala ni afecta de otro modo a la base de datos de supervisión de back-end. Al deshabilitar El conector de datos de llamadas, se impide que Skype Empresarial Server cargue datos de llamada en la nube. 

Deshabilite El conector de datos de llamadas mediante el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype Empresarial Server. Por ejemplo, el siguiente comando deshabilita El conector de datos de llamada en el ámbito global estableciendo la propiedad EnableCallDataConnector en $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si desea reanudar la carga de datos de llamada a la nube, establezca la propiedad EnableCallDataConnector en $True, como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Visualización de datos locales a través del panel en línea

 Una vez habilitado el conector de datos de llamada, puede ver los datos de llamadas locales en el panel de Análisis de llamadas o en el Panel de calidad de llamadas, como se describe en [Uso de Call Analytics para solucionar problemas de mala calidad](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) y [Activar y usar el panel de calidad de llamadas para Microsoft Teams y Skype Empresarial Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Más información

Para obtener más información sobre los cmdlets, puede usar el comando Get-Help del Shell de administración de Skype Empresarial Server. Por ejemplo:

Get-Help Get-CsCloudCallDataConnector | más

Get-Help Set-CsCloudCallDataConnector | más

Get-Help Set-CsCloudCallDataConnectorConfiguration | más
