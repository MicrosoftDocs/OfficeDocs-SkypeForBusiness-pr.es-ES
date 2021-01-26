---
title: Realizar una investigación de exhibición de documentos electrónicos sobre el contenido
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre qué hacer cuando es necesario realizar exhibición de documentos electrónicos, por ejemplo, cuando es necesario enviar toda la información almacenada por medios electrónicos para un procedimiento legal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980464"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams

Las empresas grandes a menudo se exponen a procedimientos legales de alto nivel que exigen el envío de toda la información almacenada electrónicamente (ESI). El contenido de Microsoft Teams se puede buscar y usar durante las investigaciones de eDiscovery.

## <a name="overview"></a>Descripción general

Todos los chats grupales o de Microsoft Teams 1:1 se descargan en el diario en los buzones de los usuarios correspondientes. Todos los mensajes del canal estándar se envían en el diario al buzón del grupo que representa el equipo. Los archivos cargados en canales estándar están cubiertos por la funcionalidad de exhibición de documentos electrónicos para SharePoint Online y OneDrive para la Empresa.

La exhibición de documentos electrónicos de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, vea [eDiscovery de canales privados.](#ediscovery-of-private-channels)

No todo el contenido de Teams es eDiscoverable. En la tabla siguiente se muestran los tipos de contenido que puede buscar con las herramientas de exhibición de documentos electrónicos de Microsoft:

| Tipo de contenido | eDiscoverable | Notas |
|:--- | :--- |:--- |
|Grabaciones de audio | No | |
|Contenido de la tarjeta|Sí|Vea [Buscar contenido de tarjetas](#search-for-card-content) para obtener más información.|
|Vínculos de chat | Sí | |
|Mensajes de chat | Sí |Esto incluye contenido en los canales de Teams, chats uno a uno, chats grupales 1:N y chats con participantes invitados.  |
|Fragmentos de código | No | |
|Mensajes editados | Sí | Si el usuario está en espera, también se conservan las versiones anteriores de los mensajes editados. |
|Emojis, GIF y adhesivos | Sí | |
|Imágenes en línea | Sí | |
|Conversaciones de mensajería instantánea de la reunión | Sí | |
|Metadatos de<sup>reunión 1</sup> | Sí |  |
|Nombre del canal | No | |
|Mensajes de canal privado | Sí | |
|Presupuestos | Sí | El contenido citado se puede buscar. Sin embargo, los resultados de la búsqueda no indican que el contenido fue citado. |
|Reacciones (como me gusta, corazones y otras reacciones) | No | |
|Asunto | Sí | |
|Tablas | Sí | |
|||

<sup>1 Los metadatos</sup> de reunión (llamada) incluyen lo siguiente:

- Hora de inicio y finalización de la reunión y duración
- Unirse a la reunión y abandonar eventos para cada participante
- Llamadas o unirse a VOIP
- Unión anónima
- Unirse a usuarios federados
- Unirse a un usuario invitado

  La imagen muestra un ejemplo de metadatos de reunión.

  > [!div class="mx-imgBorder"]
  > ![La imagen es de los metadatos de reunión de los registros CVR.](media/conversationOption3.png)

Este es un ejemplo de una conversación de mensajería instantánea entre los participantes durante la reunión.

![Conversación entre participantes en Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversación entre participantes en los resultados de búsqueda de eDiscovery.](media/MeetingImConversation2.png)

Para obtener más información sobre cómo llevar a cabo una investigación de exhibición de documentos electrónicos, vea Introducción a La exhibición [principal de documentos electrónicos.](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)

Los datos de Microsoft Teams aparecerán como mensajería instantánea o conversaciones en el resultado de la exportación de eDiscovery de Excel. Puede abrir el archivo `.pst` en Outlook para ver los mensajes después de exportarlos.

Al ver el archivo .pst del equipo, todas las conversaciones se mantienen en la carpeta Chat del equipo, en Historial de conversaciones. El título del mensaje contiene el nombre del equipo y el nombre del canal. Por ejemplo, en la imagen siguiente se muestra un mensaje de Bob que le ha indicado el canal estándar de Project 7 del equipo de Especificaciones de fabricación.

![Captura de pantalla de una carpeta de Chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Los chats privados en el buzón de un usuario se almacenan en la carpeta Chat de equipo, en Historial de conversaciones.

## <a name="ediscovery-of-private-channels"></a>Exhibición de documentos electrónicos de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Como cada canal privado tiene su propio sitio de SharePoint independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo primario.

Teams no admite la búsqueda de exhibición de documentos electrónicos de un solo canal dentro de un equipo, por lo que es necesario buscar en todo el equipo. Para realizar una búsqueda de exhibición de documentos electrónicos de contenido en un canal privado, busque en el equipo, en la colección de sitios asociada al canal privado (para incluir archivos) y en los buzones de los miembros del canal privado (para incluir mensajes).

Siga estos pasos para identificar los archivos y mensajes de un canal privado que se incluirán en la búsqueda de exhibición de documentos electrónicos.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir archivos de canal privado en una búsqueda de eDiscovery

Antes de realizar estos pasos, instale el Shell de administración de [SharePoint Online y conéctese a SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas con canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```

2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas con canales privados en el equipo y el id. de grupo de grupo primario.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Para cada id. de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privados relevantes, donde $groupID es el id. de grupo del equipo.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensajes de canal privado en una búsqueda de eDiscovery

Antes de realizar estos pasos, asegúrese de que tiene instalada la última versión del módulo [de PowerShell de Teams.](teams-powershell-overview.md)

1. Ejecute el comando siguiente para obtener una lista de canales privados en el equipo.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Ejecute el siguiente comando para obtener una lista de los miembros del canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Incluya los buzones de todos los miembros de cada canal privado en el equipo como parte de la consulta [de búsqueda de exhibición de documentos electrónicos.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Buscar contenido para usuarios invitados

Puede usar herramientas de exhibición de documentos electrónicos para buscar contenido de Teams relacionado con los usuarios invitados de su organización. El contenido del chat de Teams asociado a un usuario invitado se conserva en una ubicación de almacenamiento basada en la nube y se puede buscar con eDiscovery. Esto incluye buscar contenido en conversaciones de chat 1:1 y 1:N en las que un usuario invitado es un participante con otros usuarios de su organización. También puede buscar mensajes de canal privados en los que un usuario invitado sea un participante y buscar contenido en conversaciones de *chat* de invitado:invitado donde los únicos participantes son usuarios invitados.

Para buscar contenido para usuarios invitados:

1. Conéctese a PowerShell de Azure AD. Para obtener instrucciones, consulte la sección "Conectarse con PowerShell de Azure Active Directory" en Conectarse a [Microsoft 365 con PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Asegúrese de completar los pasos 1 y 2 en el tema anterior.

2. Después de conectarse correctamente a PowerShell de Azure AD, ejecute el siguiente comando para mostrar el nombre principal de usuario (UPN) para todos los usuarios invitados de la organización. Tiene que usar el UPN del usuario invitado al crear la búsqueda en el paso 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > En lugar de mostrar una lista de nombres principales de usuario en la pantalla del equipo, puede redirigir la salida del comando a un archivo de texto. Para ello, puede anexar `> filename.txt` al comando anterior. El archivo de texto con los nombres principales de usuario se guardará en la carpeta actual.

3. En otra ventana de Windows PowerShell, conéctese a PowerShell del Centro & seguridad. Para obtener instrucciones, [consulte Conectarse a PowerShell del Centro & seguridad.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Puede conectarse con o sin utilizar la autenticación multifactor.

4. Cree una búsqueda de contenido que busque todo el contenido (como mensajes de chat y mensajes de correo electrónico) en el que el usuario invitado especificado sea un participante ejecutando el siguiente comando.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Por ejemplo, para buscar contenido asociado a la usuario invitada Sara Davis, ejecute el siguiente comando.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Para obtener más información sobre cómo usar PowerShell para crear búsquedas de contenido, consulta [New-ComplianceSearch.](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

5. Ejecute el siguiente comando para iniciar la búsqueda de contenido que creó en el paso 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Vaya a Mostrar todo el contenido y [https://compliance.microsoft.com](https://compliance.microsoft.com) haga clic en Mostrar **toda**  >  **la búsqueda.**

7. En la lista de búsquedas, seleccione la búsqueda que creó en el paso 4 para mostrar la página que aparece en el menú desplegable.

8. En la página desplegable, puede hacer lo siguiente:

   - Haga clic **en Ver resultados** para ver los resultados de la búsqueda y obtener una vista previa del contenido.

   - Junto al campo **Consulta,** haga clic **en Editar** para editar y, a continuación, vuelva a ejecutar la búsqueda. Por ejemplo, puede agregar una consulta de búsqueda para restringir los resultados.

   - Haga **clic en Exportar resultados** para exportar y descargar los resultados de búsqueda.

## <a name="search-for-card-content"></a>Buscar contenido de la tarjeta

El contenido de las tarjetas generado por las aplicaciones en los canales de Teams, los chats uno a uno y los chats 1xN se almacenan en buzones y se pueden buscar. Una *tarjeta es* un contenedor de la interfaz de usuario para partes cortas de contenido. Las tarjetas pueden tener varias propiedades y datos adjuntos, y pueden incluir botones que pueden desencadenar acciones de tarjeta. Para obtener más información, vea [Tarjetas](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Como con otros contenidos de Teams, donde se almacena el contenido de la tarjeta se basa en el lugar donde se usó la tarjeta. El contenido de las tarjetas que se usan en un canal de Teams se almacena en el buzón del grupo de equipos. El contenido de la tarjeta para los chats 1:1 y 1xN se almacena en los buzones de los participantes del chat.

Para buscar contenido de la tarjeta, puede usar las condiciones `kind:microsoftteams` de `itemclass:IPM.SkypeTeams.Message` búsqueda. Al revisar los resultados de la búsqueda, el contenido de la tarjeta generado por los bots en un canal de Teams tiene la propiedad de correo electrónico **Remitente/Autor** como, donde se encuentra el nombre de la aplicación que generó el contenido de la `<appname>@teams.microsoft.com` `appname` tarjeta. Si un usuario generó contenido de la tarjeta, el valor de **Remitente/Autor** identifica al usuario.

Al ver el contenido de la tarjeta en los resultados de la búsqueda de contenido, el contenido aparece como datos adjuntos en el mensaje. El archivo adjunto se denomina `appname.html` , donde se encuentra el nombre de la aplicación que `appname` generó el contenido de la tarjeta. Las siguientes capturas de pantalla muestran cómo aparece el contenido de la tarjeta (para una aplicación denominada Asana) en Teams y en los resultados de una búsqueda.

**Contenido de tarjetas en Teams**

![Contenido de la tarjeta en el mensaje del canal de Teams](media/CardContentTeams.png)

**Contenido de la tarjeta en los resultados de búsqueda**
  
![Contenido de la misma tarjeta en los resultados de una búsqueda de contenido](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Para mostrar las imágenes del contenido de la tarjeta en los resultados de búsqueda en este momento (como las marcas de verificación en la captura de pantalla anterior), tiene que haber iniciado sesión en Teams (en una pestaña diferente en la misma sesión del explorador que usa para ver los resultados de https://teams.microsoft.com) búsqueda. En caso contrario, se muestran los marcadores de posición de imagen.

## <a name="advanced-ediscovery"></a>eDiscovery avanzado

Parte del contenido de Microsoft Teams también se puede buscar y conservar con el flujo de trabajo [advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) Aunque eDiscovery proporciona un rango de funcionalidades de búsqueda, retención y exportación, la exhibición avanzada de documentos electrónicos ofrece a los administradores de cumplimiento más herramientas para identificar orígenes de datos y analizar su contenido.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flujo de trabajo de exhibición avanzada de documentos electrónicos para contenido de Teams

Puede ser miembro de varios equipos. Puede capturar contenido de Teams que sea relevante para estos contenidos. Para obtener instrucciones sobre el flujo de trabajo de usuario, [consulte Agregar usuarions a un caso de exhibición avanzada de documentos electrónicos.](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)

Después de agregar una a uno, haz clic en el **botón** Siguiente y, a continuación, **en el botón** Agregar. A continuación, se muestra una ventana que le pide que seleccione ubicaciones adicionales, que le mostrarán todas las pertenencias de esa persona y las correspondientes ubicaciones del sitio de SharePoint para sus datos. De todos estos orígenes de datos y equipos, puede elegir el contenido que desea usar para la exhibición de documentos electrónicos y, después, poner en espera a ese usuario y a todos los orígenes de datos que haya identificado.

Puede seleccionar si desea incluir su contenido de Exchange, su contenido de OneDrive o ambos. El contenido de Exchange incluye todo el contenido de la aplicación en los buzones del usuario, como el correo electrónico, el contenido de Teams almacenado en su buzón, y así sucesivamente. El contenido de OneDrive incluye no solo el contenido del usuario, sino también todo el contenido de Teams que se almacena en OneDrive, como los chats 1:1, los chats 1:N y los archivos compartidos en chats.

También tiene la opción de asociar cualquier equipo al que sea miembro el compañero para que se incluyan los mensajes de chat del canal y los archivos a los que tiene acceso el usuario. Además, cualquier otro equipo se puede asociar con un usuario.

> [!NOTE]
> La exhibición de documentos electrónicos de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, [vea eDiscovery de canales privados.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Poner un origen de datos en espera

Si no hay ningún usuario específico que designe como usuario de confianza, puede poner todo un origen de datos en espera. Para obtener más información sobre las retenciones, vea [Administrar retenciones en exhibición avanzada de documentos electrónicos.](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)

Al crear una retención de contenido de Teams, puede elegir todas las ubicaciones que desea incluir en su retención. Aunque los usuarios eliminen o cambien contenido, la retención mantendrá copias de todas las versiones anteriores de ese contenido.

También puede usar una consulta opcional para establecer condiciones de retención basadas en palabras clave, intervalo de fechas, autor y muchos otros criterios. Si no especifica palabras clave, todo el origen de datos estará sujeto a la retención.

### <a name="advanced-ediscovery-searches"></a>Búsquedas avanzadas de eDiscovery

También se puede buscar contenido de Teams. Para obtener más información sobre las búsquedas, vea [Recopilar datos para un caso de exhibición avanzada de documentos electrónicos.](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery) Una búsqueda devolverá una conversación completa si incluso un mensaje coincide con la consulta de búsqueda.

Al crear una consulta de búsqueda, puede elegir entre carpetas para que se busquen todos los orígenes que ya ha seleccionado. También puede buscar orígenes que no están asignados a un usuario, como un sitio de Teams. Las consultas opcionales también están disponibles para restringir la búsqueda dentro del contenido de Teams.

Después de crear una búsqueda y seleccionarla, se muestra una ventana con detalles y acciones adicionales que puede realizar en la búsqueda seleccionada. Si hace clic en el botón **Estadísticas,** puede ver estadísticas sobre la búsqueda, incluidos los desgloses según los tipos de ubicación, el origen original del contenido y si el contenido se encuentra en un buzón de grupo, en el buzón de usuario individual o en un sitio de SharePoint. Por lo tanto, puede ver un desglose de los orígenes que contribuyen a los resultados de búsqueda. También hay disponible una **vista de consultas** para que pueda ver qué palabras clave individuales contribuyen a los resultados.

Después de finalizar la búsqueda,  puede hacer clic en el botón Agregar resultados para revisar conjunto y agregarlo a un conjunto de revisión. Para obtener más información sobre los conjuntos de revisión, vea Administrar conjuntos de [revisión](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) en el flujo de trabajo Detección avanzada y Conjuntos de revisión, [](#review-sets-workflow) más adelante en este artículo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Conjuntos de revisión normales y conjuntos de revisión de conversaciones

Al agregar una búsqueda a un conjunto de revisión, puede elegir entre un conjunto de revisión normal o un conjunto de revisión de conversación.

Un conjunto de revisión normal es similar a una exportación; proporciona los archivos `.msg` individuales del contenido de Teams y presenta el contenido en una vista básica. Normalmente se usaba un conjunto de revisión normal cuando planea usar otras herramientas de software para volver a procesar los archivos más adelante.

Un conjunto de revisión de conversaciones ofrece una vista en hilo más intuitiva de las conversaciones; muestra juntos los mensajes relacionados en el orden correcto.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla del conjunto de revisión de conversaciones](media/conversationOptions2.png)

Funcionalidad como redaction está disponible en ambos tipos de conjuntos de revisión. Para obtener más información sobre los conjuntos de revisión, vea [Revisar conversaciones en eDiscovery avanzado.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Opciones de colección

Al agregar un conjunto de revisión, hay varias  opciones disponibles como casillas en la sección Opciones de colección de la ventana, incluidas las opciones de recuperación de conversación y **las** conversaciones **de Teams.** Si habilita estas opciones, los mensajes individuales de Teams que forman parte de su conjunto de revisión también se mostrarán con mensajes adicionales a su alrededor para obtener contexto. Por ejemplo, si la consulta es específica y solo se devuelve un mensaje como resultado, al habilitar estas opciones también se devolverán varios mensajes que llevan al mensaje que coincide con la consulta y que sigue a este.

Muchos criterios lógicos se usan para determinar si los mensajes adicionales proporcionan contexto a los mensajes que coinciden con la consulta. Por ejemplo, para el contenido de Teams, al habilitar estas opciones, se recuperarán el mensaje principal y todos los mensajes secundarios debido a la forma en que los mensajes están en conversación.

También se comprueban las marcas de tiempo de los mensajes. Si un mensaje coincide con la consulta, se considera que los mensajes adyacentes que los preceden en un intervalo de 4 horas o que lo siguen en un intervalo de 4 horas son parte de la conversación y también se incluyen en los resultados.

Si debe estar seguro de qué mensajes contextuales se devolverán con coincidencias con la consulta de búsqueda, no es necesario usar estas opciones. Puede recopilar todo el contenido o ampliar el intervalo de fechas de la búsqueda para que se devuelvan más mensajes como resultado de la consulta.

### <a name="review-sets-workflow"></a>Flujo de trabajo de conjuntos de revisión

Puede ver conjuntos de revisión existentes o crear otros nuevos haciendo clic en la **pestaña Revisar conjuntos.** Para obtener más información sobre los conjuntos de revisión, vea [Administrar conjuntos de revisión en Exhibición avanzada de documentos electrónicos.](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)

Además de documentos, puede agregar correos electrónicos, mensajes de Teams, mensajes de Yammer y otros contenidos a su conjunto de revisión. Dentro de un conjunto de revisión, también puede realizar muchas de las mismas operaciones que puede realizar en otros contextos, como buscar contenido y crear consultas personalizadas. Estas operaciones solo se aplican a los elementos que se han agregado al conjunto de revisión.

El **botón Administrar conjuntos de** revisión proporciona opciones adicionales como análisis, informes de resumen, cuántos conjuntos de carga se han agregado, y así sucesivamente.

Para acceder a visualizaciones y  gráficos de los datos, haga clic en Vista de perfil de búsqueda de resultados \> **individuales** en la esquina superior derecha. Puede hacer clic en cuñas en estos gráficos para seleccionar de forma interactiva el tipo de contenido que desea consultar. Por ejemplo, puede elegir consultar solo el contenido de Teams. También puede guardar estas consultas del mismo modo que las consultas que escribe manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Vista resumen, vista de texto y vista Anotar

Si hace clic en una conversación de Teams en el conjunto de revisión, se muestra la vista **Resumen,** que muestra una conversación de Teams completa como una lista de mensajes con los que puede interactuar individualmente. Haga clic en la flecha hacia abajo a la derecha de un mensaje para mostrar un menú contextual que le permite ver detalles del mensaje o descargar el archivo `.msg` individual. Al hacer clic en los detalles del mensaje, se mostrará un resumen de los metadatos o de los metadatos completos del mensaje.

Para descargar un archivo PDF, haga clic en el botón de descarga situado en la parte superior derecha de la vista de resumen.

Haga clic **en la pestaña Vista** de texto para mostrar una vista de texto sin formato del texto extraído de la conversación de Teams. Este contenido de texto sin formato es adecuado para exportación y puede trabajar fácilmente con él con otras herramientas de software.

Haga clic en la **pestaña Vista Anotaciones para** acceder a las características de anotación. Esta pestaña muestra el contenido en un formato similar a una conversación de Teams, pero también hay opciones adicionales de edición. Puede usar una herramienta de lápiz para tomar notas, dibujar en el mensaje o para hacer un borrador específico con fines de redacción. También hay una herramienta **Redacción de** área que puede usar para dibujar un rectángulo que dibuje un área en negro y la marca como "Redactada".

Este es un ejemplo de un archivo redactado para conversaciones en hilos entre usuarios.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla del archivo redactado](media/RedactedFileExample.png)

En la parte inferior de la **pestaña vista Anotaciones** se encuentra el **botón** Etiquetar documentos, que muestra el panel de etiquetado. En este panel, puede aplicar una etiqueta a todos los mensajes de la conversación de Teams. Puede etiquetar una conversación como que responda o que no responda, tenga privilegios o no tenga privilegios, si contiene "Elementos interesantes", si debe incluirse en la exportación y si necesita una revisión posterior. También puede administrar y aplicar otras etiquetas personalizables.

#### <a name="action-menu"></a>Menú de acciones

En la ventana de conjuntos de revisión, puede exportar el contenido haciendo clic en **Exportar** \> **acción.** Hay muchas opciones disponibles al exportar.

Para exportar un archivo que contiene todos los metadatos de todos los mensajes de Teams, haga clic para seleccionar la **casilla Cargar** archivo. Para incluir en el archivo todas las etiquetas que haya aplicado al contenido, haga clic para seleccionar la casilla **Etiquetas.**

Use la **opción Archivos nativos** para exportar archivos en su formato nativo. Puede exportar una conversación como un archivo o como todos los mensajes de chat individuales en sus propios archivos independientes.

La **opción Archivos de** texto le permite guardar versiones de texto sin formato del contenido. Para obtener más información sobre cómo obtener una vista de texto sin formato de las conversaciones de Teams en el conjunto de revisión, vea la vista [Resumen,](#summary-view-text-view-and-annotate-view) la vista de texto y realizar anotaciones más arriba.

Si aplicó redacciones al contenido como se describe en la sección anterior Vista [resumen,](#summary-view-text-view-and-annotate-view) Vista de texto y Anotación, puede seleccionar la opción Reemplazar nativos redactados por archivos **PDF convertidos** para reemplazar los archivos nativos por copias convertadas en PDF.

Puede elegir exportar a un contenedor de Azure Blob Storage proporcionado por Microsoft o puede proporcionar su propio contenedor de Azure Blob Storage.

Cuando esté listo para comenzar el proceso de exportación, haga clic en **el botón** Exportar. Vea [Descargar trabajos de exportación](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) para obtener más información sobre cómo puede obtener acceso al contenedor de Azure Blob Storage y descargar el contenido exportado una vez completada la exportación.

> [!NOTE]
> La exportación puede llevar un largo período de tiempo. Para realizar un seguimiento del estado del proceso de exportación, salga de la pestaña **Conjuntos** de revisión y haga clic en **la pestaña** Exportaciones.

## <a name="related-topics"></a>Temas relacionados

- [Exhibición de documentos electrónicos en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
