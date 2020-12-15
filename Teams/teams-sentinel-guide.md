---
title: Azure Sentinel y Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Asesoría y aprendizaje de seguridad para administradores de IT acerca del uso de Sentinel para supervisar y buscar las amenazas que puedan surgir en Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aa8e733aeb3828bb1815001ba0299a9ee1aaf78
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852151"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="34216-103">Azure Sentinel y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34216-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="34216-104">Teams desempeña un papel fundamental tanto en la comunicación como en el uso compartido de datos en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34216-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="34216-105">Como el servicio de los equipos toca tantas tecnologías subyacentes en la nube, se puede beneficiar de análisis humanos y automatizados no solamente cuando se trata de la *búsqueda en los registros*, sino también en *el seguimiento en tiempo real de las reuniones*.</span><span class="sxs-lookup"><span data-stu-id="34216-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="34216-106">Estas soluciones las proporcionan los administradores de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="34216-107">¿Necesita un actualizador de Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="34216-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="34216-108">[Este artículo](https://docs.microsoft.com/azure/sentinel/overview) es la solución..</span><span class="sxs-lookup"><span data-stu-id="34216-108">[This article](https://docs.microsoft.com/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="34216-109">Registros de actividad de Sentinel y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34216-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="34216-110">El presente artículo se centra en la recopilación de los registros de actividad de los equipos en Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="34216-111">Además de permitirles a los administradores poner la gestión de seguridad bajo un solo panel de cristal (incluyendo cualquier dispositivo seleccionado de terceros, la Protección contra amenazas de Microsoft y otras cargas de trabajo de Microsoft 365), los libros de trabajo y de ejecución de Sentinel pueden hacer sistemática la supervisión de la seguridad.</span><span class="sxs-lookup"><span data-stu-id="34216-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="34216-112">Un buen primer paso de este proceso es recopilar los registros necesarios para analizarlos.</span><span class="sxs-lookup"><span data-stu-id="34216-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="34216-113">Pueden ver más de una suscripción de Microsoft 365 en la misma instancia de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="34216-114">Esto permite la supervisión [en tiempo real](https://docs.microsoft.com/azure/sentinel/livestream) y la búsqueda de amenazas en los archivos de registro históricos s.</span><span class="sxs-lookup"><span data-stu-id="34216-114">This will allow for [realtime monitoring](https://docs.microsoft.com/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="34216-115">Los administradores podrán buscar mediante [consultas entre recursos](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), que se encuentren en un único grupo de recursos, entre grupos de recursos o en otra suscripción.</span><span class="sxs-lookup"><span data-stu-id="34216-115">Administrators will be able to hunt using [cross-resource queries](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="34216-116">Paso 1: recopilar registros de equipos</span><span class="sxs-lookup"><span data-stu-id="34216-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="34216-117">Esta sección cuenta con tres partes:</span><span class="sxs-lookup"><span data-stu-id="34216-117">This section has three parts:</span></span>

1. <span data-ttu-id="34216-118">Habilitar registros de auditoría en **Microsoft 365** (M365).</span><span class="sxs-lookup"><span data-stu-id="34216-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="34216-119">Registro de una aplicación en **Microsoft Azure** para permitir la autenticación y autorización para la recopilación de registros.</span><span class="sxs-lookup"><span data-stu-id="34216-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="34216-120">Registro de la suscripción a la API que permitirá la recopilación de registros a través de la API de M365 a través de **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="34216-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="34216-121">Habilitar registros de auditoría en M365</span><span class="sxs-lookup"><span data-stu-id="34216-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="34216-122">Como Teams registra la actividad por M365, los registros de auditoría no se recopilan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34216-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="34216-123">Active esta característica mediante [estos pasos](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span><span class="sxs-lookup"><span data-stu-id="34216-123">Turn on this feature via [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span></span> <span data-ttu-id="34216-124">Los datos de los equipos se recopilan en la auditoría de M365, en *auditar. información general*.</span><span class="sxs-lookup"><span data-stu-id="34216-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="34216-125">Registrar una aplicación en Microsoft Azure para la recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="34216-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="34216-126">Antes de empezar, debe registrar el **Id. de la aplicación / cliente** y su **Id. de inquilino** para usarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="34216-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="34216-127">Asegúrese de capturarlas como se indica en los pasos de registro de la aplicación que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="34216-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="34216-128">Verá ambos ID.</span><span class="sxs-lookup"><span data-stu-id="34216-128">You will see both IDs.</span></span>
>- <span data-ttu-id="34216-129">Después de crear la aplicación, haga clic en registro de aplicaciones en la barra de inicio rápido > encontrar el nombre para mostrar de la nueva aplicación > copie la aplicación (cliente) ID.</span><span class="sxs-lookup"><span data-stu-id="34216-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="34216-130">Haga clic en información general en la barra lateral Inicio rápido > copie el ID. de directorio (inquilino).</span><span class="sxs-lookup"><span data-stu-id="34216-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="34216-131">Autentique y autorice una aplicación de Azure Active Directory (Azure AD) para recopilar datos de registro de la API.</span><span class="sxs-lookup"><span data-stu-id="34216-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="34216-132">Vaya a su hoja de *Azure AD* en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="34216-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="34216-133">Haga clic en *registros de aplicaciones* en la barra lateral de inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="34216-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="34216-134">Seleccione *Nuevo registro*.</span><span class="sxs-lookup"><span data-stu-id="34216-134">Select *New registration*.</span></span>
4. <span data-ttu-id="34216-135">Asigne un nombre a su equipo de recopilación de registros y haga clic en *registrarse*.</span><span class="sxs-lookup"><span data-stu-id="34216-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="34216-136">Haga clic en la ruta de acceso: *Permisos de la API* > *Agregar un permiso* > *API de administración de Office 365* > *Permisos de aplicación*.</span><span class="sxs-lookup"><span data-stu-id="34216-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="34216-137">Expanda fuente de actividades y compruebe *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="34216-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="34216-138">Seleccione *consentimiento de administrador general* aquí.</span><span class="sxs-lookup"><span data-stu-id="34216-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="34216-139">Cuando se le solicite, haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="34216-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="34216-140">Haga clic en *Certificados y secretos* en la barra lateral > en el botón *nuevo secreto de cliente*.</span><span class="sxs-lookup"><span data-stu-id="34216-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="34216-141">En la ventana nuevo secreto de cliente, escriba una descripción para el nuevo secreto de cliente, asegúrese de seleccionar "Nunca" para la expiración, y haga clic en *Agregar*.</span><span class="sxs-lookup"><span data-stu-id="34216-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34216-142">Es **crítico** copiar el nuevo secreto de cliente en una entrada del administrador de contraseñas que va debajo del nombre de la aplicación recién creada.</span><span class="sxs-lookup"><span data-stu-id="34216-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="34216-143">No podrá volver a ver este secreto después del cierre de la hoja de Azure (la *hoja* es el término de Azure para la ventana).</span><span class="sxs-lookup"><span data-stu-id="34216-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="34216-144">Registrar la API con PowerShell para recopilar registros de Teams</span><span class="sxs-lookup"><span data-stu-id="34216-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="34216-145">El último paso de la instalación es recopilar y registrar la suscripción API para que pueda recopilar sus datos de registro.</span><span class="sxs-lookup"><span data-stu-id="34216-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="34216-146">Esto se hace a través de las llamadas de REST de PowerShell a la API de Actividad de administración de M365.</span><span class="sxs-lookup"><span data-stu-id="34216-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="34216-147">Prepárese para suministrar el **ID de la Aplicación (cliente)**, el nuevo **Secreto de Cliente**, su **Dominio URL para M365** y los valores de **ID del Directorio (inquilino)** en el cmdlet de PowerShell que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="34216-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="34216-148">Paso 2: implementar un Cuaderno de estrategias de Sentinel para ingesta de los registros de Teams</span><span class="sxs-lookup"><span data-stu-id="34216-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="34216-149">Cuaderno de estrategias de Azure Sentinel (que también se denominan "Logic Apps") permiten que Azure ingiera datos de Teams recopilados.</span><span class="sxs-lookup"><span data-stu-id="34216-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="34216-150">Logic Apps consulta Office 365 para buscar los datos de auditoría que escribe en el área de trabajo de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="34216-151">Use [esta](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) plantilla de ARM para implementar su cuaderno de estrategias de Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="34216-152">Cosas para recordar:</span><span class="sxs-lookup"><span data-stu-id="34216-152">Things to remember:</span></span>

1. <span data-ttu-id="34216-153">Tendrá que recorrer la plantilla de ARM y reemplazar algunos de los valores con valores apropiados para su propio entorno.</span><span class="sxs-lookup"><span data-stu-id="34216-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="34216-154">Tendrá que dejar tiempo entre la ingesta de registros y ver los resultados en Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="34216-155">Espere entre 5 y 10 minutos, comprendiendo que si no hay datos durante los últimos 5 minutos, verá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="34216-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="34216-156">Compruebe los registros de auditoría y tenga en cuenta que, como la información de Teams se encuentra en la auditoría. Eventos generales, que se recopilan en más de un registro de Teams, los resultados deben aparecer en un plazo de entre 5 y 10 minutos en los sistemas que están en uso.</span><span class="sxs-lookup"><span data-stu-id="34216-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="34216-157">Si usa un entorno de texto, asegúrese de que usa Teams para generar registros.</span><span class="sxs-lookup"><span data-stu-id="34216-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Gráfico que muestra las clases de aplicación lógica.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="34216-159">Explicación de las acciones en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="34216-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="34216-160">• Periodicidad es el desencadenador de la aplicación lógica que indica al flujo de trabajo que se ejecute cada hora.</span><span class="sxs-lookup"><span data-stu-id="34216-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="34216-161">• La acción Hora actual es muy básica y simplemente obtiene la hora actual.</span><span class="sxs-lookup"><span data-stu-id="34216-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="34216-162">• Inicializar la variable crea una variable llamada NextPage y la establece en 1.</span><span class="sxs-lookup"><span data-stu-id="34216-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="34216-163">Esto se usará más tarde para manejar la paginación de la API del O365.</span><span class="sxs-lookup"><span data-stu-id="34216-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="34216-164">• Inicializar la variable 2 crea una variable vacía denominada Hora de inicio.</span><span class="sxs-lookup"><span data-stu-id="34216-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="34216-165">• Ejecutar consulta y mostrar resultados es una acción de Azure Monitor que realizará una consulta en el área de trabajo del último registro de O365 que se especificó desde la Logic App.</span><span class="sxs-lookup"><span data-stu-id="34216-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="34216-166">• La condición 4 se usa para comprobar si la consulta Ejecutar consulta y mostrar resultados devolvió algún dato.</span><span class="sxs-lookup"><span data-stu-id="34216-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="34216-167">Esto se hace para comprobar si esta es la primera vez que se usó la Logic App.</span><span class="sxs-lookup"><span data-stu-id="34216-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="34216-168">Si no se devuelve ningún dato, la variable StartTime se establecerá en: 24 horas.</span><span class="sxs-lookup"><span data-stu-id="34216-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="34216-169">Si se devuelven datos, StartTime se establecerá en el último registro TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="34216-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="34216-170">Esto se hace para que la consulta pueda obtener datos de la última entrada hasta ahora en la encuesta contra la API de O365 o en las últimas 24 horas si se trata de la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="34216-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="34216-171">• Inicializar la variable 3 crea una variable denominada AvailableUri.</span><span class="sxs-lookup"><span data-stu-id="34216-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="34216-172">Esta es una cadena con la dirección URL creada con el StartTime y CurrentTime como horas de inicio y finalización, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="34216-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="34216-173">• La condición Hasta es un bucle que permite a la aplicación lógica seguir el sondeo de la API para ver si hay más datos (paginación).</span><span class="sxs-lookup"><span data-stu-id="34216-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="34216-174">Mientras la variable NextPage sea 1 el bucle continuará.</span><span class="sxs-lookup"><span data-stu-id="34216-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="34216-175">Más tarde esta variable se actualizará si no quedan más páginas por recuperar.</span><span class="sxs-lookup"><span data-stu-id="34216-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="34216-176">• Dentro del bucle Hasta, el primer paso HTTP se conecta al AvailableURI.</span><span class="sxs-lookup"><span data-stu-id="34216-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="34216-177">Esta URI devuelve una lista del contenido disponible y cada URI de contenido.</span><span class="sxs-lookup"><span data-stu-id="34216-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="34216-178">Hay más información sobre cómo funciona esto en esta dirección URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="34216-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="34216-179">• A continuación, se realiza una comprobación para asegurarse de que se devuelven datos.</span><span class="sxs-lookup"><span data-stu-id="34216-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="34216-180">La condición comprueba si la longitud del cuerpo es 0.</span><span class="sxs-lookup"><span data-stu-id="34216-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="34216-181">Si es así, no hay datos que escribir en Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="34216-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="34216-182">Si el valor es mayor que 0, hay datos que procesar.</span><span class="sxs-lookup"><span data-stu-id="34216-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="34216-183">• Si se detectan datos, éstos deben ser procesados a continuación.</span><span class="sxs-lookup"><span data-stu-id="34216-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="34216-184">Analizar JSON define un esquema de los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="34216-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="34216-185">Esto permite a las aplicaciones lógicas usar los datos analizados como contenido dinámico en pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="34216-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="34216-186">• Dado que la lista devuelta de datos disponibles es una Matriz, se utiliza una acción de For Each para hacer un bucle en la lista de contenidos disponibles.</span><span class="sxs-lookup"><span data-stu-id="34216-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="34216-187">• A continuación se captura el contenido.</span><span class="sxs-lookup"><span data-stu-id="34216-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="34216-188">El HTTP se utiliza de nuevo para obtener el contentUri (una propiedad dinámica creada a partir del Analizar JSON), que es la dirección URL de los datos a recuperar.</span><span class="sxs-lookup"><span data-stu-id="34216-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="34216-189">• Analizar JSON también se usa para analizar los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="34216-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="34216-190">Puede encontrar algunos contenidos de muestra en esta URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="34216-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="34216-191">• Los datos devueltos también son matrices.</span><span class="sxs-lookup"><span data-stu-id="34216-191">• The data returned is also an array.</span></span> <span data-ttu-id="34216-192">También puede usarse un bucle For Each.</span><span class="sxs-lookup"><span data-stu-id="34216-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="34216-193">En este bucle, el flujo de trabajo toma el elemento actual de datos y usa la acción Enviar datos para escribir los datos en Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="34216-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="34216-194">• Como puede haber varias páginas de contenido disponible, una condición comprueba si la NextPageUri no es NULL.</span><span class="sxs-lookup"><span data-stu-id="34216-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="34216-195">Si es NULL o está vacío, NextPage se establece en 0, lo que finaliza el bucle Until.</span><span class="sxs-lookup"><span data-stu-id="34216-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="34216-196">Si contiene una dirección URL, la variable AvaibleUri se actualizará a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="34216-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="34216-197">De esta forma, la siguiente ejecución del bucle Until usa una dirección URL disponible próxima y no la URL de inicio.</span><span class="sxs-lookup"><span data-stu-id="34216-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="34216-198">En su lugar, puede usar una *Función de Azure* para recopilar estos registros, y si lo hace, la información sobre cómo implementar se [aquí](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)u [en la](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), según sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="34216-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="34216-199">Con el conector (cualquiera de las opciones anteriores elegidas) en ejecución, debería ver una tabla personalizada llamada O365API_CL en el área de trabajo de Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="34216-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="34216-200">Esto almacenará los registros de su Teams.</span><span class="sxs-lookup"><span data-stu-id="34216-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="34216-201">Paso 3: usar Sentinel para supervisar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34216-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="34216-202">Identidad es un vector de ataque importante que supervisa en lo que respecta a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="34216-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="34216-203">Como Azure Active Directory (Azure AD) es el respaldo del directorio de Microsoft 365, incluyendo a Teams, la recopilación y búsqueda de amenazas en los registros de Azure AD en torno a la autenticación serán útiles para detectar comportamientos sospechosos en torno a la identidad.</span><span class="sxs-lookup"><span data-stu-id="34216-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="34216-204">Puede usar el conector integrado para extraer los datos de Azure AD en Azure Sentinel y usar estos [la detección](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) y [cazar](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) consultas para comprobar si hay problemas.</span><span class="sxs-lookup"><span data-stu-id="34216-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="34216-205">En cuanto a los ataques específicos de Microsoft Teams, las amenazas a los datos, por ejemplo, Azure Sentinel también dispone de medios para vigilarlos y localizarlos.</span><span class="sxs-lookup"><span data-stu-id="34216-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="34216-206">Crear un analizador para los datos</span><span class="sxs-lookup"><span data-stu-id="34216-206">Create a parser for your data</span></span>

<span data-ttu-id="34216-207">Para darle sentido al gran conjunto de datos recogidos, lo primero que hay que hacer es darle un significado analizándolo.</span><span class="sxs-lookup"><span data-stu-id="34216-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="34216-208">Esto se lleva a cabo con una función del lenguaje de consulta de Kusto que facilite el uso de los datos.</span><span class="sxs-lookup"><span data-stu-id="34216-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="34216-209">Las funciones KQL son consultas de KQL guardadas como un tipo de datos denominado "Function".</span><span class="sxs-lookup"><span data-stu-id="34216-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="34216-210">Las funciones KQL tienen un alias que puede escribirse en el cuadro consulta en Sentinel para volver a ejecutar la consulta rápidamente.</span><span class="sxs-lookup"><span data-stu-id="34216-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="34216-211">Para obtener más información sobre las funciones KQL y cómo construir una función de analizador, lea [este artículo de la Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="34216-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="34216-212">El analizador que figura a continuación es un ejemplo personalizable cuyo objetivo es seleccionar un subconjunto de los campos de la API de gestión de Office 365 pertinentes para los *Teams*.</span><span class="sxs-lookup"><span data-stu-id="34216-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="34216-213">Asimismo, se recomienda usar el analizador [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), pero el analizador que se muestra a continuación puede modificarse para adecuarse a las distintas necesidades y preferencias.</span><span class="sxs-lookup"><span data-stu-id="34216-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="34216-214">Guardar el analizador como una función KQL, con un alias de TeamsData.</span><span class="sxs-lookup"><span data-stu-id="34216-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="34216-215">Se usará para las consultas siguientes.</span><span class="sxs-lookup"><span data-stu-id="34216-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="34216-216">Más detalle sobre la configuración y el uso de una función KQL como analizador, siga este artículo [Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="34216-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="34216-217">Consultas útiles de búsqueda de KQL</span><span class="sxs-lookup"><span data-stu-id="34216-217">Helpful hunting KQL queries</span></span>

<span data-ttu-id="34216-218">Use estas consultas para familiarizarse con el entorno de equipos y datos de su equipo.</span><span class="sxs-lookup"><span data-stu-id="34216-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="34216-219">El conocer cómo debe verse y comportarse el entorno es un excelente primer paso para reconocer una actividad sospechosa.</span><span class="sxs-lookup"><span data-stu-id="34216-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="34216-220">Desde allí, puede llegar a la búsqueda de amenazas.</span><span class="sxs-lookup"><span data-stu-id="34216-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="34216-221">Consulta de usuarios externos federados</span><span class="sxs-lookup"><span data-stu-id="34216-221">Federated external users query</span></span>

<span data-ttu-id="34216-222">Obtenga una lista de los sitios de Teams que tienen usuarios externos federados.</span><span class="sxs-lookup"><span data-stu-id="34216-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="34216-223">Estos usuarios tendrán un sufijo de nombre de dominio/UPN que *no* pertenezcan a su organización.</span><span class="sxs-lookup"><span data-stu-id="34216-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="34216-224">En esta consulta de ejemplo, el propietario de la organización es contoso.com.</span><span class="sxs-lookup"><span data-stu-id="34216-224">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="34216-225">Para obtener más información sobre los tipos de acceso externo e invitado en Teams, vea [este artículo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)o en la sección *tipos de participantes* en la guía de seguridad de [equipos](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span><span class="sxs-lookup"><span data-stu-id="34216-225">To learn more about External and Guest access types in Teams see [this article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations), or the *Participant Types* section in the [Teams Security Guide](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="34216-226">Que se hayan unido recientemente o cuya función haya cambiado</span><span class="sxs-lookup"><span data-stu-id="34216-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="34216-227">Consulte a un usuario específico para comprobar si se han agregado a un canal de Teams en los últimos 7 días, o en una semana:</span><span class="sxs-lookup"><span data-stu-id="34216-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="34216-228">Se ha cambiado la función de un usuario para un equipo en los últimos 7 días:</span><span class="sxs-lookup"><span data-stu-id="34216-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="34216-229">Usuarios externos de organizaciones desconocidas o nuevas</span><span class="sxs-lookup"><span data-stu-id="34216-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="34216-230">En Teams, puede agregar usuarios externos a su entorno o canales.</span><span class="sxs-lookup"><span data-stu-id="34216-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="34216-231">Las organizaciones suelen tener un número limitado de asociaciones clave y agregar usuarios de entre estos asociados.</span><span class="sxs-lookup"><span data-stu-id="34216-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="34216-232">Esta KQL se ocupa de los usuarios externos añadidos a los equipos que provienen de organizaciones que no han sido vistas o añadidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="34216-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="34216-233">Usuarios externos que se añadieron y que luego fueron eliminados </span><span class="sxs-lookup"><span data-stu-id="34216-233">External users who were added and then removed</span></span>

<span data-ttu-id="34216-234">Los atacantes con algún nivel de acceso existente pueden agregar una nueva cuenta externa a los Teams para tener acceso a los datos y exfiltrarlos.</span><span class="sxs-lookup"><span data-stu-id="34216-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="34216-235">También pueden quitar rápidamente a ese usuario para ocultar que ha realizado el acceso.</span><span class="sxs-lookup"><span data-stu-id="34216-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="34216-236">Esta búsqueda busca cuentas externas que se agregan a Teams y se quitan rápidamente para ayudar a identificar comportamientos sospechosos.</span><span class="sxs-lookup"><span data-stu-id="34216-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="34216-237">Nuevo bot o aplicación agregada</span><span class="sxs-lookup"><span data-stu-id="34216-237">New bot or application added</span></span>

<span data-ttu-id="34216-238">Los Teams tienen la capacidad de incluir aplicaciones o bots en un equipo para ampliar el conjunto de características.</span><span class="sxs-lookup"><span data-stu-id="34216-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="34216-239">Esto incluye las aplicaciones personalizadas y los bots.</span><span class="sxs-lookup"><span data-stu-id="34216-239">This includes custom apps and bots.</span></span> <span data-ttu-id="34216-240">En algunos casos, se podría utilizar una aplicación o un bot para establecer la persistencia en los Teams sin necesidad de una cuenta de usuario, así como para acceder a los archivos y otros datos.</span><span class="sxs-lookup"><span data-stu-id="34216-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="34216-241">Esta búsqueda para aplicaciones o robots que son nuevos en los Teams.</span><span class="sxs-lookup"><span data-stu-id="34216-241">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="34216-242">Cuentas de usuario que son propietarios de un gran número de Teams</span><span class="sxs-lookup"><span data-stu-id="34216-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="34216-243">Un atacante que intente aumentar sus privilegios puede asignarse a sí mismo privilegios de propietario de un gran número de Teams diversos, cuando, por lo general, los usuarios pueden crear y poseer un pequeño número de Teams alrededor de temas específicos.</span><span class="sxs-lookup"><span data-stu-id="34216-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse Teams, when, usually, users create and own a small number of Teams around specific topics.</span></span> <span data-ttu-id="34216-244">Esta consulta de KQL busca comportamientos sospechosos.</span><span class="sxs-lookup"><span data-stu-id="34216-244">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="34216-245">Muchas eliminaciones de equipo de un único usuario</span><span class="sxs-lookup"><span data-stu-id="34216-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="34216-246">Los atacantes pueden causar interrupciones y perjudicar proyectos y datos eliminando varios equipos.</span><span class="sxs-lookup"><span data-stu-id="34216-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="34216-247">Como los equipos suelen eliminarse por parte de los propietarios, una eliminación centralizada de varios equipos puede ser un problema.</span><span class="sxs-lookup"><span data-stu-id="34216-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="34216-248">Esta KQL busca un único usuario que elimine varios equipos.</span><span class="sxs-lookup"><span data-stu-id="34216-248">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="34216-249">Ampliar las oportunidades de búsqueda de hilos</span><span class="sxs-lookup"><span data-stu-id="34216-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="34216-250">Puede ampliar su búsqueda combinando consultas de recursos como el Directorio Activo Azure (Azure AD), u otras cargas de trabajo de Office 365 con las consultas de sus Teams.</span><span class="sxs-lookup"><span data-stu-id="34216-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="34216-251">Un ejemplo es la detección de patrones sospechosos en Azure AD SigninLogs y el uso de esa información durante la búsqueda para los propietarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="34216-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="34216-252">Asimismo, puede hacer que las detecciones de SigninLogs específicas para los Teams agreguen un filtro solo para los inicios de sesión basados en Teams mediante:</span><span class="sxs-lookup"><span data-stu-id="34216-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="34216-253">Para que le resulte más fácil explicar el uso de `where AppDisplayName starts with "Microsoft Teams"`, en la moneda siguiente, el error de inicio de sesión de una dirección IP de una dirección IP diferente es la misma que la de los Teams:</span><span class="sxs-lookup"><span data-stu-id="34216-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="34216-254">Información y actualizaciones importantes</span><span class="sxs-lookup"><span data-stu-id="34216-254">Important information and updates</span></span>

<span data-ttu-id="34216-255">**Gracias por colaborar en el contenido, Pedro Bryan, Nicholas DiCola y Matthew Gómez.**</span><span class="sxs-lookup"><span data-stu-id="34216-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="34216-256">Pedro Bryan, y las personas con las que colabora, seguirán desarrollando consultas de detección y búsqueda para los Teams, así que manténgase al día con este repositorio de [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="34216-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="34216-257">Monitor para las actualizaciones de la aplicación [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) y [Logic](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usan en este artículo.</span><span class="sxs-lookup"><span data-stu-id="34216-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="34216-258">También puede unirse a la [comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) y colaborar en ellas.</span><span class="sxs-lookup"><span data-stu-id="34216-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="34216-259">Muchas gracias.</span><span class="sxs-lookup"><span data-stu-id="34216-259">Thank you!</span></span> <span data-ttu-id="34216-260">Feliz búsqueda.</span><span class="sxs-lookup"><span data-stu-id="34216-260">Happy hunting.</span></span>

<span data-ttu-id="34216-261">[Registro de la aplicación en Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0).</span><span class="sxs-lookup"><span data-stu-id="34216-261">[Registering your application in Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)</span></span>

[<span data-ttu-id="34216-262">Activar o desactivar la búsqueda de registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="34216-262">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[<span data-ttu-id="34216-263">¿Qué es Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="34216-263">What is Azure Sentinel</span></span>](https://docs.microsoft.com/azure/sentinel/overview)
