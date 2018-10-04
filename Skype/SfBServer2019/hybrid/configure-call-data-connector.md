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
ms.openlocfilehash: 7c64ff1cfb7c300c575fb1b4512c590d1ddb867d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373302"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="36d4a-103">Configurar el conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="36d4a-103">Configure Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

<span data-ttu-id="36d4a-104">En este artículo se describe cómo configurar el conector de datos de llamadas--un único conjunto de herramientas que permite ver Skype para datos de calidad de llamadas de negocio Server mediante Skype para herramientas de negocio Online llamada calidad panel (CQD) y análisis de llamadas (CA).</span><span class="sxs-lookup"><span data-stu-id="36d4a-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="36d4a-105">En la versión preliminar pública, panel de análisis de llamadas sólo está disponible.</span><span class="sxs-lookup"><span data-stu-id="36d4a-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="36d4a-106">Para obtener más información acerca de las ventajas de conector de datos de llamadas y los requisitos previos, como los requisitos de las funciones y la configuración de conectividad híbrida, consulte [Planeación de conector de datos de llamada](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="36d4a-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="36d4a-107">Habilitar la supervisión</span><span class="sxs-lookup"><span data-stu-id="36d4a-107">Enable Monitoring</span></span> 

<span data-ttu-id="36d4a-108">Debe configurar el registro de datos de llamadas (CDR) y recopilación de datos de calidad de la experiencia (QoE); de lo contrario, el análisis de llamadas y paneles de calidad de llamadas no obtienen información para mostrar.</span><span class="sxs-lookup"><span data-stu-id="36d4a-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection; otherwise, the Call Analytics and Call Quality Dashboards won’t get information to display.</span></span> <span data-ttu-id="36d4a-109">Antes Configure conector de datos de llamada, siga los pasos proporcionados en [Deploy supervisión en Skype para Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar CDR y QoE.</span><span class="sxs-lookup"><span data-stu-id="36d4a-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE.</span></span>


## <a name="enable-call-data-connector"></a><span data-ttu-id="36d4a-110">Habilitar conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="36d4a-110">Enable Call Data Connector</span></span>

<span data-ttu-id="36d4a-111">Para configurar y habilitar el conector de datos de llamadas, va a usar los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="36d4a-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="36d4a-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="36d4a-112">Cmdlet</span></span>| <span data-ttu-id="36d4a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="36d4a-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="36d4a-114">Nueva CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="36d4a-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="36d4a-115">Un cmdlet en línea que establece un recopilador de datos en línea.</span><span class="sxs-lookup"><span data-stu-id="36d4a-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="36d4a-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="36d4a-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="36d4a-117">Un cmdlet en línea que recupera un recopilador de datos en línea existente.</span><span class="sxs-lookup"><span data-stu-id="36d4a-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="36d4a-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="36d4a-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="36d4a-119">Un cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="36d4a-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="36d4a-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="36d4a-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="36d4a-121">Un cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="36d4a-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="36d4a-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="36d4a-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="36d4a-123">Un cmdlet local que le permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.</span><span class="sxs-lookup"><span data-stu-id="36d4a-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="36d4a-124">Configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="36d4a-124">Configure your environment</span></span> 

<span data-ttu-id="36d4a-125">Para configurar el entorno para habilitar a un recopilador de datos en línea, debe primero inicie sesión en Skype para profesionales Online PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="36d4a-125">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="36d4a-126">Para obtener más información, vea [Administrar Skype para profesionales en línea con Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="36d4a-126">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="36d4a-127">Existen dos métodos para iniciar sesión en Skype para PowerShell en línea de negocio:</span><span class="sxs-lookup"><span data-stu-id="36d4a-127">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="36d4a-128">Desde el Skype para shell de administración de Business Server 2019 (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="36d4a-128">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="36d4a-129">Desde otra sesión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d4a-129">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="36d4a-130">Inicie sesión Skype para PowerShell en línea de negocio desde la Skype para Business Server management shell (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="36d4a-130">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="36d4a-131">Si habilita el conector por primera vez, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36d4a-131">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="36d4a-132">Si recibe un error que la conexión ya existe, esto significa que la conexión de datos llamada ya existe para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="36d4a-132">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="36d4a-133">En este caso, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="36d4a-133">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="36d4a-134">Inicie sesión Skype para PowerShell en línea de negocio desde otra sesión de PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="36d4a-134">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="36d4a-135">Si habilita el conector por primera vez, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36d4a-135">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="36d4a-136">Si recibe un error que la conexión ya existe, esto significa que la conexión de datos llamada ya existe para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="36d4a-136">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="36d4a-137">En este caso, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="36d4a-137">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="36d4a-138">El resultado de los comandos anteriores contiene un valor de símbolo (token) que necesitará al configurar su entorno local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="36d4a-138">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="36d4a-139">Desde dentro de la Skype para shell de administración de Business Server, especifique el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36d4a-139">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="36d4a-140">Configurar el ámbito</span><span class="sxs-lookup"><span data-stu-id="36d4a-140">Configure the scope</span></span>

<span data-ttu-id="36d4a-141">Puede habilitar llame al conector de datos para un sitio concreto o para su Skype completo para la implementación de servidor empresarial mediante el cmdlet Set-CsCloudCallDataConnectorConfiguration desde dentro de la Skype para shell de administración de Business Server.</span><span class="sxs-lookup"><span data-stu-id="36d4a-141">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="36d4a-142">Por ejemplo, el siguiente comando permite llamar al conector de datos en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="36d4a-142">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="36d4a-143">Además de la configuración global, opciones de configuración del conector de datos de llamadas pueden asignarse al ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="36d4a-143">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="36d4a-144">Esto proporciona mayor flexibilidad de administración, lo que respecta a la supervisión.</span><span class="sxs-lookup"><span data-stu-id="36d4a-144">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="36d4a-145">Por ejemplo, un administrador puede habilitar el reenvío de llamadas de conector de datos para el sitio de Redmond, pero deshabilitar el reenvío de llamadas conector de datos para el sitio de Dublin, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36d4a-145">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="36d4a-146">Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="36d4a-146">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="36d4a-147">Por ejemplo, suponga que el desvío de llamadas de conector de datos está habilitado en el ámbito global, pero está deshabilitado en el ámbito del sitio (para el sitio de Redmond).</span><span class="sxs-lookup"><span data-stu-id="36d4a-147">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="36d4a-148">Esto significa que información de QoE y registro de detalles de llamadas no se desviarán para los usuarios en el sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="36d4a-148">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="36d4a-149">Sin embargo, los usuarios en otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio Redmond) tendrán sus detalles de las llamadas y la información de QoE reenviado.</span><span class="sxs-lookup"><span data-stu-id="36d4a-149">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="36d4a-150">Los valores para la configuración usada con más frecuencia utilizado por el conector de datos de llamadas se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="36d4a-150">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="36d4a-151">Propiedad</span><span class="sxs-lookup"><span data-stu-id="36d4a-151">Property</span></span>|<span data-ttu-id="36d4a-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="36d4a-152">Description</span></span>|<span data-ttu-id="36d4a-153">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="36d4a-153">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36d4a-154">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="36d4a-154">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="36d4a-155">Indica si está habilitado el conector de datos de llamada.</span><span class="sxs-lookup"><span data-stu-id="36d4a-155">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="36d4a-156">Si es True, los registros de supervisión se desviarán a la supervisión en línea.</span><span class="sxs-lookup"><span data-stu-id="36d4a-156">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="36d4a-157">$False</span><span class="sxs-lookup"><span data-stu-id="36d4a-157">$False</span></span>  <br/> |
| <span data-ttu-id="36d4a-158">Identity </span><span class="sxs-lookup"><span data-stu-id="36d4a-158">Identity</span></span> | <span data-ttu-id="36d4a-159">Determina el nivel de ámbito para el comando: global o sitio.</span><span class="sxs-lookup"><span data-stu-id="36d4a-159">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="36d4a-160">global</span><span class="sxs-lookup"><span data-stu-id="36d4a-160">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="36d4a-161">Deshabilitar el conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="36d4a-161">Disable Call Data Connector</span></span>

<span data-ttu-id="36d4a-162">Deshabilitar el conector de datos de llamadas no desasociar al almacén de supervisión desde el grupo de servidores Front-End, ni desinstalar o en caso contrario, afectan a la base de datos de supervisión de back-end.</span><span class="sxs-lookup"><span data-stu-id="36d4a-162">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="36d4a-163">Cuando se deshabilita el conector de datos de llamadas, detenga Skype para Business Server de carga de datos de la llamada a la nube.</span><span class="sxs-lookup"><span data-stu-id="36d4a-163">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="36d4a-164">Deshabilitar el conector de datos de llamadas usando el cmdlet Set-CsCloudCallDataConnectorConfiguration desde dentro de la Skype para shell de administración de Business Server.</span><span class="sxs-lookup"><span data-stu-id="36d4a-164">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="36d4a-165">Por ejemplo, el siguiente comando deshabilita el conector de datos de llamadas en el ámbito global estableciendo la propiedad EnableCallDataConnector en $False:</span><span class="sxs-lookup"><span data-stu-id="36d4a-165">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="36d4a-166">Si desea reanudar la carga de datos de la llamada a la nube, Establece la propiedad EnableCallDataConnector atrás en $True, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36d4a-166">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="36d4a-167">Vista de datos locales a través del panel en línea</span><span class="sxs-lookup"><span data-stu-id="36d4a-167">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="36d4a-168">Después de llamar al conector de datos está habilitado, puede ver los datos de llamada local en el panel de análisis de llamadas, tal como se describe en el [Análisis de uso de llamadas para solucionar problemas de calidad deficiente](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="36d4a-168">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="36d4a-169">Más información</span><span class="sxs-lookup"><span data-stu-id="36d4a-169">For more information</span></span>

<span data-ttu-id="36d4a-170">Para obtener más información sobre los cmdlets, puede usar el comando Get-Help desde el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="36d4a-170">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="36d4a-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="36d4a-171">For example:</span></span>

<span data-ttu-id="36d4a-172">Get-Help Get-CsCloudCallDataConnector | más</span><span class="sxs-lookup"><span data-stu-id="36d4a-172">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="36d4a-173">Get-Help Set-CsCloudCallDataConnector | más</span><span class="sxs-lookup"><span data-stu-id="36d4a-173">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="36d4a-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | más</span><span class="sxs-lookup"><span data-stu-id="36d4a-174">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>