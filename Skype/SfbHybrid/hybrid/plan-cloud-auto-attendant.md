---
title: Planeación de un operador automático de la nube
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Información general sobre el uso de un operador automático de la nube con Skype empresarial Server 2019
ms.openlocfilehash: 635d9c6548ba807153876d63ad228f69646e93c8
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207040"
---
# <a name="plan-cloud-auto-attendants"></a>Planeación de operadores automáticos en la nube

El operador automático que se usa con la mensajería unificada de Exchange (Exchange Server 2013 o Exchange Server 2016) ya no está disponible en Exchange Server 2019 ni en Exchange Online. Si la implementación de Skype empresarial Server 2019 se integra con cualquiera de estas versiones de Exchange, deberá usar las características de voz en la nube en línea asociadas con el sistema telefónico. Consulte [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md) para obtener información sobre cómo mover los servicios de mensajería unificada de Exchange hospedados en exchange Server 2013 y 2016 a la nube.

Esto implica intrínsecamente que tendrá una implementación híbrida de Skype empresarial Server 2019 si desea usar características de mensajería unificada como operadores automáticos. Consulte [configurar la conectividad híbrida entre Skype empresarial Server y Office 365](configure-hybrid-connectivity.md) para obtener más información.

Un operador automático es un servicio en la nube que acepta llamadas de cliente y saludos, les proporciona opciones de menú e interactúa con las personas que llaman con voz o con Dialpad para enrutar las llamadas al destino correcto. A cada operador automático se le asigna una **cuenta de recursos** (consulte[configurar cuentas de recursos](configure-onprem-ra.md)) en el sistema de Skype empresarial Server 2019, que se vinculará directamente a un operador automático en el centro de administración de Microsoft Teams. Consulte [¿Qué son los operadores automáticos de la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) para obtener más información sobre qué son los operadores automáticos y qué opciones y características existen para los operadores automáticos.

> [!NOTE]
> Puede asignar varios números de servicio de Microsoft o números híbridos a un operador automático.

Una llamada entrante a un operador automático de la nube puede tomar una de varias rutas, como se muestra aquí:

![Diagrama de operadores automáticos](../../SfBServer2019/media/AA-plan-concept.png)

1. A través de Skype empresarial Server 2019
2. A través de un [controlador de borde de sesión](/MicrosoftTeams/direct-routing-border-controllers.md) y [enrutamiento directo](/MicrosoftTeams/direct-routing-plan.md)
3. A través de un número alojado en línea en Office 365.

Consulte también:

- [Configurar un operador automático de la nube](/microsoftteams/create-a-phone-system-auto-attendant)
- [Contestar y enrutar automáticamente las llamadas entrantes](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requisitos

En los siguientes requisitos se da por sentado que ya ha implementado Skype empresarial Server 2019 en una topología compatible.  Sus requisitos dependen de su escenario:

- Si ya usa la mensajería unificada de Exchange en línea o local y actualiza a Skype empresarial 2019, deberá capturar la estructura de los operadores automáticos y volver a crearla en la nube con operadores automáticos de la nube. Para obtener más información, vea [mover un operador automático de mensajería unificada de Exchange o una cola de llamadas al sistema telefónico](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).

- Para una nueva configuración de operadores automáticos de la nube, siga los pasos descritos en [Configure Resource accounts](configure-onprem-ra.md).

Además de los requisitos anteriores, deben configurarse los siguientes requisitos para conectarse al servicio del operador automático de la nube de Microsoft:

- Conectividad híbrida. Si ya ha implementado Skype empresarial Server y desea habilitar el operador automático de la nube para los usuarios locales, debe asegurarse de que tiene una conectividad híbrida configurada entre su entorno local y el entorno en línea. A veces, se denomina configuración de dominio dividido.

   Para obtener más información, consulte [planear la conectividad híbrida entre Skype empresarial Server y office 365](plan-hybrid-connectivity.md) y [configurar la conectividad híbrida entre Skype empresarial server y Office 365](configure-hybrid-connectivity.md).

- Si está asignando un número de teléfono al operador automático, necesitará una licencia de [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) .
- Cree una [cuenta de recurso](/MicrosoftTeams/manage-resource-accounts.md) en línea o una [cuenta de recursos](configure-onprem-ra.md)local para cada operador automático y asigne números de teléfono y licencias. 

## <a name="migration-and-interoperability"></a>Migración e interoperabilidad

Si tiene previsto implementar Skype empresarial Server 2019 o Exchange Server 2019, debe planear la migración detenidamente para garantizar la compatibilidad continua con los operadores automáticos. Tenga en cuenta lo siguiente:

- Exchange Server 2019 ya no proporciona funcionalidad de mensajería unificada de Exchange
- La mensajería unificada de Exchange está en modo de retiro
- Skype empresarial Server 2019 ya no se integra con la mensajería unificada de Exchange Online

Los operadores automáticos de la nube se pueden configurar con Skype empresarial Server 2019, 2015 y 2013.

Microsoft recomienda las siguientes rutas de migración:

- Si va a actualizar a Skype empresarial Server 2019, puede usar la mensajería unificada de Exchange en Exchange Server 2013 o 2016, pero debe actualizar a operador automático de la nube si usa Exchange Server 2019.

- Si va a actualizar a Exchange Server 2019 y está usando versiones anteriores de la mensajería UNIFICAda de Exchange Server para los mensajes de voz de Skype empresarial Server, Microsoft le recomienda que actualice a Skype empresarial Server 2019 antes de la actualización del buzón de correo.  De lo contrario, se perderán las funciones de mensajería de voz.

Para obtener más información acerca de la planeación de la migración, vea [Plan for Skype for Business Server and Exchange Server Migration](plan-um-migration.md).

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Migrar un sistema de operador automático de mensajería unificada de Exchange implementado previamente

Actualmente no se admite la migración automatizada a la nube de un sistema de operador automático de mensajería unificada creado en Exchange 2013 o 2016. Para volver a crear manualmente un sistema de operador automático, debe:

1. Use los comandos de PowerShell de administración de Exchange para revisar la estructura del antiguo sistema de operadores automáticos, incluidos los operadores automáticos anidados y las colas de llamadas.  
2. Cree copias de secuencias de comandos de texto a voz o mensajes grabados asociados con cada nodo de operador automático de mensajería unificada.
3. Cree extremos locales para cada nodo de operador automático, incluida la asignación de licencias y números de teléfono de prueba a los objetos. Tenga en cuenta que ahora tiene la posibilidad de asignar licencias de números de teléfono locales que usan los servicios en línea como sistema telefónico.
4. Implemente un nuevo servicio de operador automático de la nube con Skype empresarial online y el sistema telefónico. Vea [Configure Resource accounts](configure-onprem-ra.md) para obtener detalles de implementación. Al hacerlo, cargue los scripts de texto a voz o los mensajes grabados asociados con cada nodo de operador automático de mensajería unificada.
5. Pruebe la funcionalidad del operador automático de la nube.
6. Reasigne el número de teléfono asignado al operador automático de mensajería unificada de Exchange anterior al operador automático de la nube principal recién creado.

Vea [mover un operador automático de mensajería unificada de Exchange o una cola de llamadas a Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) para obtener más información sobre estos pasos.

## <a name="additional-planning-resources"></a>Recursos de planeación adicionales

En el tutorial titulado [Small Business example-set up an operador automático](/microsoftteams/tutorial-org-aa) se recorre el proceso de recopilar información sobre las necesidades de los usuarios, planear una estructura de operadores y usuarios automáticos (y posiblemente colas de llamadas), escribir los mensajes del menú y implementación del plan en el centro de administración de Teams. Revise el tutorial y use los ejercicios que hay para crear el plan.

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guíe a los clientes con eficacia, continúe con la [configuración de las cuentas de recursos](configure-onprem-ra.md).

> [!CAUTION]
> Como se mencionó en [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), no se recomienda mover los operadores automáticos de mensajería unificada de Exchange creados en el servidor 2015 a los servidores que ejecutan el servidor 2019. Por el momento, tendría que mantenerlas en un grupo de servidores de Skype empresarial Server 2015 que se ejecuten en el modo de coexistencia.

## <a name="see-also"></a>Vea también

[Planeación de la migración de Skype empresarial Server y Exchange Server](plan-um-migration.md)

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos de la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático de la nube](/microsoftteams/create-a-phone-system-auto-attendant)

Mensajería unificada [de Exchange: responder y enrutar automáticamente las llamadas entrantes](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Planeación de la conectividad híbrida entre Skype empresarial Server y Office 365](plan-hybrid-connectivity.md)

[Configurar la conectividad híbrida entre Skype empresarial Server y Office 365](configure-hybrid-connectivity.md)

[KB4480742: las llamadas al acceso de suscriptor o al operador automático producen errores con Fast busy y el error "500 de servidor interno" después de mover objetos de contacto a Skype empresarial Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
