---
title: Planeamiento de una cola de llamadas en la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Información general sobre el uso de un operador automático en la nube con Skype Empresarial Server 2019.
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615426"
---
# <a name="plan-cloud-call-queues"></a>Plan de colas de llamadas en la nube

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La cola de llamadas en la nube es un servicio que acepta llamadas de cliente, reproduce un mensaje de saludo y, a continuación, coloca estas llamadas en una cola de espera mientras busca una lista preconfigurada de agentes para responder a estas llamadas. Puede definir el conjunto de agentes en listas de distribución habilitadas para correo o grupos de seguridad. Su organización puede tener una o varias colas de llamadas. Las colas de llamadas se usan normalmente en combinación con operadores automáticos.

Además, las colas de llamadas en la nube pueden proporcionar:

- Música mientras los autores de llamadas esperan en espera
- Configuración personalizada para el tamaño máximo de la cola de llamadas, el tiempo de espera y las opciones de control de llamadas

A cada cola de llamadas se le asigna una **cuenta de recursos** (consulte [Configuración de cuentas de recursos](configure-onprem-ra.md)) en el sistema de Skype Empresarial Server 2019 que se vinculará directamente a una cola de llamadas en el Centro de administración de Microsoft Teams. Consulte [Creación de una cola de llamadas](/MicrosoftTeams/create-a-phone-system-call-queue) en la nube para obtener más detalles sobre qué son las colas de llamadas y qué opciones y características existen para las colas de llamadas.

> [!NOTE]
> Puede asignar varios números de teléfono a una cola de llamadas, pero deben ser números de servicio de Microsoft, números de enrutamiento directo o números híbridos.

## <a name="requirements"></a>Requisitos

Los siguientes requisitos suponen que ya tiene Skype Empresarial Server 2019 implementado en una topología compatible.  Los requisitos dependen de su escenario:

- Para obtener una nueva configuración de las colas de llamadas en la nube, siga los pasos descritos en [Configurar cuentas de recursos](configure-onprem-ra.md). Tendrá que crear cuentas de recursos en línea o en Skype Empresarial Server 2019, y es posible que también tenga que asociar un número de teléfono a la cola de llamadas.

Además de los requisitos anteriores, los requisitos siguientes deben configurarse para conectarse al servicio de cola de llamadas de Microsoft Cloud:

- Conectividad híbrida. Si ya ha implementado Skype Empresarial Server y desea habilitar las colas de llamadas en la nube para los usuarios locales, debe asegurarse de que tiene configurada la conectividad híbrida entre los entornos locales y en línea. Esto a veces se denomina configuración de dominio dividido.

   Para obtener más información, vea [Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](plan-hybrid-connectivity.md) y [Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](configure-hybrid-connectivity.md).

- Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de **cuenta de recursos Teléfono Microsoft Teams** gratuita. Esto proporciona funcionalidades del sistema telefónico a los números de teléfono en el nivel organizativo y le permite crear funcionalidades de operador automático y cola de llamadas.

- Cree una [cuenta de recursos](configure-onprem-ra.md) local para cada cola de llamadas y asigne una licencia y un número de teléfono si es necesario.  

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guíe a los clientes de forma eficaz, vaya a  [Configurar cuentas de recursos](configure-onprem-ra.md).

## <a name="see-also"></a>Consulta también

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos en la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planear la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](plan-hybrid-connectivity.md)

[Configuración de la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 o Office 365](configure-hybrid-connectivity.md)

[Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)