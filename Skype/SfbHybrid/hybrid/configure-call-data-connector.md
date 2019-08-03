---
title: Configurar el conector de datos de llamada
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones para configurar el conector de datos de llamada, que permite ver la telemetría de Skype empresarial local con el uso de herramientas de Skype empresarial online.
ms.openlocfilehash: 1851e1e0c430107a27d706f7bc16ad974c5abaed
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2019
ms.locfileid: "36160801"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="1a4a3-103">Configurar el conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="1a4a3-103">Configure Call Data Connector</span></span>

<span data-ttu-id="1a4a3-104">En este artículo se describe cómo configurar el conector de datos de llamada, un conjunto de herramientas único que permite ver datos de calidad de llamadas de Skype empresarial Server mediante las herramientas del panel de calidad de llamadas de Skype empresarial online (CQD) y el análisis de llamadas (CA).</span><span class="sxs-lookup"><span data-stu-id="1a4a3-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="1a4a3-105">En la versión preliminar pública, solo está disponible el panel de análisis de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="1a4a3-106">Para obtener más información acerca de las ventajas y los requisitos previos de los conectores de datos de llamada, como los requisitos de roles y la configuración de la conectividad híbrida, vea [plan Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1a4a3-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="1a4a3-107">Habilitar la supervisión</span><span class="sxs-lookup"><span data-stu-id="1a4a3-107">Enable Monitoring</span></span>
 
<span data-ttu-id="1a4a3-108">Debe configurar la recopilación de datos de grabación de datos de llamadas (CDR) y calidad de la experiencia (QoE) en la supervisión del grupo de servidores front-end con bases de datos de LCSCdr y QoEMetrics locales; de lo contrario, los paneles análisis de llamadas y calidad de llamadas no recibirán los datos con los que trabajar.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="1a4a3-109">Antes de configurar el conector de datos de llamada, siga los pasos que se indican en [deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar tanto CDR como QoE, así como la supervisión básica.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a4a3-110">Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="1a4a3-111">Habilitar el conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="1a4a3-111">Enable Call Data Connector</span></span>

<span data-ttu-id="1a4a3-112">Para configurar y habilitar el conector de datos de llamada, deberá usar los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="1a4a3-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1a4a3-113">Cmdlet</span></span>| <span data-ttu-id="1a4a3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a4a3-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="1a4a3-115">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="1a4a3-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="1a4a3-116">Un cmdlet en línea que establece un recopilador de datos en línea.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="1a4a3-117">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="1a4a3-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="1a4a3-118">Un cmdlet en línea que recupera un recopilador de datos en línea existente.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="1a4a3-119">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="1a4a3-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="1a4a3-120">Un cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="1a4a3-121">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="1a4a3-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="1a4a3-122">Un cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="1a4a3-123">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1a4a3-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="1a4a3-124">Un cmdlet local que permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="1a4a3-125">Para borrar la configuración y comenzar de nuevo, use el cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-125">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="1a4a3-126">Configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="1a4a3-126">Configure your environment</span></span> 

<span data-ttu-id="1a4a3-127">Para configurar el entorno para habilitar un recopilador de datos en línea, primero debe iniciar sesión en PowerShell de Skype empresarial online como administrador.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-127">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="1a4a3-128">Para obtener más información, consulte [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="1a4a3-128">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="1a4a3-129">Hay dos métodos para iniciar sesión en PowerShell de Skype empresarial online:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-129">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="1a4a3-130">Desde el shell de administración de Skype empresarial Server 2019 (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="1a4a3-130">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="1a4a3-131">Desde otra sesión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a4a3-131">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="1a4a3-132">Iniciar sesión en PowerShell de Skype empresarial online desde el shell de administración de Skype empresarial Server (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="1a4a3-132">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="1a4a3-133">Si habilita el conector por primera vez, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-133">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="1a4a3-134">Si recibe un error que indica que la conexión ya existe, significa que la conexión de datos de llamada ya existe para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-134">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="1a4a3-135">En este caso, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-135">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="1a4a3-136">Iniciar sesión en PowerShell de Skype empresarial online desde otra sesión de PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="1a4a3-136">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="1a4a3-137">Si habilita el conector por primera vez, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-137">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="1a4a3-138">Si recibe un error que indica que la conexión ya existe, significa que la conexión de datos de llamada ya existe para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-138">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="1a4a3-139">En este caso, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-139">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="1a4a3-140">El resultado de los comandos anteriores contiene un valor de token, que necesitará para configurar el entorno local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-140">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="1a4a3-141">En el shell de administración de Skype empresarial Server, especifique el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-141">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="1a4a3-142">Configurar el ámbito</span><span class="sxs-lookup"><span data-stu-id="1a4a3-142">Configure the scope</span></span>

<span data-ttu-id="1a4a3-143">Puede habilitar el conector de datos de llamada para un sitio en particular o para toda la implementación de Skype empresarial Server usando el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-143">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="1a4a3-144">Por ejemplo, el siguiente comando habilita el conector de datos de llamada en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-144">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="1a4a3-145">Además de la configuración global, las opciones de configuración del conector de datos de llamadas se pueden asignar al ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-145">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="1a4a3-146">Esto proporciona una flexibilidad de administración adicional cuando se trata de la supervisión.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-146">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="1a4a3-147">Por ejemplo, un administrador puede habilitar el reenvío del conector de datos de llamada para el sitio de Redmond, pero deshabilitar el reenvío del conector de datos de llamada para el sitio de Dublin, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-147">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="1a4a3-148">Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-148">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="1a4a3-149">Por ejemplo, supongamos que el reenvío del conector de datos de llamada está habilitado en el ámbito global, pero deshabilitado en el ámbito del sitio (para el sitio de Redmond).</span><span class="sxs-lookup"><span data-stu-id="1a4a3-149">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="1a4a3-150">Esto significa que el registro detallado de llamadas y la información de QoE no se reenviarán a los usuarios en el sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-150">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="1a4a3-151">Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio de Redmond) tendrán su registro detallado de llamadas y la información de QoE reenviada.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-151">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="1a4a3-152">En la tabla siguiente se muestran los valores de las opciones más usadas por el conector de datos de llamada que se usan con más frecuencia:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-152">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="1a4a3-153">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1a4a3-153">Property</span></span>|<span data-ttu-id="1a4a3-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a4a3-154">Description</span></span>|<span data-ttu-id="1a4a3-155">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="1a4a3-155">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a4a3-156">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="1a4a3-156">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="1a4a3-157">Indica si el conector de datos de llamada está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-157">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="1a4a3-158">Si es true, los registros de supervisión se reenviarán a la supervisión en línea.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-158">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="1a4a3-159">$False</span><span class="sxs-lookup"><span data-stu-id="1a4a3-159">$False</span></span>  <br/> |
| <span data-ttu-id="1a4a3-160">Identidad</span><span class="sxs-lookup"><span data-stu-id="1a4a3-160">Identity</span></span> | <span data-ttu-id="1a4a3-161">Determina el nivel de ámbito del comando: global o de sitio.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-161">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="1a4a3-162">globales</span><span class="sxs-lookup"><span data-stu-id="1a4a3-162">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="1a4a3-163">Deshabilitar el conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="1a4a3-163">Disable Call Data Connector</span></span>

<span data-ttu-id="1a4a3-164">Al deshabilitar el conector de datos de llamada, no se desvincula el almacén de supervisión del grupo de servidores front-end, ni se desinstala o afecta de algún otro modo a la base de datos de supervisión back-end.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-164">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="1a4a3-165">Cuando deshabilita el conector de datos de llamada, deja que Skype empresarial Server cargue los datos de llamada en la nube.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-165">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="1a4a3-166">Deshabilite llamar a Data Connector usando el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-166">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="1a4a3-167">Por ejemplo, el siguiente comando deshabilita el conector de datos de llamada en el ámbito global al establecer la propiedad EnableCallDataConnector en $False:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-167">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="1a4a3-168">Si desea reanudar la carga de datos de llamada en la nube, vuelva a establecer la propiedad EnableCallDataConnector en $True, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-168">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="1a4a3-169">Ver datos locales a través del panel en línea</span><span class="sxs-lookup"><span data-stu-id="1a4a3-169">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="1a4a3-170">Una vez habilitado el conector de datos de llamadas, puede ver los datos de las llamadas locales en el panel de análisis de llamadas, tal como se describe en [use análisis de llamadas para solucionar problemas de mala calidad](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="1a4a3-170">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="1a4a3-171">Más información</span><span class="sxs-lookup"><span data-stu-id="1a4a3-171">For more information</span></span>

<span data-ttu-id="1a4a3-172">Para obtener más información sobre los cmdlets, puede usar el comando Get-Help desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1a4a3-172">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="1a4a3-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1a4a3-173">For example:</span></span>

<span data-ttu-id="1a4a3-174">Get-Help Get-CsCloudCallDataConnector | adicional</span><span class="sxs-lookup"><span data-stu-id="1a4a3-174">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="1a4a3-175">Get-Help Set-CsCloudCallDataConnector | adicional</span><span class="sxs-lookup"><span data-stu-id="1a4a3-175">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="1a4a3-176">Get-Help Set-CsCloudCallDataConnectorConfiguration | adicional</span><span class="sxs-lookup"><span data-stu-id="1a4a3-176">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
