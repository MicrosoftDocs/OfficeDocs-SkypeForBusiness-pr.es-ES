---
title: Azure Sentinel y Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Asesoría y aprendizaje de seguridad para ITAdmins sobre el uso de Sentinel para supervisar y detectar amenazas que pueden surgir en Teams.
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
ms.openlocfilehash: a59609404e51287be02dafc961561bd03e9efb9b
ms.sourcegitcommit: 8b172e9a0d0626c9a88998600d4b17c6c8cdadd2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761488"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel y Microsoft Teams

Teams desempeña un papel fundamental tanto en la comunicación como en el uso compartido de datos en la nube de Microsoft 365. Como el servicio de los equipos toca tantas tecnologías subyacentes en la nube, se puede beneficiar de análisis humanos y automatizados no solamente cuando se trata de la *búsqueda en los registros*, sino también en* el seguimiento en tiempo real de las reuniones*. Estas soluciones las proporcionan los administradores de Azure Sentinel.

> [!NOTE]
> ¿Necesita un actualizador de Azure Sentinel? [Este artículo](https://docs.microsoft.com/azure/sentinel/overview) es la solución..

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Registros de actividad de Sentinel y Microsoft Teams

El presente artículo se centra en la recopilación de los registros de actividad de los equipos en Azure Sentinel. Además de permitirles a los administradores poner la gestión de seguridad bajo un solo panel de cristal (incluyendo cualquier dispositivo seleccionado de terceros, la Protección contra amenazas de Microsoft y otras cargas de trabajo de Microsoft 365), los libros de trabajo y de ejecución de Sentinel pueden hacer sistemática la supervisión de la seguridad. Un buen primer paso de este proceso es recopilar los registros necesarios para analizarlos.

> [!NOTE]
> Pueden ver más de una suscripción de Microsoft 365 en la misma instancia de Azure Sentinel. Esto permite la supervisión [en tiempo real](https://docs.microsoft.com/azure/sentinel/livestream) y la búsqueda de amenazas en los archivos de registro históricos s. Los administradores podrán buscar mediante [consultas entre recursos](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), que se encuentren en un único grupo de recursos, entre grupos de recursos o en otra suscripción.

## <a name="step-1-collect-teams-logs"></a>Paso 1: recopilar registros de equipos

Esta sección cuenta con tres partes:

1. Habilitar registros de auditoría en **Microsoft 365** (M365).
2. Registro de una aplicación en **Microsoft Azure** para permitir la autenticación y autorización para la recopilación de registros.
3. Registro de la suscripción a la API que permitirá la recopilación de registros a través de la API de M365 a través de **PowerShell**.

### <a name="enable-audit-logs-in-m365"></a>Habilitar registros de auditoría en M365

Como Teams registra la actividad por M365, los registros de auditoría no se recopilan de forma predeterminada. Active esta característica mediante [estos pasos](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0). Los datos de los equipos se recopilan en la auditoría de M365, en *auditar. información general*.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>Registrar una aplicación en Microsoft Azure para la recopilación de registros

> [!TIP]
> Antes de empezar, debe registrar el **Id. de la aplicación / cliente**y su **Id. de inquilino** para usarlo más adelante. Asegúrese de capturarlas como se indica en los pasos de registro de la aplicación que se muestran a continuación. Verá ambos ID.
>- Después de crear la aplicación, haga clic en registro de aplicaciones en la barra de inicio rápido > encontrar el nombre para mostrar de la nueva aplicación > copie la aplicación (cliente) ID.
>- Haga clic en información general en la barra lateral Inicio rápido > copie el ID. de directorio (inquilino).

Autentique y autorice una aplicación de Azure Active Directory (Azure AD) para recopilar datos de registro de la API.

1. Vaya a su hoja de *Azure AD* en el portal de Azure.
2. Haga clic en *registros de aplicaciones* en la barra lateral de inicio rápido.
3. Seleccione *Nuevo registro*.
4. Asigne un nombre a su equipo de recopilación de registros y haga clic en *registrarse*.
5. Haga clic en la ruta de acceso: *Permisos de la API* > *Agregar un permiso* > *API de administración de Office 365 * > *Permisos de aplicación*.
6. Expanda fuente de actividades y compruebe *ActivityFeed.Read*.
7. Seleccione *consentimiento de administrador general* aquí. Cuando se le solicite, haga clic en Sí.
8. Haga clic en *Certificados y secretos* en la barra lateral > en el botón *nuevo secreto de cliente*.
9. En la ventana nuevo secreto de cliente, escriba una descripción para el nuevo secreto de cliente, asegúrese de seleccionar "Nunca" para la expiración, y haga clic en *Agregar*.

> [!IMPORTANT]
> Es **crítico** copiar el nuevo secreto de cliente en una entrada del administrador de contraseñas que va debajo del nombre de la aplicación recién creada. No podrá volver a ver este secreto después del cierre de la hoja de Azure (la *hoja* es el término de Azure para la ventana).

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Registrar la API con PowerShell para recopilar registros de Teams

El último paso de la instalación es recopilar y registrar la suscripción API para que pueda recopilar sus datos de registro. Esto se hace a través de las llamadas de REST de PowerShell a la API de Actividad de administración de M365.

Prepárese para suministrar el **ID de la Aplicación (cliente)**, el nuevo **Secreto de Cliente**, su **Dominio URL para M365** y los valores de **ID del Directorio (inquilino)** en el cmdlet de PowerShell que aparece a continuación.

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>Paso 2: implementar un Cuaderno de estrategias de Sentinel para ingesta de los registros de Teams

Cuaderno de estrategias de Azure Sentinel (que también se denominan "Logic Apps") permiten que Azure ingiera datos de Teams recopilados. Logic Apps consulta Office 365 para buscar los datos de auditoría que escribe en el área de trabajo de Azure Sentinel.

Use [esta](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) plantilla de ARM para implementar su cuaderno de estrategias de Sentinel.

Cosas para recordar:

1. Tendrá que recorrer la plantilla de ARM y reemplazar algunos de los valores con valores apropiados para su propio entorno.
2. Tendrá que dejar tiempo entre la ingesta de registros y ver los resultados en Azure Sentinel.

   Espere entre 5 y 10 minutos, comprendiendo que si no hay datos durante los últimos 5 minutos, verá un mensaje de error. Compruebe los registros de auditoría y tenga en cuenta que, como la información de Teams se encuentra en la auditoría. Eventos generales, que se recopilan en más de un registro de Teams, los resultados deben aparecer en un plazo de entre 5 y 10 minutos en los sistemas que están en uso. Si usa un entorno de texto, asegúrese de que usa Teams para generar registros.

![Gráfico que muestra las clases de aplicación lógica.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> Explicación de las acciones en el gráfico: 
  </summary>

  • Periodicidad es el desencadenador de la aplicación lógica que indica al flujo de trabajo que se ejecute cada hora.
  <p>
• La acción Hora actual es muy básica y simplemente obtiene la hora actual.
  <p>
• Inicializar la variable crea una variable llamada NextPage y la establece en 1. Esto se usará más tarde para manejar la paginación de la API del O365.
  <p>
• Inicializar la variable 2 crea una variable vacía denominada Hora de inicio.
  <p>
• Ejecutar consulta y mostrar resultados es una acción de Azure Monitor que realizará una consulta en el área de trabajo del último registro de O365 que se especificó desde la Logic App.
  <p>
• La condición 4 se usa para comprobar si la consulta Ejecutar consulta y mostrar resultados devolvió algún dato. Esto se hace para comprobar si esta es la primera vez que se usó la Logic App. Si no se devuelve ningún dato, la variable StartTime se establecerá en: 24 horas. Si se devuelven datos, StartTime se establecerá en el último registro TimeGenerated. Esto se hace para que la consulta pueda obtener datos de la última entrada hasta ahora en la encuesta contra la API de O365 o en las últimas 24 horas si se trata de la primera ejecución.
  <p>
• Inicializar la variable 3 crea una variable denominada AvailableUri. Esta es una cadena con la dirección URL creada con el StartTime y CurrentTime como horas de inicio y finalización, respectivamente.
  <p>
• La condición Hasta es un bucle que permite a la aplicación lógica seguir el sondeo de la API para ver si hay más datos (paginación). Mientras la variable NextPage sea 1 el bucle continuará. Más tarde esta variable se actualizará si no quedan más páginas por recuperar.
  <p>
• Dentro del bucle Hasta, el primer paso HTTP se conecta al AvailableURI. Esta URI devuelve una lista del contenido disponible y cada URI de contenido. Hay más información sobre cómo funciona esto en esta dirección URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• A continuación, se realiza una comprobación para asegurarse de que se devuelven datos. La condición comprueba si la longitud del cuerpo es 0. Si es así, no hay datos que escribir en Log Analytics. Si el valor es mayor que 0, hay datos que procesar.
  <p>
• Si se detectan datos, éstos deben ser procesados a continuación. Analizar JSON define un esquema de los datos devueltos. Esto permite a las aplicaciones lógicas usar los datos analizados como contenido dinámico en pasos posteriores.
  <p>
• Dado que la lista devuelta de datos disponibles es una Matriz, se utiliza una acción de For Each para hacer un bucle en la lista de contenidos disponibles.
  <p>
• A continuación se captura el contenido.  El HTTP se utiliza de nuevo para obtener el contentUri (una propiedad dinámica creada a partir del Analizar JSON), que es la dirección URL de los datos a recuperar.
  <p>
• Analizar JSON también se usa para analizar los datos devueltos. Puede encontrar algunos contenidos de muestra en esta URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Los datos devueltos también son matrices. También puede usarse un bucle For Each. En este bucle, el flujo de trabajo toma el elemento actual de datos y usa la acción Enviar datos para escribir los datos en Log Analytics.
  <p>
• Como puede haber varias páginas de contenido disponible, una condición comprueba si la NextPageUri no es NULL. Si es NULL o está vacío, NextPage se establece en 0, lo que finaliza el bucle Until. Si contiene una dirección URL, la variable AvaibleUri se actualizará a la dirección URL. De esta forma, la siguiente ejecución del bucle Until usa una dirección URL disponible próxima y no la URL de inicio.

  </details>

> [!TIP]
> En su lugar, puede usar una *Función de Azure* para recopilar estos registros, y si lo hace, la información sobre cómo implementar se [aquí](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)u [en la](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), según sus preferencias.

Con el conector (cualquiera de las opciones anteriores elegidas) en ejecución, debería ver una tabla personalizada llamada O365API_CL en el área de trabajo de Azure Sentinel. Esto almacenará los registros de su Teams.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>Paso 3: usar Sentinel para supervisar Microsoft Teams

Identidad es un vector de ataque importante que supervisa en lo que respecta a Microsoft Teams. Como Azure Active Directory (Azure AD) es el respaldo del directorio de Microsoft 365, incluidos los Teams, la recopilación y la búsqueda de amenazas en los registros de Azure AD en torno a la autenticación serán útiles para capturar comportamientos sospechosos en torno a la identidad. Puede usar el conector integrado para extraer los datos de Azure AD en Azure Sentinel y usar estos [la detección](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) y [cazar](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) consultas para comprobar si hay problemas.

En cuanto a los ataques específicos de Microsoft Teams, las amenazas a los datos, por ejemplo, Azure Sentinel también dispone de medios para vigilarlos y localizarlos.

### <a name="create-a-parser-for-your-data"></a>Crear un analizador para los datos

Para darle sentido al gran conjunto de datos recogidos, lo primero que hay que hacer es darle un significado analizándolo. Esto se lleva a cabo con una función del lenguaje de consulta de Kusto que facilite el uso de los datos.

> [!NOTE]
> Las funciones KQL son consultas de KQL guardadas como un tipo de datos denominado "Function". Las funciones KQL tienen un alias que puede escribirse en el cuadro consulta en Sentinel para volver a ejecutar la consulta rápidamente. Para obtener más información sobre las funciones KQL y cómo construir una función de analizador, lea [este artículo de la Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).
 
 El analizador que figura a continuación es un ejemplo personalizable cuyo objetivo es seleccionar un subconjunto de los campos de la API de gestión de Office 365 pertinentes para los *Teams*. Asimismo, se recomienda usar el analizador [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), pero el analizador que se muestra a continuación puede modificarse para adecuarse a las distintas necesidades y preferencias.

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
 Guardar el analizador como una función KQL, con un alias de TeamsData. Se usará para las consultas siguientes. Más detalle sobre la configuración y el uso de una función KQL como analizador, siga este artículo [Tech Community](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).

## <a name="helfpul-hunting-kql-queries"></a>Consultas de KQL de búsqueda Helfpul

Use estas consultas para familiarizarse con el entorno de equipos y datos de su equipo. El conocer cómo debe verse y comportarse el entorno es un excelente primer paso para reconocer una actividad sospechosa. Desde allí, puede llegar a la búsqueda de amenazas.

#### <a name="federated-external-users-query"></a>Consulta de usuarios externos federados

Obtenga una lista de los sitios de Teams que tienen usuarios externos federados. Estos usuarios tendrán un sufijo de nombre de dominio/UPN que *no* pertenezcan a su organización. En esta consulta de ejemplo, el propietario de la organización es contoso.com.

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
> Para obtener más información sobre los tipos de acceso externo e invitado en Teams, vea [este artículo](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)o en la sección *tipos de participantes* en la guía de seguridad de [equipos](https://docs.microsoft.com/microsoftteams/teams-security-guide).

#### <a name="who-recently-joined--whose-role-changed"></a>Que se hayan unido recientemente o cuya función haya cambiado

Consulte a un usuario específico para comprobar si se han agregado a un canal de Teams en los últimos 7 días, o en una semana:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

Se ha cambiado la función de un usuario para un equipo en los últimos 7 días:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>Usuarios externos de organizaciones desconocidas o nuevas

En Teams, puede agregar usuarios externos a su entorno o canales. Las organizaciones suelen tener un número limitado de asociaciones clave y agregar usuarios de entre estos asociados. Esta KQL se ocupa de los usuarios externos añadidos a los equipos que provienen de organizaciones que no han sido vistas o añadidas anteriormente.

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

#### <a name="external-users-who-were-added-and-then-removed"></a>Usuarios externos que se añadieron y que luego fueron eliminados 

Los atacantes con algún nivel de acceso existente pueden agregar una nueva cuenta externa a los Teams para tener acceso a los datos y exfiltrarlos. También pueden quitar rápidamente a ese usuario para ocultar que ha realizado el acceso. Esta búsqueda busca cuentas externas que se agregan a Teams y se quitan rápidamente para ayudar a identificar comportamientos sospechosos.

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

#### <a name="new-bot-or-application-added"></a>Nuevo bot o aplicación agregada

Los Teams tienen la capacidad de incluir aplicaciones o bots en un equipo para ampliar el conjunto de características. Esto incluye las aplicaciones personalizadas y los bots. En algunos casos, se podría utilizar una aplicación o un bot para establecer la persistencia en los Teams sin necesidad de una cuenta de usuario, así como para acceder a los archivos y otros datos. Esta búsqueda para aplicaciones o robots que son nuevos en los Teams.

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Cuentas de usuario que son propietarios de un gran número de Teams

Un atacante que intente aumentar sus privilegios puede asignarse a sí mismo privilegios de propietario de un gran número de Teams diversos, cuando, por lo general, los usuarios pueden crear y poseer un pequeño número de Teams alrededor de temas específicos. Esta consulta de KQL busca comportamientos sospechosos.

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

#### <a name="many-team-deletions-by-a-single-user"></a>Muchas eliminaciones de equipo de un único usuario

Los atacantes pueden causar interrupciones y perjudicar proyectos y datos eliminando varios equipos. Como los equipos suelen eliminarse por parte de los propietarios, una eliminación centralizada de varios equipos puede ser un problema. Esta KQL busca un único usuario que elimine varios equipos.

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

#### <a name="expanding-your-thread-hunting-opportunities"></a>Ampliar las oportunidades de búsqueda de hilos

Puede ampliar su búsqueda combinando consultas de recursos como el Directorio Activo Azure (Azure AD), u otras cargas de trabajo de Office 365 con las consultas de sus Teams. Un ejemplo es la detección de patrones sospechosos en Azure AD SigninLogs y el uso de esa información durante la búsqueda para los propietarios de Teams.

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

Asimismo, puede hacer que las detecciones de SigninLogs específicas para los Teams agreguen un filtro solo para los inicios de sesión basados en Teams mediante:

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

Para que le resulte más fácil explicar el uso de `where AppDisplayName starts with "Microsoft Teams"`, en la moneda siguiente, el error de inicio de sesión de una dirección IP de una dirección IP diferente es la misma que la de los Teams:

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

## <a name="important-information-and-updates"></a>Información y actualizaciones importantes

**Gracias por colaborar en el contenido, Pedro Bryan, Nicholas DiCola y Matthew Gómez.** Pedro Bryan, y las personas con las que colabora, seguirán desarrollando consultas de detección y búsqueda para los Teams, así que manténgase al día con este repositorio de [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) para las actualizaciones.  Monitor para las actualizaciones de la aplicación [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) y [Logic](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) usan en este artículo. También puede unirse a la [comunidad de Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki) y colaborar en ellas. Muchas gracias. Feliz búsqueda.

[Registro de la aplicación en Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0).

[Activar o desactivar la búsqueda de registros de auditoría](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[¿Qué es Azure Sentinel?](https://docs.microsoft.com/azure/sentinel/overview)