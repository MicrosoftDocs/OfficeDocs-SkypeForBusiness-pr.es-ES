---
title: Directiva de llamada en Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Obtenga información acerca de la configuración de la directiva de llamada en Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860268"
---
<a name="calling-policy-in-microsoft-teams"></a>Directiva de llamada en Microsoft Teams
==========================================

En Microsoft Teams, llamar al control de las directivas que la llamada a y las características de desvío de llamadas están disponibles para los usuarios. Las directivas de la llamada a determinan si un usuario puede realizar llamadas privadas, use el desvío de llamadas o llamadas a otros usuarios o números de teléfono externos simultáneas, enrutar las llamadas al correo de voz, enviar las llamadas a grupos de llamadas, delegación para las llamadas entrantes y salientes, y así sucesivamente. Una directiva global predeterminada se crea automáticamente, pero los administradores también pueden crear y asignar directivas de llamada personalizadas.

## <a name="calling-policy-settings"></a>Configuración de la directiva de llamada

|Configuración de directiva de llamada | Descripción |
|-----------------------|-------------|
|Usuario puede realizar llamadas privadas | Controla todas las capacidades de llamada en los equipos. Desactivación de esto va a desactivar toda la funcionalidad de llamada en los equipos.|
|Desvío de llamadas y las llamadas simultáneas a otros usuarios | Controla si las llamadas entrantes pueden transferirse a otros usuarios o pueden llamar a otra persona al mismo tiempo. |
|Desvío de llamadas y las llamadas simultáneas a números de teléfono externos | Controla si las llamadas entrantes se pueden reenviar a un número externo o pueden llamar a un número externo al mismo tiempo.|
|Correo de voz está disponible para enrutar las llamadas entrantes a los usuarios | Permite las llamadas entrantes que se envíen al correo de voz. Las opciones válidas son **siempre activado**, **siempre deshabilitado**o **controlado de usuario**. |
|Se pueden redirigir las llamadas entrantes para llamar a grupos | Controla si se pueden reenviar las llamadas entrantes a un grupo de llamada.  |
|Permitir la delegación de las llamadas entrantes y salientes | Permite las llamadas entrantes deben enrutarse a delegados; permite a los delegados realizar llamadas salientes en nombre de los usuarios para quienes se delega permisos. |
|Evitar el desvío de pago y enviar las llamadas a través de la RTC | Si se establece en **** va a enviar las llamadas a través de RTC e incurrir en los cargos en lugar de pasar por la red y omitir el cuotas. |
|No disponible en no disponible está disponible mientras se encuentre en una llamada.| Configura las llamadas entrantes cómo se controlan cuando un usuario ya está en una llamada o conferencia. Se pueden rechazar las llamadas entrantes o nuevo con una señal de ocupado. |

## <a name="create-a-custom-calling-policy"></a>Crear una directiva llamada personalizada

Siga estos pasos para crear una nueva directiva llamada personalizada.

1. En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.
2. Seleccione **nueva directiva**.
3. Activar las características que desea usar en la directiva de llamada. Todas las selecciones están **desactivadas** de forma predeterminada.
4. Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**. Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.
5. Seleccione **Guardar**.

## <a name="modify-an-existing-calling-policy"></a>Modificar una directiva de llamada existente

Siga estos pasos para modificar una directiva de llamada existente.

1. En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.
2. Haga clic en junto a la directiva que desea modificar y, a continuación, seleccione **Editar**.
3. Activar las características que desea usar en la directiva de llamada. Todas las selecciones están **desactivadas** de forma predeterminada.
4. Para controlar si los usuarios pueden enrutar las llamadas entrantes al correo de voz, seleccione **siempre habilitado** o **bajo control de usuario**. Para evitar que el enrutamiento al correo de voz, seleccione **siempre deshabilitado**.
5. Seleccione **Guardar**.

## <a name="assign-a-calling-policy-to-a-user"></a>Asignar una directiva de llamada a un usuario

Siga estos pasos para asignar una directiva personalizada que llama a un usuario.

1. En el centro de administración de Microsoft Teams, seleccione **voz** > **Directiva de llamada**.
2. Haga clic en junto al nombre de directiva para seleccionarlo y, a continuación, seleccione **Administrar usuarios**.
3. En el panel **Administrar usuarios** , buscar el nombre del usuario. (Debe escribir al menos tres caracteres).
4. Seleccione el nombre del usuario y, a continuación, seleccione **Agregar**.
5. Seleccione **Guardar**.
