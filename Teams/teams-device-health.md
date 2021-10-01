---
title: Administrar el estado de Teams dispositivos
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artículo le guiará en la administración del estado de Teams dispositivos, dispositivos que Microsoft Teams instalados en ellos.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: fae26365a09cab2705d4c7fee5d57c2135203a65
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045816"
---
# <a name="manage-the-health-of-teams-devices"></a>Administrar el estado de Teams dispositivos


Los administradores pueden supervisar el estado de los dispositivos instalados Microsoft Teams mediante el estado de estado, que indica la gravedad de los problemas. Para comprobar el estado de un dispositivo, puede ir a la lista de dispositivos presente en la sección Teams **dispositivos** del centro de administración Teams dispositivos. La columna estado de estado de esta lista indica el estado actual del dispositivo. Al seleccionar ese estado, se abrirá el **panel** Estado del estado, que proporciona más detalles sobre los problemas de estado.

Muchos tipos de problemas pueden contribuir al estado del dispositivo y el Teams centro de administración evalúa la gravedad de estos problemas a medida que se producen.

El administrador que administra Teams dispositivos de su organización puede decidir que la gravedad de los problemas no es la misma que la configuración predeterminada Teams proporciona. Los administradores pueden personalizar la gravedad y el impacto en el estado de sus dispositivos para que coincidan con las prioridades de su organización.

Salas de Teams dispositivos tienen periféricos conectados para proporcionar una experiencia de reunión completa, como altavoz, micrófono, pantalla, cámara. Los detalles sobre ellos están disponibles en la página del dispositivo en las pestañas Periféricos y Estado. La conectividad de estos periféricos afecta al estado del dispositivo principal.

## <a name="feature-details"></a>Detalles de características

Al ver detalles periféricos en una página de dispositivo, ahora verá una opción Administrar impacto  **en el** estado. Además, los administradores también pueden ver el impacto que tiene cada periférico en el estado del dispositivo.

De forma predeterminada, todos los periféricos están configurados para **que tengan un impacto crítico en** el estado del dispositivo. Si un periférico está desconectado, el estado  del dispositivo principal se convertirá en crítico y este problema se mostrará en Problemas críticos **en** el panel de estado de estado.

> [!NOTE]
> Las categorías periféricos **Ingerir HDMI** y Calcular no están disponibles para la personalización, ya que son cruciales para el funcionamiento del dispositivo principal. 

## <a name="how-does-this-work"></a>¿Cómo funciona?

1. Un administrador puede seleccionar los periféricos para los que desea cambiar el impacto en el estado. A continuación, pueden seleccionar **Administrar impacto en el estado.** Como alternativa, también pueden encontrar la opción Administrar impacto **en** el estado en la pestaña **Periféricos** de cada tarjeta periférico.
1. Se **abrirá el** panel Impacto del estado y el administrador podrá seleccionar el nivel de impacto deseado para los periféricos seleccionados y guardarlo.

| Configuración Opciones | Descripción |
|------------------|-------------|
| **No urgente** | Cuando se establece para una categoría de periférico (como una pantalla o un altavoz) y el periférico está desconectado, el estado de estado del dispositivo Salas de Teams pasará a ser no urgente **(en** lugar de **crítico).** Los nuevos problemas se clasificarán en la **sección No** urgente del panel de estado de estado.|
| **Sin impacto** | Cuando se establece para una categoría de periférico y el periférico está desconectado, el estado de estado del dispositivo Salas de Teams permanecerá en estado **correcto** (en lugar **de** crítico). Este problema de estado no se mostrará en el panel estado de estado.|
| **Crítico** | Cuando se establece para una categoría de periférico y el periférico está desconectado, el estado de estado del Salas de Teams dispositivo se convertirá en **Crítico.** Los nuevos problemas de este tipo se clasificarán en la **sección** Crítica del panel de estado de estado.|
| **Restablecer a predeterminado** | Cuando se establece para una categoría de periférico, el impacto en el estado de esa categoría se restablecerá a **Crítico.** Una vez guardada esta opción, los cambios se aplicarán y el impacto en el estado reflejará esos cambios en el futuro.|

## <a name="applicable-device-categories"></a>Categorías de dispositivo aplicables

Actualmente, esta característica está disponible para administrar el impacto en el estado de los periféricos asociados con Salas de Microsoft Teams (Windows) dispositivos.

## <a name="impact-on-other-workflows"></a>Impacto en otros flujos de trabajo

Si el impacto sobre el estado de los periféricos se reduce en gravedad, es posible que los administradores no notan problemas cuando se suceden. Debe tener en cuenta los dispositivos de alta prioridad que necesitan una supervisión estrecha.

Por ejemplo, si una alerta está configurada para activarse para ConfRoom1 si su estado se convierte en **crítico.** El administrador ha reducido el impacto en el estado de la pantalla y del orador de esa sala de reuniones de la predeterminada, **Crítica,** a **No urgente.** Ahora, si la pantalla está desconectada, el estado de ConfRoom1 pasará a **ser no urgente.** En este caso, la alerta no se activará.
