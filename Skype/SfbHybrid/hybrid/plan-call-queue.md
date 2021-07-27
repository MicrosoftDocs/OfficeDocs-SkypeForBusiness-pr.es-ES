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
description: Información general sobre cómo usar un operador automático de nube Skype Empresarial Server 2019.
ms.openlocfilehash: 79682e7079519c2c9532aecdd79a43a6d2e8b30b
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509811"
---
# <a name="plan-cloud-call-queues"></a>Plan de colas de llamadas en la nube

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La cola de llamadas en la nube es un servicio que acepta llamadas de clientes, reproduce un mensaje de saludo y, a continuación, coloca estas llamadas en una cola de espera mientras se busca en una lista predefinida de agentes para responder a estas llamadas. Puede definir el conjunto de agentes en listas de distribución habilitadas para correo o grupos de seguridad. Su organización puede tener una o varias colas de llamadas. Las colas de llamadas se usan normalmente en combinación con operadores automáticos.

Además, las colas de llamadas en la nube pueden proporcionar:

- Música mientras los autores de llamadas están esperando en espera
- Configuración personalizada para las opciones de tamaño máximo, tiempo de espera y control de llamadas de la cola de llamadas

A cada cola de llamadas se le asigna una cuenta de recursos **(consulte** [Configurar](configure-onprem-ra.md)cuentas de recursos ) en el sistema de Skype Empresarial Server 2019 que se vinculará directamente a una cola de llamadas en el centro de administración de Microsoft Teams. Consulte [Crear una cola de llamadas en](/MicrosoftTeams/create-a-phone-system-call-queue) la nube para obtener más información sobre qué son las colas de llamadas y qué opciones y características existen para las colas de llamadas.

> [!NOTE]
> Puede asignar varios números de teléfono a una cola de llamadas, pero deben ser números de servicio de Microsoft, números de enrutamiento directo o números híbridos.

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya Skype Empresarial Server 2019 implementado en una topología compatible.  Los requisitos dependen del escenario:

- Para una nueva configuración de colas de llamadas en la nube, siga los pasos descritos en [Configurar cuentas de recursos](configure-onprem-ra.md). Deberá crear cuentas de recursos en línea o en Skype Empresarial Server 2019, y es posible que también necesite asociar un número de teléfono con la cola de llamadas.

Además de los requisitos anteriores, los siguientes requisitos deben configurarse para conectarse al servicio de cola de llamadas de Microsoft Cloud:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar colas de llamadas en la nube para los usuarios locales, debe asegurarse de que tiene la conectividad híbrida configurada entre los entornos locales y los entornos en línea. A veces se denomina configuración de dominio dividido.

   Para obtener más información, vea [Plan hybrid connectivity between Skype Empresarial Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) y Configure hybrid connectivity between Skype Empresarial Server and Microsoft 365 or [Office 365](configure-hybrid-connectivity.md).

- Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia gratuita Sistema telefónico usuario virtual. Esto proporciona Sistema telefónico funcionalidades a los números de teléfono en el nivel de la organización y le permite crear funciones de operador automático y cola de llamadas.

- Cree una cuenta de recurso local [para](configure-onprem-ra.md) cada cola de llamadas y asigne una licencia y un número de teléfono si es necesario.  

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guía a los clientes de forma eficiente, vaya a  [Configurar cuentas de recursos](configure-onprem-ra.md).

## <a name="see-also"></a>Consulta también

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos en la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](plan-hybrid-connectivity.md)

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)