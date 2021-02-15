---
title: Planear una cola de llamadas en la nube
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
description: Información general sobre el uso de un operador automático en la nube con Skype Empresarial Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918746"
---
# <a name="plan-cloud-call-queues"></a>Plan de colas de llamadas en la nube

La cola de llamadas en la nube es un servicio que acepta llamadas de clientes, reproduce un mensaje de saludo y, a continuación, las coloca en una cola de espera mientras busca en una lista preconfigurado de agentes para responder a estas llamadas. Puede definir el conjunto de agentes en listas de distribución habilitadas para correo o grupos de seguridad. Su organización puede tener una o varias colas de llamadas. Las colas de llamadas se usan normalmente en combinación con operadores automáticos.

Además, las colas de llamadas en la nube pueden proporcionar:

- Música mientras las personas que llaman están en espera
- Configuración personalizada para el tamaño máximo de la cola de llamadas, el tiempo de espera y las opciones de administración de llamadas

A cada cola de llamadas se le asigna una cuenta de recursos **(vea** [Configurar](configure-onprem-ra.md)cuentas de recursos) en el sistema de Skype Empresarial Server 2019 que se vinculará directamente a una cola de llamadas en el Centro de administración de Microsoft Teams. Consulte [Crear una cola de llamadas en](/MicrosoftTeams/create-a-phone-system-call-queue) la nube para obtener más información sobre qué son las colas de llamadas y qué opciones y características existen para las colas de llamadas.

> [!NOTE]
> Puede asignar varios números de teléfono a una cola de llamadas, pero deben ser números de servicio de Microsoft, números de enrutamiento directo o números híbridos.

## <a name="requirements"></a>Requirements

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server 2019 implementado en una topología compatible.  Los requisitos dependen de su escenario:

- Para obtener una nueva configuración de colas de llamadas en la nube, siga los pasos descritos en [Configurar cuentas de recursos.](configure-onprem-ra.md) Tendrá que crear cuentas de recursos en línea o en Skype Empresarial Server 2019, y es posible que también necesite asociar un número de teléfono con la cola de llamadas.

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio de cola de llamadas de Microsoft Cloud:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar colas de llamadas en la nube para los usuarios locales, debe asegurarse de que tiene configurada la conectividad híbrida entre los entornos locales y en línea. A veces, esto se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).

- Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia gratuita de usuario virtual del sistema telefónico. Esto proporciona funcionalidades de Sistema telefónico a los números de teléfono en el nivel de la organización y le permite crear funciones de operador automático y cola de llamadas.

- Cree una cuenta de recursos local [para](configure-onprem-ra.md) cada cola de llamadas y asigne una licencia y un número de teléfono si es necesario.  

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guía a los clientes de forma eficaz, continúe con [Configurar cuentas de recursos.](configure-onprem-ra.md)

## <a name="see-also"></a>Vea también

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos en la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](plan-hybrid-connectivity.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](configure-hybrid-connectivity.md)

[Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
