---
title: Planear un operador automático de nube
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
description: Información general sobre cómo usar un operador automático de nube Skype Empresarial Server 2019
ms.openlocfilehash: 61ffefab04dc70167d768332132217ebd6564e31
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509801"
---
# <a name="plan-cloud-auto-attendants"></a>Plan de los operadores automáticos en la nube

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

El operador automático usado con la mensajería unificada de Exchange (Exchange Server 2013 o Exchange Server 2016) ya no está disponible en Exchange Server 2019 o Exchange Online. Si la implementación de Skype Empresarial Server 2019 se integra con cualquiera de estas versiones de Exchange, deberá usar las características de Cloud Voice en línea asociadas con Sistema telefónico. Consulte [Plan for Skype Empresarial Server and Exchange Server migration](plan-um-migration.md) para obtener información acerca de cómo mover Exchange servicios de mensajería unificada en Exchange server 2013 y 2016 a la nube.

Esto significa inherentemente que tendrá una implementación híbrida de Skype Empresarial Server 2019 si desea usar características de mensajería unificada como operadores automáticos. Consulte [Configure hybrid connectivity between Skype Empresarial Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md) para obtener más información.

Un operador automático es un servicio en la nube que acepta llamadas de clientes y reproduce saludos, les proporciona opciones de menú e interactúa con los autores de llamadas mediante voz o el panel de marcado para enrutar sus llamadas al destino correcto. A cada operador automático se le asigna una cuenta de recurso *(consulte* [Configurar](configure-onprem-ra.md)cuentas de recursos ) en el sistema de Skype Empresarial Server 2019 que se vinculará directamente a un operador automático en el centro de administración de Microsoft Teams. Consulte [¿Qué son los operadores automáticos](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) en la nube? para obtener más información sobre qué son los operadores automáticos y qué opciones y características existen para los operadores automáticos.

> [!NOTE]
> Puede asignar varios números de servicio de Microsoft, números de enrutamiento directo o números híbridos a un operador automático.

Una llamada entrante a un operador automático de nube puede tomar una de varias rutas de acceso, como se muestra aquí:

![Diagrama para operadores automáticos](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype Empresarial Server 2019
2. A través [de un controlador de borde de sesión](/MicrosoftTeams/direct-routing-border-controllers.md) y enrutamiento [directo](/MicrosoftTeams/direct-routing-plan.md)
3. A través de un número en línea en Microsoft 365 o Office 365.

Consulte también:

- [Configurar un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant)
- [Contestar y enrutar automáticamente las llamadas entrantes](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya Skype Empresarial Server 2019 implementado en una topología compatible.  Los requisitos dependen del escenario:

- Si ya está usando una mensajería unificada en línea o local y actualiza Skype Empresarial Skype Empresarial 2019, deberá capturar la estructura de los operadores automáticos y volver Exchange a crearlos en la nube con operadores automáticos de nube. Para obtener más información, vea [Moving an Exchange UM auto attendant or call queue to Sistema telefónico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Para una nueva configuración de operadores automáticos en la nube, siga los pasos descritos en  [Configurar cuentas de recursos](configure-onprem-ra.md).

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio de operador automático de Microsoft Cloud:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar el operador automático en la nube para los usuarios locales, debe asegurarse de que tiene la conectividad híbrida configurada entre los entornos locales y en línea. A veces se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype Empresarial Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) y Configure hybrid connectivity between Skype Empresarial Server and Microsoft 365 or [Office 365](configure-hybrid-connectivity.md).

- Si va a asignar un número de teléfono al operador automático, necesitará una licencia [Office 365 Enterprise E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Cree una cuenta [de recurso en línea](/MicrosoftTeams/manage-resource-accounts.md) o una cuenta de recursos local para cada operador automático y asigne números de teléfono y licencias. [](configure-onprem-ra.md) 

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si tiene previsto implementar Skype Empresarial Server 2019 o Exchange Server 2019, debe planear cuidadosamente la migración para garantizar la compatibilidad continua con los operadores automáticos. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona Exchange funcionalidad de mensajería unificada
- Exchange La mensajería unificada está en modo de retiro
- Skype Empresarial Server 2019 ya no se integra con Exchange Online mensajería unificada

Los operadores automáticos en la nube se pueden configurar Skype Empresarial Server 2019, 2015 y 2013.

Microsoft recomienda las siguientes rutas de migración:

- Si va Exchange a actualizar Skype Empresarial Server Skype Empresarial Server 2019, puede usar una mensajería unificada en Exchange Server 2013 o 2016, pero debe actualizar al operador automático de nube si usa Exchange Server 2019.

- Si actualiza Exchange Server Exchange Server 2019 y usa versiones anteriores de mensajería unificada de Exchange Server para mensajería de voz Skype Empresarial Server, Microsoft recomienda actualizar Skype Empresarial Server Skype Empresarial Server 2019 antes de la actualización del buzón.  De lo contrario, se perderán las capacidades de mensajería de voz.

Para obtener más información acerca de la planeación de la migración, [vea Plan for Skype Empresarial Server and Exchange Server migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrar un sistema de operador automático de mensajería unificada Exchange implementado anteriormente

Actualmente no se admite la migración automatizada a la nube de un sistema de operador automático de mensajería unificada creado en Exchange 2013 o 2016. Para volver a crear manualmente un sistema de operador automático, deberá:

1. Use Exchange comandos de PowerShell de administración para revisar la estructura del antiguo sistema de operador automático, incluidos los operadores automáticos anidados y las colas de llamadas.  
2. Cree copias de scripts de texto a voz o mensajes grabados asociados con cada nodo de operador automático de mensajería unificada.
3. Cree puntos de conexión locales para cada nodo de operador automático, incluida la asignación de números de teléfono de prueba y licencias a los objetos. Tenga en cuenta que ahora tiene la capacidad de asignar licencias de números de teléfono locales usadas por servicios en línea como Sistema telefónico.
4. Implemente un nuevo servicio de operador automático en la nube con Microsoft Teams y Sistema telefónico. Consulte [Configurar cuentas de recursos para](configure-onprem-ra.md) obtener detalles de implementación. Al hacerlo, cargue los scripts de texto a voz o los mensajes grabados asociados con cada nodo de operador automático de mensajería unificada.
5. Pruebe la funcionalidad del operador automático de nube.
6. Reasigna el número de teléfono asignado al operador Exchange automático de mensajería unificada al operador automático de nube principal recién creado.

Consulte [Moving an Exchange UM auto attendant or call queue to Sistema telefónico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) para obtener más información sobre estos pasos.

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guía a los clientes de forma eficiente, vaya a [Configurar cuentas de recursos](configure-onprem-ra.md).

> [!CAUTION]
> Como se mencionó en [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)no se recomienda mover Exchange operadores automáticos de mensajería unificada creados en server 2015 a servidores que ejecutan Server 2019. De momento, tendrías que mantenerlos en un grupo de servidores Skype Empresarial Server 2015 en modo de coexistencia.

## <a name="see-also"></a>Consulta también

[Planificar la migración de Skype Empresarial Server y Exchange Server](plan-um-migration.md)

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos en la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange MENSAJERÍA UNIFICADA: [responder y enrutar automáticamente las llamadas entrantes](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](plan-hybrid-connectivity.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[KB4480742: Las llamadas al acceso de suscriptor o al operador automático fallan con un error de disponibilidad rápida y "500 servidores internos" después de mover objetos de contacto a Skype Empresarial Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)