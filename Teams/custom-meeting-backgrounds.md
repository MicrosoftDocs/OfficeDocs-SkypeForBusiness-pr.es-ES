---
title: Fondos de reunión personalizados para reuniones de Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Usar activos corporativos aprobados como fondos para crear fondos personalizados para las reuniones de Teams dentro de su organización.
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800222"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Fondos de reunión personalizados para reuniones de Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>Información general

La personalización en las reuniones de Teams permite a las organizaciones ampliar sus identidades visuales en toda la experiencia de reunión. Usar fondos de reuniones personalizados ayuda a fomentar la creación de cultura corporativa interna y aumentar el conocimiento general de la marca con los participantes de reuniones internas y externas. Con la ayuda de los equipos de comunicaciones corporativas y de administración de marca de una organización, los administradores pueden configurar y crear fácilmente fondos de reuniones personalizados para varias unidades de negocio y departamentos dentro de un único inquilino.

De forma predeterminada, los usuarios con licencia premium de Teams que sean administradores o que tengan asignada una directiva de personalización de reuniones pueden crear reuniones con fondos de reunión personalizados. Estos fondos personalizados solo estarán disponibles para los usuarios finales de su organización que tengan una licencia de Teams Premium para usar.

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar fondos de reunión personalizados para las reuniones de Teams, compruebe que tiene los siguientes elementos:

- Acceso a la SKU de Teams Premium
- Es un administrador con acceso al Centro de administración de Teams o se le ha asignado una directiva de personalización
- Ha habilitado la directiva de [fondo personalizada](#enabling-the-custom-background-policy)
- Las imágenes de fondo cumplen las [especificaciones necesarias](#adding-custom-background-images)

## <a name="setting-up-custom-meeting-backgrounds"></a>Configurar fondos de reunión personalizados

Los administradores pueden cargar y administrar fondos de reunión personalizados para las reuniones de Teams en el Centro de administración de Teams.

### <a name="enabling-the-custom-background-policy"></a>Habilitar la directiva de fondo personalizada

Como administrador, para crear fondos personalizados, deberá crear una nueva directiva de personalización de reuniones o modificar la directiva predeterminada global de la organización.
Para habilitar la directiva de fondo personalizada, los administradores realizarán los pasos siguientes:

1. Abrir el Centro de administración de Teams
2. Seleccione **Reuniones** en el panel de navegación
3. En Reuniones, hay dos formas de acceder a la directiva de fondo personalizada. Puede seleccionar **Directivas de personalización** para seleccionar una directiva existente o crear una nueva. Como alternativa, puede seleccionar **Directivas de reunión** y, a continuación, seleccionar el botón **Imágenes de reunión personalizadas** en la esquina superior derecha.
4. Dentro de la directiva elegida, vaya a la sección **Fondos de reunión personalizados**
5. Cambie la configuración de **Fondos personalizados** de desactivado a activado para habilitar la configuración
6. Selecciona **Guardar**

### <a name="adding-custom-background-images"></a>Agregar imágenes de fondo personalizadas

Ahora que ha habilitado la directiva de fondo personalizada, puede cargar las imágenes de fondo personalizadas. Estas imágenes aparecerán en las interfaces de los usuarios finales, ordenadas por el momento de la carga.

Las cargas deben cumplir los siguientes parámetros. Los administradores pueden cargar:

- Formatos de imagen PNG y JPEG para sus imágenes
- Imágenes con dimensiones mínimas de 360 px x 360 px
- Imágenes con dimensiones mínimas de 3840 px X 2160 px
- Un máximo de 50 imágenes de fondo personalizadas

Para cargar las imágenes, vaya a **Directivas de personalización** de **reuniones** >  y seleccione la directiva del paso anterior. Desplácese hacia abajo hasta la sección **Fondos de reunión personalizados** y, debajo de la tabla con el botón de alternancia del fondo personalizado, seleccione **+Agregar**. Después de seleccionar +Agregar, se abrirá un panel llamado **Administrar fondos** , que le permite agregar las imágenes.

> [!NOTE]
> Solo los usuarios finales con una licencia de Teams Premium verán estas imágenes en el panel Configuración de fondo.

### <a name="saving-custom-background-images"></a>Guardar imágenes de fondo personalizadas

Encontrará vistas previas de las imágenes cargadas en una tabla nueva en la sección **Fondos de reunión personalizados** . Esta tabla también muestra el nombre y la resolución de las imágenes. Una vez que confirmes la elección de las imágenes cargadas, selecciona el botón **Guardar** debajo de la tabla de vista previa. Ahora que ha seleccionado guardar, los fondos cargados son visibles para los usuarios finales con una licencia de Teams Premium.

## <a name="where-are-custom-backgrounds-visible"></a>¿Dónde están visibles los fondos personalizados?

La siguiente lista muestra los clientes compatibles donde se ven fondos personalizados:

- Cliente Web
- Cliente de escritorio
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>Quién puede seleccionar y aplicar fondos de reunión personalizados

Solo Teams Premium usuarios con licencia pueden usar los fondos de la reunión en su panel Configuración de fondo.

> [!NOTE]
> Los usuarios externos o anónimos no pueden usar fondos de reunión personalizados.

### <a name="who-can-view-custom-meeting-backgrounds"></a>Quién puede ver fondos de reunión personalizados

Aunque solo los usuarios finales con licencia pueden seleccionar su elección de fondos cargados, cualquiera puede ver el fondo que se aplica a una reunión. Entre estos usuarios se incluyen:

- En el espacio empresarial, Teams Premium usuarios con licencia
- Usuarios sin licencia en el espacio empresarial
- Usuarios externos
- Usuarios anónimos
