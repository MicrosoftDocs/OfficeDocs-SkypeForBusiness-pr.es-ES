---
title: Administrar etiquetas en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo se usan las etiquetas en su organización en Microsoft Teams.
ms.openlocfilehash: bdb4fcbdd4c4d197dcdc778b9c15130071ad37fc
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267955"
---
# <a name="manage-tags-in-microsoft-teams"></a>Administrar etiquetas en Microsoft Teams

## <a name="overview"></a>Información general

Las etiquetas de Microsoft Teams permiten a los usuarios conectarse rápida y fácilmente con un subconjunto de personas de un equipo. Puede crear y asignar etiquetas personalizadas para clasificar personas en función de atributos, como rol, proyecto, aptitud o ubicación. O bien, las etiquetas se pueden asignar automáticamente a las personas en función de su información de horario y [turnos en la aplicación Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts). Después de agregar una etiqueta a uno o varios miembros del equipo, puede usarla en @mentions cualquier persona del equipo en una publicación de canal o para notificar solo a aquellas personas a las que se les asigne esa etiqueta de una conversación.

Como se mencionó anteriormente, hay dos tipos de etiquetas en Teams.

- **Etiquetas personalizadas**: los propietarios de equipos y los miembros del equipo (si la característica está habilitada para ellos) pueden crear y asignar etiquetas manualmente a los usuarios. Por ejemplo, una etiqueta "Diseñador" o "Radiólogo" llegará a esos conjuntos de personas de un equipo sin tener que escribir sus nombres.
- **Etiquetado por turno**: con esta característica, a los usuarios se les asignan etiquetas automáticamente que coinciden con su nombre de grupo de horario y [turnos en la aplicación Turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) en Teams. Por ejemplo, la etiqueta "EngineerOnCall" llega a todos los ingenieros programados en Turnos para trabajar en el momento en que la etiqueta se usa en una publicación de chat o canal. Con el etiquetado por turno, Teams elimina las conjeturas de conocer el nombre del personal en turnos cuando los usuarios necesitan retransmitir rápidamente información.

> [!NOTE]
> Las etiquetas no son compatibles con los canales privados o compartidos.

## <a name="how-tags-work"></a>Cómo funcionan las etiquetas

Una etiqueta se puede agregar manualmente o asignar automáticamente a una persona de un equipo específico. A continuación, se puede usar en @mentions en la línea **Para** de un chat o en una publicación en cualquier canal estándar del equipo. Estos son algunos ejemplos de cómo se pueden usar etiquetas en Teams:

- Un administrador de store publica un anuncio en un canal para notificar a todos los cajeros.
- Un administrador del hospital envía un mensaje a todos los radiólogos de un canal.
- Un administrador de marketing inicia un chat grupal con todos los diseñadores.

Cuando se @mentioned una etiqueta en una conversación de canal, se notificará a los miembros del equipo asociados a la etiqueta, igual que cualquier otro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Administrar etiquetas personalizadas para su organización

Como administrador, puede controlar cómo se usan las etiquetas en toda la organización en el Centro de administración de Microsoft Teams. Tenga en cuenta que no puede usar PowerShell para administrar etiquetas.

:::image type="content" source="media/manage-tags-admin-settings.png" alt-text="Captura de pantalla de la configuración de etiquetado en el Centro de administración de Microsoft Teams.":::

Un equipo puede tener hasta 100 etiquetas, hasta 100 miembros del equipo se pueden asignar a una etiqueta y se pueden asignar hasta 25 etiquetas a un solo usuario.

### <a name="set-who-can-add-custom-tags"></a>Establecer quién puede agregar etiquetas personalizadas

De forma predeterminada, los propietarios de equipos pueden agregar etiquetas personalizadas. Puede cambiar esta configuración para permitir que los propietarios del equipo y los miembros del equipo creen, editen, eliminen y administren etiquetas, o bien puede desactivar las etiquetas para su organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Configuración de** **Teams**\>.

2. En **Etiquetado**, junto a **Etiquetas administradas por**, seleccione una de las siguientes opciones:

    - **Propietarios y miembros** del equipo: permita que los propietarios y miembros del equipo administren etiquetas.
    - **Propietarios de equipos**: permita que los propietarios del equipo administren etiquetas.
    - **Deshabilitado**: desactive las etiquetas.

### <a name="configure-custom-tags-settings"></a>Configurar las opciones de etiquetas personalizadas

Puede configurar las siguientes opciones de etiquetas para controlar cómo se usan las etiquetas personalizadas en toda la organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Configuración de** **Teams**\>.

2. En **Etiquetado**, establezca lo siguiente, según las necesidades de su organización.

    - **Permitir que los propietarios del equipo invaliden quién puede administrar etiquetas**: al activar esta configuración, los propietarios del equipo pueden establecer si los miembros del equipo pueden crear y administrar etiquetas dentro de un equipo y el valor de las **etiquetas se administran mediante** la configuración es el valor predeterminado para cada equipo. Si desactiva esta configuración, no se pueden cambiar las **etiquetas por** equipo.
    - **Etiquetas predeterminadas sugeridas**: use esta opción para agregar un conjunto de etiquetas predeterminadas. Puede agregar hasta 25 etiquetas y cada etiqueta puede contener un máximo de 25 caracteres. Los propietarios y miembros del equipo (si la característica está habilitada para ellos) pueden usar estas sugerencias, agregarles o crear un nuevo conjunto de etiquetas.
    - **Permitir la creación de etiquetas personalizadas**: active esta opción para permitir que los usuarios agreguen etiquetas distintas de las etiquetas predeterminadas sugeridas que establezca. Si esta opción está desactivada, los usuarios solo podrán usar las etiquetas predeterminadas sugeridas. Si desactiva esta opción, asegúrese de agregar una o más etiquetas predeterminadas.

## <a name="related-topics"></a>Temas relacionados

[Usar etiquetas en Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Administrar la aplicación Turnos para su organización en Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentación de ayuda de Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
