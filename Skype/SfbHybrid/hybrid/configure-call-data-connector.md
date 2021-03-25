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
description: Instrucciones para configurar Call Data Connector, que permite que la telemetría de Skype Empresarial local se vea con herramientas de Skype Empresarial Online.
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118999"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="a6ca6-103">Configurar el conector de datos de llamada</span><span class="sxs-lookup"><span data-stu-id="a6ca6-103">Configure Call Data Connector</span></span>

<span data-ttu-id="a6ca6-104">En este artículo se describe cómo configurar El conector de datos de llamadas: un único conjunto de herramientas que permite ver datos de calidad de llamadas de Skype Empresarial Server con las herramientas panel de calidad de llamadas (CQD) y análisis de llamadas (CA) de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="a6ca6-105">Para obtener más información acerca de las ventajas y requisitos previos de Call Data Connector, como los requisitos de roles y la configuración de la conectividad híbrida, vea [Plan Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a6ca6-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="a6ca6-106">Habilitar supervisión</span><span class="sxs-lookup"><span data-stu-id="a6ca6-106">Enable Monitoring</span></span>
 
<span data-ttu-id="a6ca6-107">Debe configurar la recopilación de datos de registro de datos de llamadas (CDR) y calidad de la experiencia (QoE) en la supervisión del grupo de servidores front-end, con bases de datos locales LCSCdr y QoEMetrics; de lo contrario, los Paneles de análisis de llamadas y calidad de llamadas no obtienen datos con los que trabajar.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="a6ca6-108">Antes de configurar El conector de datos de llamadas, siga los pasos que se indican en Implementar la supervisión en [Skype Empresarial Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) para configurar cdr y qoe, así como la supervisión básica.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6ca6-109">Call Data Connector no funcionará si la supervisión no está habilitada en el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="a6ca6-110">Habilitar El conector de datos de llamadas</span><span class="sxs-lookup"><span data-stu-id="a6ca6-110">Enable Call Data Connector</span></span>

<span data-ttu-id="a6ca6-111">Para configurar y habilitar Call Data Connector, usará los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="a6ca6-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a6ca6-112">Cmdlet</span></span>| <span data-ttu-id="a6ca6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ca6-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="a6ca6-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="a6ca6-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="a6ca6-115">Cmdlet en línea que establece un recopilador de datos en línea.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="a6ca6-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="a6ca6-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="a6ca6-117">Cmdlet en línea que recupera un recopilador de datos en línea existente.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="a6ca6-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="a6ca6-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="a6ca6-119">Cmdlet local que recupera la información de conexión creada por el cmdlet New-CsCloudCallDataConnection local.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="a6ca6-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="a6ca6-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="a6ca6-121">Cmdlet local que guarda una copia local de la información de conexión creada por el cmdlet New-CsCloudCallDataConnection local.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="a6ca6-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="a6ca6-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="a6ca6-123">Cmdlet local que permite habilitar o deshabilitar el conector y personalizar el nivel de ámbito.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="a6ca6-124">Para borrar la configuración e iniciar de nuevo, use el cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="a6ca6-125">Configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="a6ca6-125">Configure your environment</span></span> 

<span data-ttu-id="a6ca6-126">Para configurar el entorno para habilitar un recopilador de datos en línea, primero debe iniciar sesión en PowerShell de Skype Empresarial Online como administrador.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="a6ca6-127">Para obtener más información, vea [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="a6ca6-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="a6ca6-128">Hay dos métodos para iniciar sesión en PowerShell de Skype Empresarial Online:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="a6ca6-129">Desde el Shell de administración de Skype Empresarial Server 2019 (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="a6ca6-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="a6ca6-130">Desde otra sesión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6ca6-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="a6ca6-131">Inicie sesión en PowerShell de Skype Empresarial Online desde el shell de administración de Skype Empresarial Server (método recomendado)</span><span class="sxs-lookup"><span data-stu-id="a6ca6-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="a6ca6-132">Si habilita el conector por primera vez, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="a6ca6-133">Si recibe un error de que la conexión ya existe, significa que la conexión de datos de llamada ya existe para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="a6ca6-134">En este caso, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="a6ca6-135">Inicie sesión en PowerShell de Skype Empresarial Online desde otra sesión de PowerShell (método opcional)</span><span class="sxs-lookup"><span data-stu-id="a6ca6-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="a6ca6-136">Si habilita el conector por primera vez, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="a6ca6-137">Si recibe un error de que la conexión ya existe, significa que la conexión de datos de llamada ya existe para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="a6ca6-138">En este caso, ejecute el comando:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="a6ca6-139">El resultado de los comandos anteriores contiene un valor de token, que necesitará al configurar el entorno local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="a6ca6-140">Desde el shell de administración de Skype Empresarial Server, especifique el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="a6ca6-141">Configurar el ámbito</span><span class="sxs-lookup"><span data-stu-id="a6ca6-141">Configure the scope</span></span>

<span data-ttu-id="a6ca6-142">Puede habilitar Call Data Connector para un sitio determinado o para toda la implementación de Skype Empresarial Server mediante el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="a6ca6-143">Por ejemplo, el siguiente comando habilita Call Data Connector en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="a6ca6-144">Además de la configuración global, las opciones de configuración de Call Data Connector se pueden asignar al ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="a6ca6-145">Esto proporciona flexibilidad de administración adicional en lo que respecta a la supervisión.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="a6ca6-146">Por ejemplo, un administrador puede habilitar el reenvío de Call Data Connector para el sitio Redmond pero deshabilitar el reenvío de Call Data Connector para el sitio de Dublín, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="a6ca6-147">Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="a6ca6-148">Por ejemplo, supongamos que el reenvío de Call Data Connector está habilitado en el ámbito global, pero deshabilitado en el ámbito del sitio (para el sitio Redmond).</span><span class="sxs-lookup"><span data-stu-id="a6ca6-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="a6ca6-149">Esto significa que la grabación de detalles de llamadas y la información de QoE no se reenviarán a los usuarios del sitio redmond.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="a6ca6-150">Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por la configuración global en lugar de la configuración del sitio redmond) tendrán su registro de detalles de llamadas y la información de QoE reenviada.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="a6ca6-151">Los valores de la configuración más usada por Call Data Connector se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="a6ca6-152">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a6ca6-152">Property</span></span>|<span data-ttu-id="a6ca6-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ca6-153">Description</span></span>|<span data-ttu-id="a6ca6-154">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="a6ca6-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6ca6-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="a6ca6-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="a6ca6-156">Indica si el conector de datos de llamadas está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="a6ca6-157">Si es True, los registros de supervisión se reenviarán a la supervisión en línea.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="a6ca6-158">$False</span><span class="sxs-lookup"><span data-stu-id="a6ca6-158">$False</span></span>  <br/> |
| <span data-ttu-id="a6ca6-159">Identidad</span><span class="sxs-lookup"><span data-stu-id="a6ca6-159">Identity</span></span> | <span data-ttu-id="a6ca6-160">Determina el nivel de ámbito del comando: global o site.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="a6ca6-161">global</span><span class="sxs-lookup"><span data-stu-id="a6ca6-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="a6ca6-162">Deshabilitar El conector de datos de llamadas</span><span class="sxs-lookup"><span data-stu-id="a6ca6-162">Disable Call Data Connector</span></span>

<span data-ttu-id="a6ca6-163">Deshabilitar El conector de datos de llamadas no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otro modo a la base de datos de supervisión back-end.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="a6ca6-164">Al deshabilitar Call Data Connector, se detiene que Skype Empresarial Server cargue datos de llamadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="a6ca6-165">Para deshabilitar Call Data Connector, use el cmdlet Set-CsCloudCallDataConnectorConfiguration desde el shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="a6ca6-166">Por ejemplo, el siguiente comando deshabilita Call Data Connector en el ámbito global estableciendo la propiedad EnableCallDataConnector en $False:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="a6ca6-167">Si desea reanudar la carga de datos de llamadas en la nube, establezca la propiedad EnableCallDataConnector en $True, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="a6ca6-168">Ver datos locales a través del panel en línea</span><span class="sxs-lookup"><span data-stu-id="a6ca6-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="a6ca6-169">Una vez habilitado el conector de datos de llamadas, puede ver los datos de llamadas locales en el panel análisis de llamadas o en el Panel de calidad de llamadas, como se describe en [Usar](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) análisis de llamadas para solucionar problemas de mala calidad y Activar y usar el Panel de calidad de llamadas para Microsoft Teams y [Skype Empresarial Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="a6ca6-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a6ca6-170">Más información</span><span class="sxs-lookup"><span data-stu-id="a6ca6-170">For more information</span></span>

<span data-ttu-id="a6ca6-171">Para obtener más información sobre los cmdlets, puede usar el comando Get-Help desde el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a6ca6-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="a6ca6-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6ca6-172">For example:</span></span>

<span data-ttu-id="a6ca6-173">Get-Help Get-CsCloudCallDataConnector | más</span><span class="sxs-lookup"><span data-stu-id="a6ca6-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="a6ca6-174">Get-Help Set-CsCloudCallDataConnector | más</span><span class="sxs-lookup"><span data-stu-id="a6ca6-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="a6ca6-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | más</span><span class="sxs-lookup"><span data-stu-id="a6ca6-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>