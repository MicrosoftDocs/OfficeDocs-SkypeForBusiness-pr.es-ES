---
title: Realizar una investigación de exhibición de documentos electrónicos sobre contenido
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
description: Obtenga información sobre qué hacer cuando necesita realizar exhibición de documentos electrónicos, por ejemplo, cuando necesita enviar toda la información almacenada electrónicamente para los procedimientos legales.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ebc1bb12b8a864e65cf6cb26b3d2022ae2e1563b
ms.sourcegitcommit: e023c3023f49e196315e176ce346f0dc5825fa56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53275689"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams

Las grandes empresas suelen estar expuestas a procedimientos legales con penas elevadas que exigen el envío de toda la información almacenada electrónicamente (ESI). Microsoft Teams contenido se puede buscar y usar durante las investigaciones de exhibición de documentos electrónicos.

## <a name="overview"></a>Información general

Todos Microsoft Teams chats de grupo o 1:1 se pasan por diario a los buzones de los usuarios respectivos. Todos los mensajes de canal estándar se envían en diario al buzón de grupo que representa al equipo. Los archivos cargados en canales estándar se cubren en la funcionalidad de exhibición de documentos electrónicos para SharePoint Online y OneDrive para la Empresa.

La exhibición de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, vea [Exhibición de documentos electrónicos de canales privados.](#ediscovery-of-private-channels)

No todo Teams contenido es eDiscoverable. En la tabla siguiente se muestran los tipos de contenido que puede buscar con herramientas de exhibición de documentos electrónicos de Microsoft:

| Tipo de contenido | eDiscoverable | Notas |
|:--- | :--- |:--- |
|Grabaciones de audio | No | |
|Contenido de la tarjeta|Sí|Vea [Buscar contenido de tarjeta](#search-for-card-content) para obtener más información.|
|Vínculos de chat | Sí | |
|Mensajes de chat | Sí |Esto incluye contenido en Teams, chats 1:1, chats grupales 1:N y chats con participantes de usuario invitado.  |
|Fragmentos de código | No | |
|Mensajes editados | Sí | Si el usuario está en espera, también se conservan las versiones anteriores de los mensajes editados. |
|Emojis, GIF y adhesivos | Sí | |
|Imágenes en línea | Sí | |
|Conversaciones de mensajería instantánea de reunión | Sí | |
|Metadatos de<sup>la reunión 1</sup> | Sí |  |
|Nombre del canal | No | |
|Mensajes de canal privado | Sí | |
|Comillas | Sí | Se puede buscar contenido entre comillas. Sin embargo, los resultados de la búsqueda no indican que el contenido se citó. |
|Reacciones (como me gusta, corazones y otras reacciones) | No | |
|Asunto | Sí | |
|Tablas | Sí | |
|Notificaciones de fuentes | No | |
|||

<sup>1 Los</sup> metadatos de reunión (y llamada) incluyen lo siguiente:

- Hora y duración de inicio y finalización de la reunión
- Reunión unirse y dejar eventos para cada participante
- VOIP join/calls
- Unirse anónimo
- Unión de usuarios federados
- Unirse al usuario invitado

  La imagen muestra un ejemplo de metadatos de reunión.

  > [!div class="mx-imgBorder"]
  > ![La imagen es de los metadatos de reunión de los registros CVR.](media/conversationOption3.png)

Este es un ejemplo de una conversación de mensajería instantánea entre los participantes durante la reunión.

![Conversación entre participantes en Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversación entre participantes en los resultados de búsqueda de exhibición de documentos electrónicos.](media/MeetingImConversation2.png)

Para obtener más información sobre cómo llevar a cabo una investigación de exhibición de documentos electrónicos, vea Introducción a [eDiscovery principal.](/microsoft-365/compliance/get-started-core-ediscovery)

Microsoft Teams datos aparecerán como mensajería instantánea o Conversaciones en el Excel de exportación de exhibición de documentos electrónicos. Puede abrir el `.pst` archivo en Outlook ver esos mensajes después de exportarlos.

Al ver el archivo .pst para el equipo, todas las conversaciones se encuentran en la carpeta Chat de grupo en Historial de conversaciones. El título del mensaje contiene el nombre del equipo y el nombre del canal. Por ejemplo, en la imagen siguiente se muestra un mensaje de Bob que envía un mensaje al canal Project 7 estándar del equipo de Especificaciones de fabricación.

![Captura de pantalla de una carpeta chat de grupo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Los chats privados en el buzón de un usuario se almacenan en la carpeta Chat de grupo en Historial de conversaciones.

## <a name="ediscovery-of-private-channels"></a>eDiscovery de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Dado que cada canal privado tiene su propio sitio de SharePoint independiente del sitio de grupo principal, los archivos de un canal privado se administran independientemente del equipo principal.

Teams no admite la búsqueda de exhibición de documentos electrónicos de un solo canal dentro de un equipo, por lo que se debe buscar a todo el equipo. Para realizar una búsqueda de exhibición de documentos electrónicos de contenido en un canal privado, busque en todo el equipo, la colección de sitios asociada con el canal privado (para incluir archivos) y los buzones de los miembros del canal privado (para incluir mensajes).

Siga estos pasos para identificar archivos y mensajes en un canal privado para incluirlos en la búsqueda de exhibición de documentos electrónicos.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir archivos de canal privado en una búsqueda de exhibición de documentos electrónicos

Antes de realizar estos pasos, instale SharePoint Shell de administración en línea [y conéctese a SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Ejecute lo siguiente para obtener una lista de todas SharePoint colecciones de sitios asociadas con canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```

2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios SharePoint asociadas con canales privados en el equipo y el id. de grupo de grupo principal.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Para cada id. de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado relevantes, donde $groupID es el id. de grupo del equipo.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensajes de canal privado en una búsqueda de exhibición de documentos electrónicos

Antes de realizar estos pasos, asegúrese de que tiene instalada la versión más reciente [Teams módulo de PowerShell.](teams-powershell-overview.md)

1. Ejecute el siguiente comando para obtener una lista de canales privados en el equipo.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Ejecute el siguiente comando para obtener una lista de los miembros del canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Incluya los buzones de todos los miembros de cada canal privado en el equipo como parte de la consulta [de búsqueda de exhibición de documentos electrónicos.](/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Buscar contenido para usuarios invitados

Puede usar herramientas de exhibición de documentos electrónicos para buscar Teams contenido relacionado con los usuarios invitados de su organización. Teams contenido de chat asociado a un usuario invitado se conserva en una ubicación de almacenamiento basada en la nube y se puede buscar con eDiscovery. Esto incluye buscar contenido en conversaciones de chat 1:1 y 1:N en las que un usuario invitado es un participante con otros usuarios de su organización. También puede buscar mensajes de canal privado en los que un usuario invitado es un participante y buscar contenido en conversaciones de chat de *invitado:invitado,* donde los únicos participantes son usuarios invitados.

Para buscar contenido para los usuarios invitados:

1. Conectar a Azure AD PowerShell. Para obtener instrucciones, vea la sección "Conectar con Azure Active Directory PowerShell" en Conectar para Microsoft 365 [con PowerShell.](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Asegúrese de completar los pasos 1 y 2 en el tema anterior.

2. Después de conectarse correctamente a Azure AD PowerShell, ejecute el siguiente comando para mostrar el nombre principal de usuario (UPN) para todos los usuarios invitados de su organización. Debe usar el UPN del usuario invitado al crear la búsqueda en el paso 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > En lugar de mostrar una lista de nombres principales de usuario en la pantalla del equipo, puede redirigir el resultado del comando a un archivo de texto. Puede hacerlo anexando al `> filename.txt` comando anterior. El archivo de texto con los nombres principales de usuario se guardará en la carpeta actual.

3. En otra ventana Windows PowerShell, conéctese a PowerShell del Centro de & cumplimiento. Para obtener instrucciones, [vea Conectar a PowerShell & Centro de cumplimiento](/powershell/exchange/connect-to-scc-powershell). Puede conectarse con o sin la autenticación multifactor.

4. Cree una búsqueda de contenido que busque todo el contenido (como mensajes de chat y mensajes de correo electrónico) en el que el usuario invitado especificado fuera un participante ejecutando el comando siguiente.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Por ejemplo, para buscar contenido asociado con la usuario invitada Sara Davis, ejecutaría el siguiente comando.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Para obtener más información sobre el uso de PowerShell para crear búsquedas de contenido, vea [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Ejecute el comando siguiente para iniciar la búsqueda de contenido que creó en el paso 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Mostrar toda la búsqueda** de  >  **contenido.**

7. En la lista de búsquedas, seleccione la búsqueda que creó en el paso 4 para mostrar la página desplegable.

8. En la página desplegable, puede hacer lo siguiente:

   - Haga **clic en Ver resultados** para ver los resultados de la búsqueda y obtener una vista previa del contenido.

   - Junto al **campo Consulta,** haga clic **en Editar** para editar y, a continuación, vuelva a ejecutar la búsqueda. Por ejemplo, puede agregar una consulta de búsqueda para restringir los resultados.

   - Haga **clic en Exportar resultados** para exportar y descargar los resultados de búsqueda.

## <a name="search-for-card-content"></a>Buscar contenido de tarjeta

El contenido de la tarjeta generado por las aplicaciones en Teams canales, chats 1:1 y chats 1xN se almacena en buzones y se puede buscar. Una *tarjeta es* un contenedor de interfaz de usuario para fragmentos cortos de contenido. Las tarjetas pueden tener varias propiedades y datos adjuntos, y pueden incluir botones que pueden desencadenar acciones de tarjeta. Para obtener más información, vea [Tarjetas](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Al igual que Teams contenido, donde se almacena el contenido de la tarjeta se basa en el lugar donde se usó la tarjeta. El contenido de las tarjetas usadas en un canal Teams se almacena en el buzón Teams grupo. El contenido de la tarjeta para chats 1:1 y 1xN se almacena en los buzones de los participantes del chat.

Para buscar contenido de tarjeta, puede usar las `kind:microsoftteams` condiciones de búsqueda o `itemclass:IPM.SkypeTeams.Message` o. Al revisar los resultados de la búsqueda, el contenido de la tarjeta generado por los bots en un canal de Teams tiene la propiedad de correo electrónico **Remitente/Autor** como , donde está el nombre de la aplicación que generó el contenido `<appname>@teams.microsoft.com` de la `appname` tarjeta. Si un usuario generó contenido de tarjeta, el valor de **Remitente/Autor** identifica al usuario.

Al ver el contenido de la tarjeta en los resultados de búsqueda de contenido, el contenido aparece como datos adjuntos al mensaje. El archivo adjunto se denomina `appname.html` , donde está el nombre de la aplicación que `appname` generó el contenido de la tarjeta. Las siguientes capturas de pantalla muestran cómo aparece el contenido de la tarjeta (para una aplicación denominada Asana) en Teams y en los resultados de una búsqueda.

**Contenido de tarjeta en Teams**

![Contenido de la tarjeta en Teams de canal](media/CardContentTeams.png)

**Contenido de la tarjeta en los resultados de búsqueda**
  
![Mismo contenido de tarjeta en los resultados de una búsqueda de contenido](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Para mostrar imágenes del contenido de la tarjeta en los resultados de búsqueda en este momento (como las marcas de verificación de la captura de pantalla anterior), debe haber iniciado sesión en Teams (en una pestaña diferente en la misma sesión del explorador que usa para ver los resultados de https://teams.microsoft.com) búsqueda. En caso contrario, se mostrarán marcadores de posición de imagen.

## <a name="advanced-ediscovery"></a>eDiscovery avanzado

Algunos Microsoft Teams también se pueden buscar y conservar con el [flujo Advanced eDiscovery de trabajo.](/microsoft-365/compliance/overview-ediscovery-20) Aunque eDiscovery proporciona un rango de funciones de búsqueda, retención y exportación, Advanced eDiscovery proporciona a los administradores de cumplimiento más herramientas para identificar orígenes de datos y analizar su contenido.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Advanced eDiscovery de trabajo de custodio para Teams contenido

Los custodios pueden ser miembros de varios equipos. Puede capturar Teams contenido relevante para estos custodios. Para obtener instrucciones sobre el flujo de trabajo de custodio, vea [Agregar custodios a un Advanced eDiscovery caso.](/microsoft-365/compliance/add-custodians-to-case)

Después de agregar un custodio, haga clic en **el botón** Siguiente y, a continuación, en **el botón** Agregar. A continuación, se muestra una ventana que le pide que seleccione ubicaciones adicionales, lo que le mostrará todas las pertenencias del custodio y las correspondientes ubicaciones SharePoint sitio para sus datos. De todos estos orígenes de datos y equipos, puede elegir el contenido que desea usar para eDiscovery y, a continuación, colocar ese usuario y todos los orígenes de datos que ha identificado en espera.

Puede seleccionar si desea incluir su Exchange, su OneDrive o ambos. Exchange contenido incluye todo el contenido de la aplicación en los buzones del usuario, como su correo electrónico, el contenido de Teams almacenado en su buzón, y así sucesivamente. El OneDrive incluye no solo el contenido del usuario, sino también todo el contenido de Teams almacenado en OneDrive, como chats de 1:1, chats 1:N y archivos compartidos en chats.

También tiene la opción de asociar cualquier equipo del que sea miembro el custodio para que se incluyan los mensajes de chat del canal y los archivos a los que el custodio tiene acceso. Además, cualquier otro equipo puede estar asociado con un custodio.

> [!NOTE]
> La exhibición de mensajes y archivos en [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, vea [Exhibición de documentos electrónicos de canales privados.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Poner un origen de datos en espera

Si no hay ningún usuario específico que designar como custodio, puede poner todo un origen de datos en espera. Para obtener más información sobre las retenciones, vea [Administrar retenciones en Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

Al crear una retención para Teams contenido, puede elegir todas las ubicaciones que desea incluir en la retención. Aunque los usuarios eliminen o cambien el contenido, la retención mantendrá copias de todas las versiones anteriores de ese contenido.

También puede usar una consulta opcional para establecer condiciones para la retención en función de palabras clave, intervalo de fechas, autor y muchos otros criterios. Si no especifica palabras clave, todo el origen de datos estará sujeto a la retención.

### <a name="advanced-ediscovery-searches"></a>Advanced eDiscovery búsquedas

Teams también se puede buscar contenido. Para obtener más información sobre las búsquedas, vea Recopilar [datos de un caso en Advanced eDiscovery](/microsoft-365/compliance/collecting-data-for-ediscovery). Una búsqueda devolverá una conversación completa si incluso un mensaje coincide con la consulta de búsqueda.

Al crear una consulta de búsqueda, puede elegir custodios para que se busquen todos los orígenes que ya ha seleccionado. También puede buscar orígenes que no son custodios, como un sitio Teams que no está asignado a un usuario. Las consultas opcionales también están disponibles para restringir la búsqueda dentro del Teams contenido.

Después de crear una búsqueda y seleccionarla, se muestra una ventana con detalles y acciones adicionales que puede realizar en la búsqueda seleccionada. Si hace clic en el botón **Estadísticas,** puede ver estadísticas sobre la búsqueda, incluidos los desgloses según los tipos de ubicación, el origen original del contenido y si el contenido se encuentra en un buzón de grupo, el buzón de usuario individual o un sitio de SharePoint. Por lo tanto, puede ver un desglose de las fuentes que contribuyen a los resultados de búsqueda. También hay una **vista Consultas** disponible para que pueda ver qué palabras clave individuales contribuyen a los resultados.

Después de finalizar la búsqueda,  puede hacer clic en el botón Agregar resultados para revisar el conjunto y agregarlo a un conjunto de revisión. Para obtener más información sobre los conjuntos de revisión, vea Administrar conjuntos de revisión [en el](/microsoft-365/compliance/managing-review-sets) flujo de trabajo Advanced eDiscovery y Conjuntos [de](#review-sets-workflow) revisión más adelante en este artículo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Conjuntos de revisión normales y conjuntos de revisión de conversaciones

Al agregar una búsqueda a un conjunto de revisión, puede elegir entre un conjunto de revisión normal o un conjunto de revisión de conversación.

Un conjunto de revisión normal es similar a una exportación; proporciona los archivos `.msg` individuales para el Teams y presenta el contenido en una vista básica. Normalmente, usaría un conjunto de revisión normal cuando planee usar otras herramientas de software para volver a procesar los archivos más adelante.

Un conjunto de revisión de conversación proporciona una vista en hilo más intuitiva de las conversaciones; muestra los mensajes relacionados juntos en el orden correcto.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla del conjunto de revisión de conversaciones](media/conversationOptions2.png)

Las funciones como la redacción están disponibles en ambos tipos de conjuntos de revisión. Para obtener más información sobre los conjuntos de revisión, vea [Revisar conversaciones en eDiscovery avanzado.](/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Opciones de colección

Al agregar a un conjunto de revisión, hay  varias opciones disponibles como  casillas en la sección Opciones de colección de la ventana, incluidas las Opciones de recuperación de conversaciones **y Teams conversaciones.** Si habilita estas opciones, los mensajes Teams que forman parte de su conjunto de revisión también se mostrarán con mensajes adicionales que los rodeen para el contexto. Por ejemplo, si la consulta es específica y solo se devuelve un mensaje como resultado, habilitar estas opciones también devolverá varios mensajes previos y siguientes al mensaje que coincidió con la consulta.

Se usan muchos criterios lógicos para determinar si los mensajes adicionales proporcionan contexto a los mensajes que coinciden con la consulta. Por ejemplo, para Teams contenido, habilitar estas opciones recuperará el mensaje principal y todos los mensajes secundarios debido a la forma en que se enhebran los mensajes.

Las marcas de tiempo de los mensajes también están activadas. Si un mensaje coincide con la consulta, los mensajes vecinos que lo preceden en un intervalo de 4 horas o que lo siguen en un intervalo de 4 horas se consideran parte de la conversación y también se incluyen en los resultados.

Si debe estar seguro de qué mensajes contextuales se devolverán con coincidencias con la consulta de búsqueda, no es necesario que use estas opciones. Puede recopilar todo el contenido o ampliar el intervalo de fechas de la búsqueda para que se devuelvan más mensajes como resultado de la consulta.

### <a name="review-sets-workflow"></a>Flujo de trabajo de conjuntos de revisión

Puede ver conjuntos de revisión existentes o crear nuevos haciendo clic en la **pestaña Conjuntos de** revisión. Para obtener más información sobre los conjuntos de revisión, vea [Administrar conjuntos de revisión en Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets).

Además de los documentos, puede agregar correos electrónicos, Teams, Yammer y otro contenido al conjunto de revisión. Dentro de un conjunto de revisión, también puede realizar muchas de las mismas operaciones que puede realizar en otros contextos, como buscar contenido y crear consultas personalizadas. Estas operaciones solo se aplican a los elementos que se han agregado al conjunto de revisión.

El **botón Administrar conjuntos de** revisión proporciona opciones adicionales, como análisis, informes de resumen, cuántos conjuntos de carga se han agregado, y así sucesivamente.

Para obtener acceso a visualizaciones y gráficos de los datos, haga clic en **Resultados individuales** Buscar vista de \> **perfil** en la esquina superior derecha. Puede hacer clic en cuñas en estos gráficos para seleccionar de forma interactiva el tipo de contenido que desea consultar. Por ejemplo, puede elegir consultar solo Teams contenido. También puede guardar estas consultas del mismo modo que guardaría las consultas que escriba manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Vista resumen, vista de texto y vista de anotaciones

Si hace clic en una conversación Teams en el conjunto de revisión, se muestra la vista **Resumen,** que muestra una conversación de Teams completa como una lista de mensajes con los que puede interactuar individualmente. Haga clic en la flecha hacia abajo a la derecha de un mensaje para mostrar un menú contextual que le permite ver los detalles del mensaje o descargar el archivo `.msg` individual. Al hacer clic en detalles del mensaje, se mostrará un resumen de los metadatos o los metadatos completos del mensaje.

Para descargar un PDF, haga clic en el botón descargar situado en la esquina superior derecha de la vista de resumen.

Haga clic **en la pestaña Vista** de texto para mostrar una vista de texto sin formato del texto extraído de la Teams conversación. Este contenido de texto sin formato es adecuado para la exportación y puede trabajar fácilmente con él con otras herramientas de software.

Haga clic en la **pestaña Vista anotaciones para** obtener acceso a las características de anotación. Esta pestaña muestra el contenido en un formato similar a una conversación Teams, pero también hay opciones adicionales para editar. Hay una herramienta de lápiz que puede usar para hacer notas, dibujar en el mensaje o realizar un rascado fino para fines de redacción. También hay una herramienta **de redacción de** área que puede usar para dibujar un rectángulo que aneje el área y lo marca como "Redacted".

A continuación se muestra un ejemplo de un archivo redactado para la conversación en hilo entre usuarios.

> [!div class="mx-imgBorder"]
> ![Captura de pantalla del archivo redactado](media/RedactedFileExample.png)

En la parte inferior de la pestaña **Vista** Anotaciones se encuentra el botón Etiquetar **documentos,** que muestra el panel de etiquetado. En este panel, puede aplicar una etiqueta a todos los mensajes de la Teams conversación. Puede etiquetar una conversación como responsivo o no, con privilegios o sin privilegios, si contiene "Elementos interesantes", si debe incluirse en la exportación y si necesita una revisión adicional. También puede administrar y aplicar otras etiquetas personalizables.

#### <a name="action-menu"></a>Menú Acción

En la ventana conjuntos de revisión, puede exportar el contenido haciendo clic en **Exportar** \> **acción.** Hay muchas opciones disponibles al exportar.

Para exportar un archivo que contiene todos los metadatos de todos los Teams, haga clic para seleccionar la **casilla Cargar archivo.** Para incluir en el archivo las etiquetas que haya aplicado al contenido, haga clic para seleccionar la **casilla Etiquetas.**

Use la **opción Archivos nativos** para exportar archivos en su formato nativo. Puede elegir exportar una conversación como un archivo o todos los mensajes de chat individuales en sus propios archivos independientes.

La **opción Archivos de** texto le permite guardar versiones de texto sin formato de contenido. Para obtener más información sobre cómo obtener una vista de texto sin formato de Teams conversaciones en el conjunto de revisión, vea Vista de resumen, vista de texto y vista [anotación anterior.](#summary-view-text-view-and-annotate-view)

Si aplicó alguna redacción al contenido como se describe en la vista [Resumen,](#summary-view-text-view-and-annotate-view) vista de texto y vista de anotaciones anterior, puede seleccionar la opción Reemplazar nativos redactados con **archivos PDF convertidos** para reemplazar los archivos nativos con copias convertida en PDF.

Puede elegir exportar a un contenedor de almacenamiento de blobs de Azure proporcionado por Microsoft o puede proporcionar su propio contenedor de almacenamiento de blobs de Azure.

Cuando esté listo para iniciar el proceso de exportación, haga clic en **el botón** Exportar. Consulte [Descargar trabajos de exportación](/microsoft-365/compliance/download-export-jobs) para obtener más información sobre cómo puede obtener acceso al contenedor de almacenamiento de blobs de Azure y descargar el contenido exportado una vez completada la exportación.

> [!NOTE]
> La exportación puede tardar un período de tiempo prolongado. Para realizar un seguimiento del estado del proceso de exportación, salga de la pestaña **Conjuntos de** revisión y haga clic en la **pestaña** Exportaciones.

## <a name="related-topics"></a>Temas relacionados

- [eDiscovery en Microsoft 365](/microsoft-365/compliance/ediscovery)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)