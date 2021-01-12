---
title: Etiquetas de confidencialidad de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo definir y usar etiquetas de confidencialidad en Microsoft Teams.
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795784"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etiquetas de confidencialidad de Microsoft Teams

[Las etiquetas de](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) confidencialidad permiten a los administradores de Teams regular el acceso al contenido organizativo confidencial creado durante la colaboración dentro de los equipos. Puede definir etiquetas de confidencialidad y sus directivas asociadas en el [Centro de cumplimiento.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) Estas etiquetas y directivas se aplican automáticamente a los equipos de su organización.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>¿Cuál es la diferencia entre las etiquetas de confidencialidad y las etiquetas de clasificación de Teams?

Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación. Las etiquetas de clasificación son cadenas de texto que se pueden asociar a un grupo de Microsoft 365 pero que no tienen directivas reales asociadas. Las etiquetas de clasificación se usan como metadatos para aplicar manualmente las directivas mediante scripts y herramientas internas.

Por otro lado, las etiquetas de confidencialidad y sus directivas se aplican automáticamente de un extremo a otro mediante una combinación de la plataforma Groups, el Centro de cumplimiento de & y los servicios de Teams. Las etiquetas de confidencialidad proporcionan una potente compatibilidad de infraestructura para proteger los datos confidenciales de su organización.  

Para migrar los grupos existentes desde el uso de etiquetas de clasificación hasta el uso de etiquetas de confidencialidad, use las instrucciones de clasificación y etiquetas de confidencialidad de Azure Active Directory para grupos [de Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Crear, administrar y publicar etiquetas de confidencialidad para Teams

Para obtener información sobre cómo habilitar, crear y publicar etiquetas de confidencialidad para Teams, consulte Usar etiquetas de confidencialidad para proteger el contenido de Microsoft Teams, grupos de [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)y sitios de SharePoint.

>[!IMPORTANT]
>Para crear, actualizar y eliminar etiquetas de confidencialidad es necesario un orden de orden cuidadoso con la publicación de etiquetas para los usuarios. Cualquier desviación de la secuencia puede provocar errores persistentes en la creación de equipos para todos los usuarios. Por lo tanto, es fundamental hacer <a href="#createpublishlabels"></a>lo siguiente cuando cree y publique etiquetas, <a href="#modifydeletelabels">modifique</a>y elimine etiquetas publicadas, y administre los errores de creación <a href="#manageerrors">de equipos.</a>

**Crear y publicar etiquetas** <a name="createpublishlabels"></a>

Cuando se crea y publica una etiqueta en el Centro de cumplimiento, la etiqueta puede tardar hasta 10 minutos en verse en la interfaz de creación de Teams. Siga estos pasos para publicar la etiqueta para todos los usuarios del inquilino:
1. Crear la etiqueta y publicarla para unas pocas cuentas de usuario en el espacio empresarial.
2. Cuando la etiqueta se publique, espere 10 minutos.
3. Después de 10 minutos, intente crear un equipo con la etiqueta con una de las cuentas de usuario que tienen acceso a la etiqueta.
4. Si el equipo se creó correctamente en el paso 3, a continuación, publique la etiqueta para el resto de los usuarios en el espacio empresarial.

**Modificar y eliminar etiquetas publicadas** <a name="modifydeletelabels"></a>

Eliminar o modificar la etiqueta mientras está asociada con directivas de confidencialidad puede provocar errores en la creación de equipos en el espacio empresarial. Por lo tanto, antes de eliminar o modificar una etiqueta, primero debe desasociar la etiqueta de las directivas asociadas. Siga estos pasos  
para eliminar o modificar una etiqueta:
1. Quite la etiqueta de todas las directivas que usan la etiqueta. Como alternativa, también puede eliminar las propias directivas.
2. Cuando la etiqueta se quite de las directivas o se eliminen, espere 10 minutos antes de continuar.
3. Después de 10 minutos, inicie la interfaz de creación del equipo y asegúrese de que la etiqueta ya no está visible para ningún usuario en el espacio empresarial.
4. Ahora puede eliminar o modificar la etiqueta de forma segura.

**Administrar errores de creación de equipos** <a name="manageerrors"></a>

Si la creación de equipos empieza a fallar en cualquier momento durante la vista previa pública, tiene dos opciones:
 - Asegúrese de que las etiquetas de confidencialidad no sean obligatorias para ningún usuario durante la creación de un equipo.
 - Desactive las etiquetas de confidencialidad con los scripts [en Habilitar esta vista previa.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)

Tenga en cuenta que el valor de EnableMIPLabels debe establecerse en false de la siguiente manera:

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Usar etiquetas de confidencialidad con Teams

Estos son algunos escenarios de ejemplo de cómo puede usar etiquetas de confidencialidad con Teams en su organización.

### <a name="privacy-setting-of-teams"></a>Configuración de privacidad de los equipos

Puede crear una etiqueta de confidencialidad que, cuando se aplique durante la creación del equipo, permita a los usuarios crear equipos con una configuración de privacidad específica (pública o privada).

Por ejemplo, si crea una etiqueta denominada "Confidencial" en el Centro de cumplimiento de & Seguridad y configura Teams, todos los equipos que se creen con esta etiqueta deben ser un equipo privado. Cuando un usuario crea un equipo  y selecciona la etiqueta Confidencial, la única opción de privacidad que está disponible para el usuario es **Privado.** Otras opciones de privacidad, como Público y toda la organización, están deshabilitadas para el usuario.

![Captura de pantalla de la etiqueta de confidencialidad confidencial](media/sensitivity-labels-confidential-example.png)

De forma similar, si el usuario selecciona **General** al crear un nuevo equipo, solo podrá crear equipos públicos o para toda la organización.

![Captura de pantalla de la etiqueta de confidencialidad general](media/sensitivity-labels-general-example.png)

Cuando se crea el equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo.

![Captura de pantalla de la etiqueta de confidencialidad en el canal del equipo](media/sensitivity-labels-channel.png)

El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento si va al equipo y hace clic en **Editar equipo.**

![Captura de pantalla de la etiqueta de confidencialidad en las propiedades del equipo](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Acceso de invitado a teams

Puede especificar si un equipo creado con una etiqueta específica permite el acceso de invitado. Los equipos creados con una etiqueta que no permite el acceso de invitado solo están disponibles para los usuarios de su organización. Las personas de fuera de su organización no se pueden agregar al equipo.

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Etiquetas de confidencialidad en el Centro de administración de Microsoft Teams

Puede establecer etiquetas de confidencialidad al crear o editar un equipo en el Centro de administración de Microsoft Teams. Las etiquetas de confidencialidad también  están visibles en las propiedades del equipo y en la columna Clasificación de la página Administrar equipos del Centro de administración de Microsoft Teams.

## <a name="known-issues"></a>Problemas conocidos

**Compatibilidad con etiquetas de confidencialidad en las API de Teams Graph, cmdlets y plantillas de PowerShell**

Actualmente, los usuarios no pueden aplicar etiquetas de confidencialidad a los equipos que se crean directamente a través de API de Graph, cmdlets de PowerShell y plantillas.

**Compatibilidad con etiquetas de confidencialidad en SKU de Teams EDU**

Las etiquetas de confidencialidad no son compatibles actualmente para los clientes que usan SKU de Teams Educación.

**Editar etiquetas de confidencialidad directamente en una colección de sitios de SharePoint para canales privados**

Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó en un equipo. Además, la misma etiqueta se aplica automáticamente en la colección de sitios de SharePoint para el canal privado.

Si un usuario actualiza directamente la etiqueta de confidencialidad de una colección de sitios de SharePoint para un canal privado, esa etiqueta no se actualizará en el cliente de Teams. En este escenario, los usuarios seguirán ver la etiqueta de confidencialidad aplicada a un equipo en el encabezado de canal privado.

**Tiempos de propagación de cambios aplicados a etiquetas de confidencialidad fuera de la aplicación de Teams**

Los cambios realizados en las etiquetas de confidencialidad fuera de la aplicación Teams pueden tardar hasta 24 horas en reflejarse en la aplicación teams. Esto se aplica a los cambios realizados para habilitar o deshabilitar las etiquetas para un inquilino, los cambios en los nombres de etiqueta, la configuración y las directivas.

Además, cualquier cambio realizado en una etiqueta directamente en un grupo o una colección de sitios de SharePoint que haga copia de seguridad del equipo puede tardar hasta 24 horas en propagarse a la aplicación Teams.
