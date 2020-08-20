---
title: Realizar una investigación de contenido en eDiscovery
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
description: Obtenga información sobre qué hacer cuando necesite realizar una exhibición de datos electrónicos, como cuando necesita enviar toda la información almacenada por datos por medios para procedimientos legales.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4679d8ed59ab8eec0fb856961f646d1f20049ff3
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814116"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams

Las grandes empresas suelen estar expuestas a un procedimiento legal de alta multa que exige el envío de toda la información almacenada electrónicamente (ESI). El contenido de Microsoft Teams se puede buscar y usar durante las investigaciones de eDiscovery.

## <a name="overview"></a>Información general

Todas las conversaciones de Microsoft Teams 1:1 o grupales se registran en el diario de los buzones de los usuarios respectivos. Todos los mensajes de canal estándar se registran en el diario hasta el buzón de grupo que representa al equipo. Los archivos cargados en canales estándar están cubiertos por la funcionalidad de eDiscovery para SharePoint Online y OneDrive para la empresa.

eDiscovery de los mensajes y los archivos de los [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, consulte [eDiscovery of Private Channels](#ediscovery-of-private-channels).

No todo el contenido de los equipos está eDiscoverable. En la tabla siguiente se muestran los tipos de contenido que se pueden encontrar mediante eDiscovery.

| Tipo de contenido | eDiscoverable | Notas |
|:--- | --- |:--- |
| Mensajes de chat de Teams | Sí |  |
| Mensajes de canal privado | Sí | |
| Nombre del canal | No | |
| Conversaciones de mensajería instantánea de la reunión | Sí | |
| Metadatos de reunión<sup>1</sup> | Sí |  |
| Mensajes editados | Sí | Si el usuario se encuentra en espera, se conservan las versiones anteriores de los mensajes editados. |
| Emojis, GIF, adhesivos | Sí | |
| Fragmentos de código | No | |
| Vínculos de chat | Sí | |
| Reacciones (me gusta, corazones, etc.) | No | |
| Imágenes en línea | Sí | |
| Tablas | Sí | |
| Asunto | Sí | |
| Ellas | Sí | El contenido entrecomillado se encuentra en búsqueda. Sin embargo, los resultados de la búsqueda no indican que el contenido se presupuestó. |
| Grabaciones de audio | No | |

<sup>1</sup> los metadatos de la reunión incluyen lo siguiente:

- Hora de inicio y finalización de la reunión o llamada, y duración
- Unirse a la llamada/reunión y dejar eventos para cada participante
- Unión o llamadas VOIP
- Unirse anónimamente
- Combinación de usuarios federados
- Combinación de usuarios invitados

La imagen muestra un ejemplo de los metadatos.

![La imagen es de la CVR graba los metadatos de la reunión.](media/conversationOption3.png)

Este es un ejemplo de una conversación de mensajería instantánea entre participantes durante la reunión.

![La imagen es de una conversación entre los participantes.](media/MeetingIMConversations.png)

![La imagen es de una conversación entre los participantes.](media/MeetingImConversation2.png)

Para realizar una investigación de eDiscovery con el contenido de Microsoft Teams, revise el paso 1 en Introducción [a la exhibición básica de eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).

Los datos de Microsoft Teams aparecerán como mensajes instantáneos o conversaciones en la salida de exportación de eDiscovery de Excel. Puede abrir el `.pst` archivo en Outlook para ver esos mensajes después de la exportación.

Al ver el archivo. pst del equipo, todas las conversaciones se guardan en la carpeta chat de equipo en historial de conversaciones. El título del mensaje contiene el nombre del equipo y el nombre del canal. Por ejemplo, la imagen siguiente muestra un mensaje de Bob que ha expuesto el canal de Project 7 Standard del equipo de especificaciones de fabricación.

![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Las conversaciones privadas en el buzón de un usuario se almacenan en la carpeta chat de equipo en historial de conversaciones.

## <a name="ediscovery-of-private-channels"></a>eDiscovery de canales privados

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Como cada canal privado tiene su propia colección de sitios de SharePoint que es independiente del sitio de grupo primario, los archivos de un canal privado se administran independientemente del equipo principal.

Teams no admite la búsqueda de eDiscovery en un único canal de un equipo, por lo que se debe buscar en todo el equipo. Para realizar una búsqueda en eDiscovery de contenido en un canal privado, busque en el equipo, la colección de sitios asociada al canal privado (para incluir archivos) y buzones de miembros de canales privados (para incluir mensajes).

Siga estos pasos para identificar los archivos y mensajes de un canal privado para incluirlos en la búsqueda de eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir archivos de canal privado en una búsqueda de eDiscovery

Antes de realizar estos pasos, instale el [Shell de administración de SharePoint Online y conéctese a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Ejecute lo siguiente para obtener una lista de todas las colecciones de sitios de SharePoint asociadas a los canales privados en el equipo.

    ```PowerShell
    Get-SPOSite
    ```

2. Ejecute el siguiente script de PowerShell para obtener una lista de todas las direcciones URL de la colección de sitios de SharePoint asociadas a los canales privados en el equipo y el identificador del grupo de equipos primario.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Para cada uno de los IDENTIFICADOres de grupo o equipo, ejecute el siguiente script de PowerShell para identificar todos los sitios de canal privado pertinentes, donde $groupID es el identificador de grupo del equipo.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensajes de canal privado en una búsqueda de eDiscovery

Antes de realizar estos pasos, asegúrese de que tiene instalada la [última versión del módulo de PowerShell de Teams](teams-powershell-overview.md) .

1. Ejecute lo siguiente para obtener una lista de canales privados en el equipo.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Ejecute lo siguiente para obtener una lista de miembros del canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Incluya los buzones de todos los miembros de cada canal privado del equipo como parte de la consulta de búsqueda de eDiscovery.

## <a name="advanced-ediscovery"></a>eDiscovery avanzado

El contenido de Microsoft Teams también se puede buscar y preservar con el [flujo de trabajo de EDiscovery avanzado](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20). Aunque eDiscovery proporciona una variedad de funciones de búsqueda, retención y exportación, la exhibición avanzada de datos por el administrador ofrece más herramientas para identificar los orígenes de datos y analizar su contenido.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flujo de trabajo de custodio avanzado para el contenido de Teams

Los custodios pueden ser miembros de diversos equipos. Puede capturar contenido de equipos que sea relevante para estos custodios. Para obtener más información sobre el flujo de trabajo de custodios, consulte [avanzado flujo de trabajo de eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

Después de agregar un custodio, haga clic en el botón **siguiente** y, después, en el botón **Agregar** . A continuación, aparece una ventana que le pide que seleccione ubicaciones adicionales, que le mostrarán todas las pertenencias del custodio y las ubicaciones del sitio de SharePoint correspondiente para sus datos. En todos estos orígenes de datos y equipos, puede elegir el contenido que desea usar para eDiscovery y, después, colocar ese usuario y todos los orígenes de datos que haya identificado en espera.

Puede seleccionar si desea incluir su contenido de Exchange, su contenido de OneDrive o ambos. El contenido de Exchange incluye todo el contenido de la aplicación en los buzones del usuario, como su correo electrónico, el contenido de los equipos que se almacena en su buzón, etc. El contenido de OneDrive no solo incluye el contenido del usuario, sino también todo el contenido de los equipos que se almacena en OneDrive, como chats de 1:1, 1: N chats y los archivos compartidos en los chats.

También tiene la opción de asociar cualquier equipo al que sea miembro el custodio, de modo que se incluyan los mensajes instantáneos de canal y los archivos a los que tiene acceso el custodio. Además, cualquier otro equipo se puede asociar con un custodio. Para obtener más información, consulte [Agregar custodios a un caso de EDiscovery avanzado](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).

> [!NOTE]
> eDiscovery de los mensajes y los archivos de los [canales privados](private-channels.md) funciona de forma diferente que en los canales estándar. Para obtener más información, consulte [eDiscovery of Private Channels](#ediscovery-of-private-channels).

### <a name="placing-a-data-source-on-hold"></a>Poner un origen de datos en espera

Si no hay un usuario específico para designar como custodio, puede poner un origen de datos completo en espera. Para obtener más información sobre las suspensiones, consulte [Administrar suspensiones en EDiscovery avanzado](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).

Al crear una suspensión para el contenido de Teams, puede elegir todas las ubicaciones que desea incluir en la espera. Incluso si los usuarios eliminan o cambian contenido, la retención conservará copias de todas las versiones anteriores de ese contenido.

También puede usar una consulta opcional para establecer condiciones para la retención según las palabras clave, el intervalo de fechas, el autor y otros muchos criterios. Si no especifica ninguna palabra clave, todo el origen de datos estará sujeto a la espera.

### <a name="advanced-ediscovery-searches"></a>Búsquedas avanzadas de eDiscovery

También se puede buscar en el contenido de Teams. Para obtener más información sobre las búsquedas, vea [recopilar datos para un caso en EDiscovery avanzado](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery). Una búsqueda devolverá una conversación completa si un mensaje coincide con la consulta de búsqueda.

Al crear una consulta de búsqueda, puede elegir custodios para que se busquen en todas las fuentes que ya haya seleccionado. También puede buscar fuentes que no sean de Private, como un sitio de teams que no está asignado a un usuario. Las consultas opcionales también están disponibles para restringir la búsqueda dentro del contenido de Teams.

Una vez que haya creado una búsqueda y la haya seleccionado, aparecerá una ventana con detalles y acciones adicionales que puede realizar con la búsqueda seleccionada. Si hace clic en el botón **estadísticas** , puede ver estadísticas sobre la búsqueda, incluidos desgloses según tipos de ubicación, la fuente original para el contenido y si el contenido se encuentra en un buzón de grupo, en el buzón de usuario individual o en un sitio de SharePoint. Por lo tanto, puede ver un desglose de las fuentes que contribuyen a los resultados de la búsqueda. También hay una vista **consultas** disponible para que pueda ver qué palabras clave individuales contribuyen a los resultados.

Después de finalizar la búsqueda, puede hacer clic en el botón **Agregar resultados a conjunto de revisiones** y agregarlo a un conjunto de revisiones. Para obtener más información acerca de los conjuntos de revisiones, consulte administrar el flujo [de trabajo avanzado en eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) y [conjuntos de revisiones](#review-sets-workflow) más adelante en este artículo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Conjuntos de revisión normales y conjuntos de revisión de conversaciones

Al agregar una búsqueda a un conjunto de revisiones, puede elegir un conjunto de revisiones normal o un conjunto de revisión de conversaciones.

Un conjunto de revisiones normal es similar a una exportación; proporciona los archivos individuales del `.msg` contenido de Teams y presenta el contenido en una vista básica. Normalmente, se usa un conjunto de revisión normal al planear el uso de otras herramientas de software para volver a procesar los archivos más adelante.

Un conjunto de revisión de conversaciones ofrece una vista más intuitiva y encadenada de las conversaciones; muestra los mensajes relacionados juntos en el orden correcto.

![Captura de pantalla del conjunto de revisión de conversación](media/conversationOptions2.png)

La funcionalidad, como censura, está disponible en ambos tipos de conjuntos de revisión. Para obtener más información acerca de los conjuntos de revisión, consulte [revisar las conversaciones en la exhibición avanzada de](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)datos.

#### <a name="collection-options"></a>Opciones de colección

Al agregar a un conjunto de revisiones, hay varias opciones disponibles como casillas de verificación en la sección **Opciones de recopilación** de la ventana, incluidas **las opciones de recuperación de conversaciones y las** conversaciones de **Teams**. Si habilita estas opciones, todos los mensajes de Teams individuales que forman parte de su conjunto de revisión también se mostrarán con mensajes adicionales que los rodean para el contexto. Por ejemplo, si la consulta es muy específica y solo se devuelve un mensaje como resultado, habilitar estas opciones también devolverá varios mensajes que dirigirán y seguirán el mensaje que coincide con la consulta.

Muchos criterios lógicos se usan para determinar si los mensajes adicionales proporcionan contexto a los mensajes que coinciden con la consulta. Por ejemplo, para el contenido de Teams, al habilitar estas opciones se recuperarán el mensaje principal y todos los mensajes secundarios debido a la forma en que se encadenan los mensajes.

También se marcan las marcas de tiempo del mensaje. Si un mensaje coincide con su consulta, los mensajes vecinos que lo preceden dentro de un período de 4 horas o que lo siguen dentro de un período de 4 horas se consideran parte de la conversación y también se incluyen en los resultados.

Si tiene la certeza de qué mensajes contextuales se devolverán con las coincidencias de la consulta de búsqueda, no es necesario que use estas opciones. Puede recopilar todo el contenido o bien ampliar el intervalo de fechas de la búsqueda para que se devuelvan más mensajes como resultado de la consulta.

### <a name="review-sets-workflow"></a>Revisar conjuntos flujo de trabajo

Para ver los conjuntos de revisiones existentes o crear nuevos, haga clic en la pestaña **Review sets** . Para obtener más información sobre los conjuntos de revisiones, consulte [administrar conjuntos de revisiones en la exhibición avanzada de](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)datos.

Además de los documentos, puede Agregar correos electrónicos, mensajes de equipo, mensajes de Yammer y otro contenido a su conjunto de revisión. Dentro de un conjunto de revisiones, también puede realizar muchas de las mismas acciones que puede realizar en otros contextos, como buscar contenido y crear consultas personalizadas. Estas operaciones solo se aplican a los elementos que se han agregado al conjunto de revisión.

El botón **administrar conjuntos de revisiones** proporciona opciones adicionales, como análisis, informes de Resumen, cuántos conjuntos de carga se han agregado, etc.

Para obtener acceso a las visualizaciones y los gráficos de **Individual results** los datos, haga clic \> en la **vista Perfil de búsqueda** de resultados individuales, en la esquina superior derecha. Puede hacer clic en porciones de estos gráficos para seleccionar de forma interactiva el tipo de contenido que desea consultar. Por ejemplo, puede elegir consultar solo el contenido de Teams. También puede guardar estas consultas de la misma manera en que guarda las consultas que escribe manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Vista de Resumen, vista de texto y vista de anotaciones

Si hace clic en una conversación de Teams en el conjunto de revisiones, se muestra la **vista de Resumen**, que muestra una conversación de equipos completa como una lista de mensajes con los que puede interactuar individualmente. Haga clic en la flecha abajo situada a la derecha de un mensaje para mostrar un menú contextual que le permite ver los detalles de los mensajes o descargar el `.msg` archivo individual. Al hacer clic en detalles del mensaje, se mostrará un resumen de los metadatos o los metadatos completos del mensaje.

Para descargar un archivo PDF, haga clic en el botón Descargar en la parte superior derecha de la vista de resumen.

Haga clic en la pestaña **vista de texto** para mostrar una vista de texto sin formato del texto extraído de la conversación de Teams. Este contenido de texto sin formato es apto para la exportación y puede trabajar fácilmente con él con otras herramientas de software.

Haga clic en la pestaña **vista anotar** para obtener acceso a las características de anotación. Esta pestaña muestra el contenido en un formato similar a una conversación de equipos, pero también hay opciones adicionales para la edición. Hay una herramienta de lápiz que puede usar para tomar notas, dibujar en el mensaje o realizar tareas de tachado específicas con fines de censura. También hay una herramienta de **redacción de área** que se puede usar para dibujar un rectángulo que represente el área en blanco y la marca como "censurada".

Este es un ejemplo de un archivo censurado para una conversación encadenada entre usuarios.

![Captura de pantalla del archivo censurado](media/RedactedFileExample.png)

En la parte inferior de la pestaña **vista anotar** se encuentra el botón **documentos de etiquetas** , que muestra el panel etiquetado. Dentro de este panel, puede aplicar una etiqueta a todos los mensajes de la conversación de Teams. Puede etiquetar una conversación como receptiva o sin respuesta, privilegiada o no, si contiene "elementos interesantes", si debe incluirse en la exportación y si necesita más revisión. También puede administrar y aplicar otras etiquetas personalizables.

#### <a name="action-menu"></a>Menú Acción

En la ventana de conjuntos de revisiones, puede exportar el contenido haciendo **Action** clic en \> **exportar**acción. Hay muchas opciones disponibles al exportar.

Para exportar un archivo que contiene todos los metadatos de todos los mensajes de Teams, haga clic para activar la casilla **Cargar archivo** . Para incluir en el archivo cualquier etiqueta que haya aplicado al contenido, haga clic para seleccionar la casilla **etiquetas** .

Use la opción **archivos nativos** para exportar archivos en su formato original. Puede optar por exportar una conversación como un archivo o todos los mensajes de chat individuales en sus propios archivos.

La opción **archivos de texto** le permite guardar versiones de texto sin formato de texto. Para obtener más información sobre cómo obtener una vista de texto sin formato de las conversaciones de Teams en el conjunto de revisiones, consulte vista de [Resumen, vista de texto y vista de anotaciones](#summary-view-text-view-and-annotate-view) .

Si aplicó censuras al contenido según se describe en la sección [vista de Resumen, vista de texto y vista de anotación](#summary-view-text-view-and-annotate-view) , puede seleccionar la opción reemplazar los **nativos censurados con archivos PDF convertidos** para reemplazar los archivos nativos por copias convertidas en PDF.

Puede exportar a un contenedor de almacenamiento de blobs de Azure proporcionado por Microsoft o puede proporcionar su propio contenedor de almacenamiento de blobs de Azure.

Cuando esté listo para comenzar el proceso de exportación, haga clic en el botón **exportar** . Consulte [Descargar trabajos de exportación](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) para obtener más información sobre cómo puede acceder al contenedor de almacenamiento de blobs de Azure y descargar el contenido exportado una vez completada la exportación.

> [!NOTE]
> La exportación puede tardar un período de tiempo prolongado. Para realizar un seguimiento del estado del proceso de exportación, salga de la pestaña **conjuntos de revisiones** y haga clic en la pestaña **exportaciones** .

## <a name="related-topics"></a>Temas relacionados

- [eDiscovery en Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
