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
description: Instrucciones para configurar Call Data Connector, que permite que la telemetría de Skype Empresarial local se vea con Skype Empresarial online.
ms.openlocfilehash: 28a9ba2f00a071ff5b1c0781240cf54a2de929e8
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510601"
---
# <a name="configure-call-data-connector"></a>Configurar el conector de datos de llamada

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


En este artículo se describe cómo configurar El conector de datos de llamadas: un único conjunto de herramientas que permite ver datos de calidad de llamadas Skype Empresarial Server través de herramientas del Panel de calidad de llamadas en línea (CQD) y análisis de llamadas (CA) de Skype Empresarial.

Para obtener más información acerca de las ventajas y requisitos previos de Call Data Connector, como los requisitos de roles y la configuración de la conectividad híbrida, vea [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Habilitar supervisión
 
Debe configurar la recopilación de datos de registro de datos de llamadas (CDR) y calidad de la experiencia (QoE) en la supervisión del grupo de servidores front-end, con bases de datos locales LCSCdr y QoEMetrics; de lo contrario, los Paneles de análisis de llamadas y calidad de llamadas no obtienen datos con los que trabajar. Antes de configurar El conector de datos de llamadas, siga los pasos que se indican en Implementar la supervisión en [Skype Empresarial Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar cdr y qoe, así como la supervisión básica.

> [!IMPORTANT]
> Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.

## <a name="enable-call-data-connector"></a>Habilitar El conector de datos de llamadas

Para configurar y habilitar Call Data Connector, usará los cmdlets siguientes:

| Cmdlet| Descripción|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet en línea que establece un recopilador de datos en línea.|
| Get-CsCloudCallDataConnection | Cmdlet en línea que recupera un recopilador de datos en línea existente.|  
| Get-CsCloudCallDataConnector | Cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection local. |
| Set-CsCloudCallDataConnector | Cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection local. |  
| Set-CsCloudCallDataConnectorConfiguration | Cmdlet local que permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.|

> [!NOTE]
> Para borrar la configuración e iniciar de nuevo, use el cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurar el entorno 

Para configurar el entorno para habilitar un recopilador de datos en línea, primero debe iniciar sesión en Skype Empresarial PowerShell en línea como administrador. Para obtener más información, [vea Manage Skype Empresarial Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Hay dos métodos para iniciar sesión en Skype Empresarial PowerShell en línea:

- Desde el Skype Empresarial Server de administración de 2019 (método recomendado)
- Desde otra sesión de PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Inicie sesión en Skype Empresarial PowerShell en línea desde el shell Skype Empresarial Server administración (método recomendado)

1. Si habilita el conector por primera vez, ejecute el siguiente comando:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Si recibe un error de que la conexión ya existe, significa que la conexión de datos de llamada ya existe para el inquilino. En este caso, ejecute el comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Inicie sesión en Skype Empresarial PowerShell en línea desde otra sesión de PowerShell (método opcional)

1.  Si habilita el conector por primera vez, ejecute el siguiente comando: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Si recibe un error de que la conexión ya existe, significa que la conexión de datos de llamada ya existe para el inquilino. En este caso, ejecute el comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

El resultado de los comandos anteriores contiene un valor de token, que necesitará al configurar el entorno local de la siguiente manera:

Desde dentro del shell Skype Empresarial Server administración, especifique el siguiente comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurar el ámbito

Puede habilitar Call Data Connector para un sitio determinado o para toda la implementación de Skype Empresarial Server mediante el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración Skype Empresarial Server administración. Por ejemplo, el siguiente comando habilita Call Data Connector en el ámbito global:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Además de la configuración global, las opciones de configuración de Call Data Connector se pueden asignar al ámbito del sitio. Esto proporciona flexibilidad de administración adicional en lo que respecta a la supervisión. Por ejemplo, un administrador puede habilitar el reenvío de Call Data Connector para el sitio Redmond pero deshabilitar el reenvío de Call Data Connector para el sitio de Dublín, como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global. Por ejemplo, supongamos que el reenvío de Call Data Connector está habilitado en el ámbito global, pero deshabilitado en el ámbito del sitio (para el sitio Redmond). Esto significa que la grabación de detalles de llamadas y la información de QoE no se reenviarán a los usuarios del sitio redmond. Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio redmond) tendrán su registro de detalles de llamadas y la información de QoE reenviada.

Los valores de la configuración más usada por Call Data Connector se muestran en la tabla siguiente:  

|Propiedad|Descripción|Valor predeterminado|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica si el conector de datos de llamadas está habilitado. Si es True, los registros de supervisión se reenviarán a la supervisión en línea.  <br/> |$False  <br/> |
| Identidad | Determina el nivel de ámbito del comando: global o site.   | global  |

## <a name="disable-call-data-connector"></a>Deshabilitar El conector de datos de llamadas

Deshabilitar El conector de datos de llamadas no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otro modo a la base de datos de supervisión back-end. Al deshabilitar El conector de datos de llamadas, Skype Empresarial Server de cargar datos de llamadas a la nube. 

Para deshabilitar Call Data Connector, use el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell Skype Empresarial Server administración. Por ejemplo, el siguiente comando deshabilita Call Data Connector en el ámbito global estableciendo la propiedad EnableCallDataConnector en $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Si desea reanudar la carga de datos de llamadas en la nube, establezca la propiedad EnableCallDataConnector en $True, como se muestra en el ejemplo siguiente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Ver datos locales a través del panel en línea

 Una vez habilitado el conector de datos de llamadas, puede ver los datos de llamadas locales en el panel análisis de llamadas o en el Panel de calidad de llamadas, tal como se describe en [Usar](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) análisis de llamadas para solucionar problemas de mala calidad y Activar y usar el Panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Más información

Para obtener más información sobre los cmdlets, puede usar el comando Get-Help desde el Shell Skype Empresarial Server administración. Por ejemplo:

Get-Help Get-CsCloudCallDataConnector | más

Get-Help Set-CsCloudCallDataConnector | más

Get-Help Set-CsCloudCallDataConnectorConfiguration | más