---
title: Etiquetas de confidencialidad para Microsoft Teams
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 4f1bdc4715fd1375cff637604c93962e2f30c258
ms.sourcegitcommit: d7f49f8c28cba32d3715ea1965c736e6ba574bda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091273"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etiquetas de confidencialidad para Microsoft Teams

Las [etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permiten a los administradores de equipos regular el acceso a contenido de organización confidencial creado durante la colaboración dentro de Teams. Puede definir las etiquetas de confidencialidad y las directivas asociadas en el [centro de cumplimiento de & de seguridad](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center). Estas etiquetas y directivas se aplican automáticamente a los equipos de su organización.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>¿Cuál es la diferencia entre las etiquetas de confidencialidad y las etiquetas de clasificación de equipos?

Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación que requieren su creación con PowerShell. Las etiquetas de clasificación son cadenas de texto que se pueden asociar a un grupo pero que no tienen ninguna directiva real asociada. Use las etiquetas de clasificación como metadatos para aplicar manualmente las directivas a través de las herramientas y scripts internos.

Por otro lado, las etiquetas de confidencialidad y sus directivas se aplican de forma automática de principio a fin a través de una combinación de la plataforma de grupos, el centro de cumplimiento de & de seguridad y los servicios de Teams. Las etiquetas de confidencialidad proporcionan una eficaz compatibilidad de infraestructura para proteger los datos confidenciales de su organización.  

Para migrar los grupos existentes y usar etiquetas de clasificación para usar las etiquetas de confidencialidad, use las instrucciones de [clasificación de Azure Active Directory y etiquetas de confidencialidad para los grupos de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Crear, administrar y publicar etiquetas de confidencialidad para equipos

Para obtener información sobre cómo habilitar, crear y publicar etiquetas de confidencialidad para Teams, vea [clasificación de Azure Active Directory y etiquetas de confidencialidad para grupos de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

>[!IMPORTANT]
>Crear, actualizar y eliminar etiquetas de confidencialidad requieren una secuenciación cuidadosa con etiquetas de publicación para los usuarios. Cualquier desviación en la secuencia puede dar lugar a errores de creación de equipo persistente para todos los usuarios. Por lo tanto, es esencial que haga lo siguiente cuando <a href="#createpublishlabels">cree y publique etiquetas</a>, <a href="#modifydeletelabels">modifique y elimine etiquetas publicadas</a>y <a href="#manageerrors">administre errores de creación de equipos</a>.

**Crear y publicar etiquetas** <a name="createpublishlabels"> </a>

Cuando se crea una etiqueta y se publica en el centro de cumplimiento de seguridad &, la etiqueta puede tardar hasta 10 minutos en verse en la interfaz de creación de equipos. Realice los siguientes pasos para publicar la etiqueta de todos los usuarios del espacio empresarial:
1. Cree la etiqueta y publíquela para algunas cuentas de usuario seleccionadas en el inquilino.
2. Cuando se publique la etiqueta, espere 10 minutos.
3. Después de 10 minutos, intente crear un equipo con la etiqueta usando una de las cuentas de usuario que tengan acceso a la etiqueta.
4. Si el equipo se creó correctamente en el paso 3, continúe y publique la etiqueta para el resto de usuarios del espacio empresarial.

**Modificar y eliminar las etiquetas** <a name="modifydeletelabels"> </a> publicadas

Eliminar o modificar la etiqueta mientras está asociada a directivas de confidencialidad puede dar lugar a errores en la creación del equipo en el inquilino. Por lo tanto, antes de eliminar o modificar una etiqueta, primero debe desvincular la etiqueta de sus directivas asociadas. Siga estos pasos  
para eliminar o modificar una etiqueta:
1. Quite la etiqueta de todas las directivas que usan la etiqueta. También puede eliminar las directivas en sí.
2. Cuando se elimine la etiqueta de las directivas o se eliminen las directivas, espere 10 minutos antes de continuar.
3. Después de 10 minutos, inicie la interfaz de creación de equipos y asegúrese de que la etiqueta ya no está visible para los usuarios del espacio empresarial.
4. Ahora puede eliminar o modificar la etiqueta de forma segura.

**Administrar errores** <a name="manageerrors"> </a> de creación de equipos

Si la creación del equipo comienza a fallar en cualquier momento durante la versión preliminar pública, tiene dos opciones:
 - Asegúrese de que las etiquetas de confidencialidad no son obligatorias para ningún usuario durante la creación del equipo.
 - Desactive las etiquetas de confidencialidad usando los scripts en [habilitar esta vista previa](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).

Observe que la configuración EnableMIPLabels debe establecerse en falso de la siguiente manera:

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Usar etiquetas de confidencialidad con equipos

A continuación se muestran algunos escenarios de ejemplo de cómo puede usar las etiquetas de confidencialidad con equipos de su organización.

### <a name="privacy-setting-of-teams"></a>Configuración de privacidad de Teams

Puede crear una etiqueta de confidencialidad que, cuando se aplique durante la creación del equipo, permita a los usuarios crear equipos con una configuración de privacidad (pública o privada) específica.

Por ejemplo, puede crear una etiqueta denominada "confidencial" en el centro de cumplimiento de & de seguridad y configurar Teams de modo que cualquier equipo que se cree con esta etiqueta debe ser un equipo privado. Cuando un usuario crea un nuevo equipo y selecciona la etiqueta **confidencial** , la única opción de privacidad que está disponible para el usuario es **privada**. Otras opciones de privacidad, como público y toda la organización, están deshabilitadas para el usuario.

![Captura de pantalla de etiqueta confidencial confidencial](media/sensitivity-labels-confidential-example.png)

De forma similar, si el usuario selecciona **General** al crear un equipo nuevo, solo podrá crear equipos públicos o de toda la organización.

![Captura de pantalla de etiqueta de confidencialidad general](media/sensitivity-labels-general-example.png)

Cuando se crea el equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo.

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo](media/sensitivity-labels-channel.png)

El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento al ir al equipo y, a continuación, hacer clic en **Editar equipo**.

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Acceso de invitado a equipos

Puede especificar si un equipo creado con una etiqueta específica le permite el acceso de invitado. Los equipos creados con una etiqueta que no permite el acceso de invitados solo están disponibles para los usuarios de su organización. Las personas de fuera de su organización no se pueden agregar al equipo.

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Etiquetas de confidencialidad en el centro de administración de Microsoft Teams

Puede establecer las etiquetas de confidencialidad al crear o editar un equipo en el centro de administración de Microsoft Teams. Las etiquetas de confidencialidad también están visibles en las propiedades del equipo y en la columna **clasificación** de la página administrar equipos del centro de administración de Microsoft Teams.

## <a name="known-issues"></a>Problemas conocidos

**No se muestran las etiquetas secundarias predeterminadas durante la creación del equipo**

En este momento, un conjunto de etiquetas secundarias como la etiqueta predeterminada de Teams no se mostrará en la parte superior de la lista en el menú desplegable de etiquetas de confidencialidad en el modelo de creación de equipo. Los creadores de equipos aún pueden usar la lista desplegable para aplicar la etiqueta secundaria como solución alternativa.

**Compatibilidad con etiquetas de confidencialidad en las API de Team Graph, plantillas y cmdlets de PowerShell**

En la actualidad, los usuarios no podrán aplicar etiquetas de confidencialidad a los equipos que se crean directamente a través de las API de Graph, los cmdlets de PowerShell y las plantillas.

**Compatibilidad con etiquetas de confidencialidad en SKU de los equipos EDU**

Las etiquetas de confidencialidad actualmente no son compatibles con los clientes que usan las SKU de Educación de Teams.

**Editar las etiquetas de confidencialidad directamente en una colección de sitios de SharePoint para canales privados**

Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó a un equipo. Además, la misma etiqueta se aplica automáticamente en la colección de sitios de SharePoint para el canal privado.

Si un usuario actualiza directamente la etiqueta de confidencialidad en una colección de sitios de SharePoint para un canal privado, esa etiqueta no se actualiza en el cliente de Teams. En este caso, los usuarios seguirán viendo la etiqueta de confidencialidad aplicada a un equipo en el encabezado de canal privado.

**Horas de propagación para los cambios aplicados a las etiquetas de confidencialidad fuera de la aplicación de Teams**

Los cambios realizados en las etiquetas de confidencialidad fuera de la aplicación Teams pueden demorar hasta 24 horas en reflejarse en la aplicación de Teams. Esto se aplica a los cambios realizados para habilitar o deshabilitar las etiquetas de un espacio empresarial, los cambios en los nombres de etiqueta, la configuración y las directivas.

Además, cualquier cambio en una etiqueta realizada directamente a un grupo o una colección de sitios de SharePoint que respalda al equipo puede demorar hasta 24 horas en propagarse a la aplicación de Teams.
