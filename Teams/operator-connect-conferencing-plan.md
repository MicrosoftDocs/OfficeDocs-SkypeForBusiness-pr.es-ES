---
title: Plan para conferencias Conectar operadores
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
description: Obtenga más información sobre Conectar conferencias de operadores, como requisitos y planificación de la implementación.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257563"
---
# <a name="plan-for-operator-connect-conferencing"></a>Plan para conferencias Conectar operadores

Las audioconferencias de Microsoft ofrecen la capacidad de llamar a una conferencia y llamar desde una conferencia con números de teléfono de red telefónica conmutada (RTC).  Los participantes se Microsoft Teams reuniones con un puente de conferencias de solo audio.

Con las Conectar de conferencias de operadores, las organizaciones pueden usar números de teléfono de un operador de terceros para unirse a Microsoft Teams reuniones. Si el operador actual forma parte del programa Operador de Microsoft Conectar, puede agregar números de teléfono de su operador al puente de audioconferencia y usarlos para unirse a reuniones.

Sin operador Conectar de conferencias, las organizaciones solo pueden usar números de teléfono proporcionados por Microsoft para su puente de audioconferencia.

>[!NOTE]
>En este artículo se hace referencia a un proveedor de números de teléfono que forma parte del programa de Conectar operador de Microsoft como "operador".
>
>Para ver si el operador participa en el programa microsoft Operator Conectar, vea el Microsoft 365 operador Conectar [directorio](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

En este artículo se describen Conectar conferencias de operadores:

- [Ventajas](#benefits)
- [Requisitos de licencias y facturación](#licensing-requirements-and-billing)
- [Información adicional sobre Las audioconferencias de Microsoft](#additional-information-on-microsoft-audio-conferencing)

Para obtener información sobre la configuración de Conectar conferencias, vea Configurar operador [Conectar conferencias.](operator-connect-conferencing-configure.md)

Si algunos usuarios de su organización necesitan realizar llamadas externas a números de teléfono RTC, aún necesita un plan de llamadas. Para obtener información sobre el uso de un operador de terceros para la conectividad RTC externa, vea [Plan para operadores Conectar](operator-connect-plan.md).

## <a name="benefits"></a>Ventajas

Operador Conectar conferencias ofrece las siguientes ventajas:

- **Asignación flexible de números de teléfono entre el operador y Microsoft.** Use números de teléfono tanto de Microsoft como de su operador (solo con una suscripción a Microsoft AudioConferencing Standard) o solo use números de teléfono de su operador (con una licencia de operador Conectar conferencias).

- **Infraestructura administrada por operadores.**   El operador administra los controladores de borde de sesión (SBC) y la interconexión con Microsoft, lo que le ahorra compras y administración de hardware adicionales.

- **Implementación más rápida y sencilla.**   Conéctese rápidamente a su operador y asigne números de teléfono a su puente de audioconferencia desde el Teams administrador.

- **Soporte y confiabilidad mejorados.**   Los operadores proporcionan soporte técnico y contratos de nivel de servicio compartido para mejorar el soporte técnico, y el emparejamiento directo con tecnología de Azure crea una conexión de red uno a uno para mejorar la confiabilidad.

Operador Conectar conferencias podrían ser la solución adecuada para su organización si:

- Desea mantener **los contratos con** su proveedor de números de teléfono existente

- Desea expandir **la cobertura global del** puente de audioconferencia de Microsoft existente

- Desea obtener números **de teléfono para audioconferencias** de un nuevo proveedor de números de teléfono

- **Las audioconferencias de Microsoft no están disponibles en su ubicación geográfica**

- Desea usar un operador para servicios de **audioconferencia** con un modelo de pago por minuto, como usar números gratuitos y realizar llamadas salientes desde reuniones de Teams a números de teléfono en países no incluidos en la suscripción

## <a name="licensing-requirements-and-billing"></a>Requisitos de licencias y facturación

Los usuarios que necesiten números de operador Conectar conferencias para unirse a las reuniones que organizan deben tener asignada una suscripción a Microsoft AudioConferencing Standard o una licencia de conferencias Conectar operador de Microsoft.

### <a name="audio-conferencing-standard-subscription"></a>Suscripción estándar de audioconferencia

Una suscripción a Microsoft AudioConferencing Standard se puede comprar como complemento a una licencia de Microsoft Teams y también se incluye en Microsoft 365 E5 y Office 365 E5 suscripciones.

La suscripción estándar de audioconferencia permite a los suscriptores usar números de teléfono de Microsoft y expandir sus puentes de audioconferencia con números de un operador. Los suscriptores también pueden decidir qué llamadas salientes Teams a las reuniones para enrutar a través de Microsoft y qué llamadas para enrutar a través de un operador.

Para obtener más información, vea [**Configurar operador Conectar conferencias.**](operator-connect-conferencing-configure.md)

### <a name="operator-connect-conferencing-license"></a>Operador Conectar licencia de conferencia

Una licencia de Conectar de conferencias de Microsoft se puede adquirir como complemento a una Microsoft Teams licencia.

La licencia Conectar de conferencias permite a los suscriptores usar números de teléfono de un operador, pero no incluye números de teléfono de Microsoft. Todas las llamadas salientes Teams las reuniones deben enrutarse a través de un operador.

Para obtener más información, vea [**Configurar operador Conectar conferencias.**](operator-connect-conferencing-configure.md)

>[!Note]
>Los participantes de la reunión no necesitan una licencia de suscripción estándar de audioconferencia o una licencia de conferencias de operador Conectar para unirse a una reunión organizada por un usuario con las capacidades de operador Conectar conferencia.

Con operador Conectar conferencias, Microsoft factura su organización según el tipo de licencia de audioconferencia usada por su organización, conferencias de audioconferencia de Microsoft u operador Conectar y el uso de los números de teléfono proporcionados por Microsoft.

El operador factura a su organización el uso de los Conectar de conferencia que proporcionan.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Información adicional sobre Las audioconferencias de Microsoft

Las audioconferencias de Microsoft permiten a los participantes unirse Microsoft Teams reuniones mediante la llamada con un número de teléfono RTC o marcando a un número de teléfono RTC. Para obtener más información sobre las capacidades de Audioconferencia de Microsoft disponibles para su organización, vea [Conferencias](audio-conferencing-in-office-365.md)de audio en Microsoft 365 .
