---
title: Plan de Conexión de conferencia con operador
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre Conexión de conferencia con operador, como los requisitos y el planeamiento de la implementación.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881df7d9bd2d2d2bcbf6775654a97066a2927250
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676022"
---
# <a name="plan-for-operator-connect-conferencing"></a>Plan de Conexión de conferencia con operador

Microsoft Audioconferencia proporciona la posibilidad de llamar a una conferencia y llamar desde una conferencia con números de teléfono de la red telefónica conmutada (RTC).  Los participantes se unen a Microsoft Teams reuniones mediante un puente de conferencia de solo audio.

Con Conexión de conferencia con operador capacidades, las organizaciones pueden usar números de teléfono de un operador de terceros para unirse a Microsoft Teams reuniones. Si su operador actual forma parte del programa Microsoft Conexión con operador, puede agregar números de teléfono de su operador a su puente de Audioconferencia y usarlos para unirse a reuniones.

Sin Conexión de conferencia con operador capacidades, las organizaciones solo pueden usar los números de teléfono proporcionados por Microsoft para su puente de audioconferencia.

>[!NOTE]
>En este artículo se hace referencia a un proveedor de números de teléfono que formen parte del programa Microsoft Conexión con operador como "operador".
>
>Para ver si tu operador participa en el programa Microsoft Conexión con operador, consulta el [directorio de Microsoft 365 Conexión con operador](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

En este artículo se describen Conexión de conferencia con operador:

- [Ventajas](#benefits)
- [Requisitos de licencia y facturación](#licensing-requirements-and-billing)
- [Información adicional sobre Microsoft Audioconferencia](#additional-information-on-microsoft-audio-conferencing)

Para obtener información sobre cómo configurar Conexión de conferencia con operador, vea [Configurar Conexión de conferencia con operador](operator-connect-conferencing-configure.md).

Si algunos de los usuarios de su organización necesitan realizar llamadas externas a números de teléfono RTC, aún necesita un plan de llamadas. Para obtener información sobre el uso de un operador de terceros para la conectividad RTC externa, vea [Planear la Conexión con operador](operator-connect-plan.md).

## <a name="benefits"></a>Ventajas

Conexión de conferencia con operador ofrece las siguientes ventajas:

- **Asignación flexible de números de teléfono entre el operador y Microsoft.** Use números de teléfono de Microsoft y de su operador (solo con una suscripción a Microsoft Audioconferencia Standard) o use solo números de teléfono de su operador (solo con una licencia de Conexión de conferencia con operador).

- **Infraestructura administrada por el operador.** Tu operador administra los controladores de borde de sesión (SCS) y la interconexión con Microsoft, lo que te ahorra en compras y administración de hardware adicionales.

- **Implementación más rápida y sencilla.** Conéctese rápidamente a su operador y asigne números de teléfono a su puente de Audioconferencia desde el centro de administración de Teams.

- **Soporte y confiabilidad mejorados.** Los operadores proporcionan soporte técnico y contratos de nivel de servicio compartidos para mejorar el soporte técnico, y el emparejamiento directo con tecnología de Azure crea una conexión de red uno a uno para mejorar la confiabilidad.

Conexión de conferencia con operador puede ser la solución adecuada para su organización si:

- Desea **mantener sus contratos** con su proveedor de número de teléfono existente

- Desea **expandir la cobertura global** de su puente de Audioconferencia de Microsoft existente

- Desea **obtener números de teléfono de origen para Audioconferencia** de un nuevo proveedor de números de teléfono

- **Microsoft Audioconferencia no está disponible en tu ubicación geográfica**

- Desea **usar un operador para Audioconferencia servicios con un modelo de pago por minuto**, como usar números gratuitos y realizar llamadas salientes desde Teams reuniones a números de teléfono en países no incluidos en la suscripción

## <a name="licensing-requirements-and-billing"></a>Requisitos de licencia y facturación

Los usuarios que necesitan números de Conexión de conferencia con operador para unirse a las reuniones que organizan deben tener asignada una suscripción a Microsoft Audioconferencia Standard o una licencia de Microsoft Conexión de conferencia con operador.

### <a name="audio-conferencing-standard-subscription"></a>Audioconferencia suscripción estándar

Se puede comprar una suscripción a Microsoft Audioconferencia Standard como un complemento de una licencia de Microsoft Teams y también se incluye en las suscripciones de Microsoft 365 E5 y Office 365 E5.

La suscripción Audioconferencia Estándar permite a los suscriptores usar números de teléfono de Microsoft y expandir sus puentes de audioconferencia con los números de un operador. Los suscriptores también pueden decidir qué llamadas salientes de Teams reuniones enrutar a través de Microsoft y qué llamadas redirigir a través de un operador.

Para obtener más información, vea [**Configurar Conexión de conferencia con operador**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>Conexión de conferencia con operador licencia

Una licencia de Microsoft Conexión de conferencia con operador se puede adquirir como un complemento de una licencia de Microsoft Teams.

La licencia de Conexión de conferencia con operador permite a los suscriptores usar números de teléfono de un operador, pero no los números de teléfono de Microsoft. Todas las llamadas salientes de Teams reuniones deben enrutarse a través de un operador.

Para obtener más información, vea [**Configurar Conexión de conferencia con operador**](operator-connect-conferencing-configure.md).

>[!Note]
>Los participantes de la reunión no necesitan una licencia de suscripción estándar Audioconferencia o una licencia de Conexión de conferencia con operador para unirse a una reunión organizada por un usuario con capacidades de Conexión de conferencia con operador.

Con Conexión de conferencia con operador, Microsoft factura su organización según el tipo de licencia de Audioconferencia que use su organización, Microsoft Audioconferencia o Conexión de conferencia con operador y el uso de los números de teléfono proporcionados por Microsoft.

El operador factura a la organización por el uso de Conexión de conferencia con operador números que proporcione.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Información adicional sobre Microsoft Audioconferencia

Microsoft Audioconferencia permite a los participantes unirse a Microsoft Teams reuniones marcando con un número de teléfono RTC o llamando a un número de teléfono RTC. Para obtener más información sobre las capacidades de Microsoft Audioconferencia disponibles para su organización, consulte [Audioconferencia en Microsoft 365](audio-conferencing-in-office-365.md).
