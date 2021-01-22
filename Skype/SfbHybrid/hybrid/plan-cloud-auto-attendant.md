---
title: Planear un operador automático en la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Información general sobre el uso de un operador automático en la nube con Skype Empresarial Server 2019
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918696"
---
# <a name="plan-cloud-auto-attendants"></a>Plan de los operadores automáticos en la nube

El operador automático que se usa con la mensajería unificada de Exchange (Exchange Server 2013 o Exchange Server 2016) ya no está disponible en Exchange Server 2019 o Exchange Online. Si la implementación de Skype Empresarial Server 2019 se integra con cualquiera de estas versiones de Exchange, tendrá que usar las características en línea de Cloud Voice asociadas con el sistema telefónico. Consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.

Esto significa inherentemente que tendrá una implementación híbrida de Skype Empresarial Server 2019 si desea usar características de mensajería unificada como operadores automáticos. Consulte [Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](configure-hybrid-connectivity.md) para obtener más información.

Un operador automático es un servicio en la nube que acepta llamadas de clientes y reproduce saludos, les proporciona opciones de menú e interactúa con las personas que llaman mediante voz o el teclado de marcado para enrutar sus llamadas al destino correcto. A cada operador automático se le asigna una cuenta de recursos *(vea* [Configurar](configure-onprem-ra.md)cuentas de recursos) en el sistema de Skype Empresarial Server 2019 que se vinculará directamente a un operador automático en el Centro de administración de Microsoft Teams. Consulte [¿Qué son los operadores automáticos](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) en la nube? Para obtener más información sobre qué son los operadores automáticos y qué opciones y características existen para los operadores automáticos.

> [!NOTE]
> Puede asignar varios números de servicio de Microsoft, números de enrutamiento directo o números híbridos a un operador automático.

Una llamada entrante a un operador automático de nube puede tomar una de varias rutas, como se muestra aquí:

![Diagrama para operadores automáticos](../../SfBServer2019/media/AA-plan-concept.png)

1. A través de Skype Empresarial Server 2019
2. A través de [un controlador de borde de sesión](/MicrosoftTeams/direct-routing-border-controllers.md) y enrutamiento [directo](/MicrosoftTeams/direct-routing-plan.md)
3. A través de un número conectado en Microsoft 365 u Office 365.

Consulte también:

- [Configurar un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant)
- [Contestar y enrutar automáticamente las llamadas entrantes](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server 2019 implementado en una topología compatible.  Los requisitos dependen de su escenario:

- Si ya usa la mensajería unificada de Exchange en línea o local y actualiza a Skype Empresarial 2019, tendrá que capturar la estructura de los operadores automáticos y volver a crearlos en la nube con operadores automáticos en la nube. Para obtener más información, vea Mover un operador automático de mensajería unificada [de Exchange o una cola de llamadas al Sistema telefónico.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- Para obtener una nueva configuración de operadores automáticos en la nube, siga los pasos descritos en [Configurar cuentas de recursos.](configure-onprem-ra.md)

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio de operador automático de Microsoft Cloud:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar el operador automático en la nube para los usuarios locales, debe asegurarse de que tiene configurada la conectividad híbrida entre los entornos locales y en línea. A veces, esto se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Si asigna un número de teléfono al operador automático, necesitará una licencia de [Office 365 Enterprise E5.](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)
- Cree una cuenta [de recursos en línea](/MicrosoftTeams/manage-resource-accounts.md) o una cuenta de recursos local para cada operador automático y asigne números de teléfono y licencias. [](configure-onprem-ra.md) 

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si tiene previsto implementar Skype Empresarial Server 2019 o Exchange Server 2019, debe planear cuidadosamente la migración para garantizar la compatibilidad continua con los operadores automáticos. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona funcionalidad de mensajería unificada de Exchange
- La mensajería unificada de Exchange está en modo de retirada
- Skype Empresarial Server 2019 ya no se integra con la mensajería unificada de Exchange Online

Los operadores automáticos en la nube se pueden configurar con Skype Empresarial Server 2019, 2015 y 2013.

Microsoft recomienda las siguientes rutas de migración:

- Si va a actualizar a Skype Empresarial Server 2019, puede usar la mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar al operador automático en la nube si usa Exchange Server 2019.

- Si está actualizando Exchange Server Exchange Server 2019 y está usando versiones anteriores de mensajería unificada de Exchange Server para mensajería de voz de Skype Empresarial Server, Microsoft recomienda actualizar a Skype Empresarial Server 2019 antes de la actualización del buzón.  De lo contrario, se perderán las capacidades de mensajería de voz.

Para obtener más información acerca de la planeación de la migración, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migración de un sistema de operador automático de mensajería unificada de Exchange implementado anteriormente

Actualmente no se admite la migración automatizada a la nube de un sistema de operador automático de mensajería unificada creado en Exchange 2013 o 2016. Para volver a crear manualmente un sistema de operador automático, tendrá que:

1. Use los comandos de PowerShell de administración de Exchange para revisar la estructura del antiguo sistema de operador automático, incluidos los operadores automáticos anidados y las colas de llamadas.  
2. Cree copias de scripts de texto a voz o mensajes grabados asociados con cada nodo de operador automático de mensajería unificada.
3. Cree extremos locales para cada nodo de operador automático, incluida la asignación de números de teléfono de prueba y licencias a los objetos. Tenga en cuenta que ahora tiene la capacidad de asignar licencias de números de teléfono locales usadas por servicios en línea como Sistema telefónico.
4. Implementar un nuevo servicio de operador automático en la nube con Microsoft Teams y sistema telefónico. Consulta [Configurar cuentas de recursos para](configure-onprem-ra.md) obtener detalles de implementación. Al hacerlo, cargue los scripts de texto a voz o los mensajes grabados asociados con cada nodo de operador automático de mensajería unificada.
5. Pruebe la funcionalidad del operador automático de nube.
6. Reasignar el número de teléfono asignado al antiguo operador automático de mensajería unificada de Exchange al operador automático principal de nube recién creado.

Consulte Mover un operador automático de mensajería unificada [de Exchange o una cola de llamadas](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) al Sistema telefónico para obtener más información sobre estos pasos.

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guía a los clientes de forma eficaz, continúe con [Configurar cuentas de recursos.](configure-onprem-ra.md)

> [!CAUTION]
> Como se mencionó en [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)no se recomienda mover operadores automáticos de mensajería unificada de Exchange creados en Server 2015 a servidores que ejecutan Server 2019. Por el momento, tendría que mantenerlos en un grupo de Skype Empresarial Server 2015 que se ejecute en modo de coexistencia.

## <a name="see-also"></a>Consulte también

[Planificar la migración de Skype Empresarial Server y Exchange Server](plan-um-migration.md)

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos en la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant)

Mensajería unificada de Exchange: [responder y enrutar automáticamente las llamadas entrantes](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](plan-hybrid-connectivity.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](configure-hybrid-connectivity.md)

[KB4480742: Las llamadas al acceso de suscriptor o al operador automático producirán un error de disponibilidad rápida y "500 servidores internos" después de mover objetos de contacto a Skype Empresarial Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
