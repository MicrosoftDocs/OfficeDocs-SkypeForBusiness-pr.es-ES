---
title: Configurar reuniones de Teams con tres niveles de protección
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365solution-overview
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Obtenga información sobre cómo configurar reuniones de Teams para mejorar la seguridad con tres niveles de protección, equilibrando la seguridad con la facilidad de colaboración.
ms.openlocfilehash: 607c4d484df714fd4fba736ffd618aafdbab67d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800127"
---
# <a name="configure-teams-meetings-with-three-tiers-of-protection"></a>Configurar reuniones de Teams con tres niveles de protección

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Los artículos de esta serie proporcionan opciones para usar las características de cumplimiento disponibles en Teams y Microsoft 365 con el fin de crear un entorno de reuniones que cumpla los requisitos de cumplimiento normativo. Analizaremos las opciones disponibles con etiquetas y plantillas de confidencialidad y cómo puede usarlas junto con otras opciones de configuración de administrador de Teams.

> [!Note]
> La configuración de reuniones en etiquetas de confidencialidad y plantillas de reunión personalizadas requieren Teams Premium.

En este artículo se definen cuatro configuraciones diferentes, comenzando con una configuración de línea base para reuniones que no tienen requisitos de cumplimiento específicos. Cada configuración adicional representa un paso significativo en la protección a medida que las opciones de reunión están más restringidas. Las configuraciones de este artículo proporcionan ejemplos de cómo configurar la protección para reuniones con distintos niveles de confidencialidad. Use estos ejemplos para comprender lo que es posible y modificar la configuración específica según sea necesario para su organización.

Explicaremos estas tres configuraciones:

- Protección de línea base

- Protección confidencial

- Protección altamente sensible

Además, explicaremos una variación de la configuración altamente confidencial que está diseñada para presentaciones que tienen interacción mínima de los asistentes.

## <a name="three-tiers-at-a-glance"></a>Tres niveles de un vistazo

En la tabla siguiente se resumen las configuraciones para cada nivel. Use estas configuraciones como recomendaciones de punto de partida y ajuste las configuraciones para satisfacer las necesidades de su organización. Según sus necesidades de cumplimiento, es posible que no necesite cada nivel.

|&nbsp;|Base|Sensible|Altamente sensible|Presentación altamente confidencial|
|:-----|:-----|:-----|:-----|:-----|
|Permitir cámara para los asistentes|**On**|**On**|**On**|**Desactivado**|
|Permitir micrófono para los asistentes|**On**|**On**|**On**|**Desactivado**|
|Aplicar una marca de agua a la fuente de vídeo de todos|**Desactivado**|**Desactivado**|**On**|**On**|
|Aplicar una marca de agua al contenido compartido|**Desactivado**|**Desactivado**|**On**|**On**|
|Cifrado de un extremo a otro|**Desactivado**|**Desactivado**|**On**|**On**|
|Administrar lo que ven los asistentes|**Desactivado**|**On**|**On**|**On**|
|Chat de reunión|**On**|**On**|**Solo en reunión**|**Desactivado**|
|Personas marcación puede omitir la sala de espera|**Desactivado**|**Desactivado**|**Desactivado**|**Desactivado**|
|Impedir copiar el contenido del chat en el Portapapeles|**Desactivado**|**Desactivado**|**On**|**On**|
|Grabar automáticamente|**Desactivado**|**Desactivado**|**Desactivado**|**Desactivado**|
|Quién puede omitir la sala de espera|**Personas en mi organización, personas en dominios de confianza e invitados**|**Personas invito**|**Solo yo y los co-organizadores**|**Solo yo y los co-organizadores**|
|Quién puede presentar|**Usuarios en mi organización e invitados**|**Usuarios en mi organización e invitados**|**Solo los organizadores y co-organizadores**|**Solo los organizadores y co-organizadores**|
|Quién puede grabar|**Organizadores y moderadores**|**Organizadores y co-organizadores**|Deshabilitada debido a la marca de agua|Deshabilitada debido a la marca de agua|

Los detalles sobre cómo configurar cada nivel están cubiertos en:

- [Configurar reuniones de Teams con protección de línea base](configure-meetings-baseline-protection.md)
- [Configurar reuniones de Teams con protección para datos confidenciales](configure-meetings-sensitive-protection.md)
- [Configurar reuniones de Teams con protección para datos altamente confidenciales](configure-meetings-highly-sensitive-protection.md)

## <a name="managing-compliance-with-sensitivity-labels-and-meeting-templates"></a>Administrar el cumplimiento con etiquetas de confidencialidad y plantillas de reunión

Tanto las plantillas de reunión como las etiquetas de confidencialidad pueden exigir determinadas configuraciones de reunión. La mayoría de las opciones de configuración se pueden aplicar como activadas o desactivadas, o se pueden dejar sin configurar para que el organizador de la reunión pueda establecerlas.

> [!Important]
> Algunas características se [controlan mediante directivas de administración](meeting-templates-sensitivity-labels-policies.md#policies-labels-templates-and-meetings-settings) y deben habilitarse allí para poder controlarse mediante plantillas de reunión y etiquetas de confidencialidad.

Algunas opciones de configuración solo están disponibles en etiquetas de confidencialidad y algunas solo están disponibles en plantillas. Hay varios disponibles en ambos casos:

- Chat
- Cifrado de un extremo a otro
- Configuración de la sala de espera
- Grabación de la reunión
- Marca de agua

Las etiquetas y plantillas de confidencialidad se pueden usar conjuntamente para ayudarle a satisfacer sus necesidades de cumplimiento normativo. Para obtener más información, vea [Usar plantillas de reunión de Teams, etiquetas de confidencialidad y directivas de administración juntas](meeting-templates-sensitivity-labels-policies.md).

## <a name="meeting-chat"></a>Chat de reunión

El chat de la reunión puede ser una parte importante de la colaboración durante una reunión. Sin embargo, es posible que desee restringir el chat de reuniones en determinados tipos de reuniones para evitar que se comparta información confidencial allí.

Como administrador, puede controlar el chat de la reunión de las siguientes maneras:

- La **directiva de reunión de administración de Teams** (por usuario o grupo) se puede usar para permitir el chat, permitir el chat para todos excepto los participantes anónimos o desactivar el chat.
- **La configuración de etiqueta de confidencialidad** (por reunión) puede exigir que el chat esté activado, desactivado o permitido solo durante la reunión. Esta configuración puede dejarse sin configurar para que la controle una plantilla o el organizador de la reunión.
- **La configuración de la plantilla de** reunión (por reunión) puede exigir que el chat esté activado, desactivado o permitido solo durante la reunión. Esta configuración puede dejarse sin configurar para que el organizador de la reunión la controle.

Para los tres niveles de protección, permitimos el chat para reuniones de línea base y confidenciales, y lo restringimos en reuniones altamente confidenciales a solo dentro de la reunión.

Para obtener más información, vea [Administrar el chat para reuniones confidenciales de Teams](manage-chat-sensitive-meetings.md).

## <a name="meeting-recordings"></a>Grabaciones de reuniones

Como administrador, puede controlar las grabaciones de reuniones de las siguientes maneras:

- Directiva de reunión de administrador de grabación en la **nube** (por usuario o grupo)
- La directiva de reunión de administrador **Reuniones expira automáticamente** (eliminación de la grabación) (por usuario o grupo)
- La configuración **Quién puede grabar** en etiquetas de confidencialidad y plantillas de reunión (por reunión)
- La configuración **Grabar automáticamente** en etiquetas de confidencialidad y plantillas de reunión (por reunión)

Si su organización o determinados usuarios o grupos dentro de ella nunca deberían poder grabar reuniones, puede desactivar la característica mediante la directiva de reunión de administrador de grabación en la **nube** .

Si hay ciertos tipos de reuniones que deben grabarse siempre, puede aplicar la configuración **Grabar automáticamente** con una plantilla de reunión o una etiqueta de confidencialidad.

Dentro de los tres niveles descritos aquí, la grabación se deshabilita en las reuniones altamente confidenciales porque estamos usando el cifrado de un extremo a otro y marcas de agua en contenido compartido y vídeo. Si necesita poder grabar reuniones altamente confidenciales, asegúrese de no exigir marcas de agua ni cifrado de un extremo a otro con la etiqueta de confidencialidad. Los organizadores de la reunión pueden seguir usando el cifrado de un extremo a otro y aplicar marcas de agua si no se graba una reunión determinada.

Para obtener más información sobre cómo administrar las opciones de grabación de reuniones, consulte [Administrar las opciones de grabación de reuniones de Microsoft Teams para reuniones confidenciales](manage-meeting-recording-options.md).

Para obtener información sobre la grabación basada en directivas de reuniones para el cumplimiento, vea [Introducción a la grabación basada en directivas de Teams para llamadas & reuniones](teams-recording-policy.md).

## <a name="meeting-with-guests-and-external-participants"></a>Reunión con invitados y participantes externos

Hay tres tipos de participantes externos que pueden unirse a las reuniones:

- Participantes de dominios de confianza
- Invitados
- Participantes anónimos

Los participantes de dominios de confianza se unen a las reuniones a través de la característica de [acceso externo](manage-external-access.md) . Puede controlar en qué dominios, si los hay, su organización quiere confiar. (Esta configuración también afecta a 1:1 y al chat grupal con personas de esos dominios).

Si [el acceso de invitado de Teams](guest-access.md) está habilitado para su organización, los invitados podrán unirse a las reuniones. La configuración de acceso de invitado también se puede usar para controlar el modo de pantalla compartida de los invitados, incluida la deshabilitación del uso compartido de la pantalla. (El acceso de invitado también se usa para invitar a invitados a equipos).

Si la opción **Usuarios anónimos pueden unirse a una reunión** , la opción De administrador de Teams está activada, los participantes anónimos podrán unirse a las reuniones.

Aunque puede desactivar completamente la unión anónima sin afectar a características que no sean reuniones, tanto el acceso de invitado como los dominios de confianza se usan en escenarios fuera de las reuniones. Si desea restringir el acceso a la reunión a estos participantes pero necesita dejar activadas las características por otros motivos, debe usar la sala de espera.

## <a name="lobby-options"></a>Opciones de sala de espera

La sala de espera de la reunión permite a los organizadores de la reunión supervisar a los asistentes antes de permitirles entrar en la reunión. Según el tipo de reunión y los requisitos de cumplimiento, es posible que quiera permitir que todos los asistentes omitan la sala de espera y se unan a la reunión directamente, o mantener determinados tipos de asistentes en la sala de espera hasta que un organizador de la reunión los admita. Si desea impedir que ciertos tipos de personas, como invitados, asistan a reuniones, puede pedirles que pasen por la sala de espera y, a continuación, el organizador de la reunión puede denegarles la admisión.

Para el nivel de línea base, permitimos que todos los asistentes excepto los anónimos omitan la sala de espera. Para las reuniones confidenciales, permitimos que solo las personas con una invitación de reunión omitan la sala de espera. Para las reuniones altamente confidenciales, es necesario que los organizadores admitan a cada asistente.

Como administrador, puede controlar la sala de espera de las siguientes maneras:

- La **directiva Admitir automáticamente la** reunión de administrador de personas (por usuario o grupo)
- Los **usuarios de acceso telefónico local pueden omitir la directiva** de reunión del administrador de la sala de espera (por usuario o grupo)
- La configuración **Quién puede omitir la sala de espera** en etiquetas de confidencialidad y plantillas de reunión (por reunión)
- El **Personas marcar puede omitir la** directiva de reunión del administrador de la sala de espera (por usuario o grupo) o en etiquetas de confidencialidad y plantillas de reunión (por reunión)

Esta configuración también está disponible para el organizador de la reunión, a menos que haya sido bloqueada por una etiqueta o plantilla de confidencialidad.


Aunque la directiva de administrador establece un valor predeterminado, necesita una plantilla o etiqueta para aplicar


Si se encuentra en un sector muy regulado y necesita admitir manualmente a cada asistente en todas las reuniones de su organización, puede configurar la sala de espera mediante las directivas de reuniones de administración del Centro de administración de Teams. Si su organización tiene diferentes tipos de reuniones que tienen diferentes requisitos de sala de espera, le recomendamos que use plantillas de reunión o etiquetas de confidencialidad para configurar estas opciones.

Para obtener más información, consulte [Configurar la sala de espera de reunión de Microsoft Teams para reuniones confidenciales](configure-lobby-sensitive-meetings.md)

## <a name="related-topics"></a>Temas relacionados

[Ilustraciones de microsoft cloud para arquitectos empresariales](/microsoft-365/solutions/cloud-architecture-models)

[Usar etiquetas de confidencialidad para proteger los elementos del calendario, las reuniones y el chat de Teams](/microsoft-365/compliance/sensitivity-labels-meetings)
