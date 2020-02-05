---
title: Planeación de una cola de llamadas en la nube
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Información general sobre el uso de un operador automático de la nube con Skype empresarial Server 2019.
ms.openlocfilehash: 24a0bba82ef38288f5c96cc7c51ce1bfb88c8f05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735230"
---
# <a name="plan-cloud-call-queues"></a>Planear colas de llamadas en la nube

La cola de llamadas en la nube es un servicio que acepta llamadas de clientes, reproduce un mensaje de saludo y, a continuación, coloca estas llamadas en una cola de espera mientras busca una lista preconfigurada de agentes para responder a estas llamadas. Puede definir el conjunto de agentes en listas de distribución o grupos de seguridad habilitados para correo. Su organización puede tener una o varias colas de llamadas. Las colas de llamadas se suelen usar en combinación con los operadores automáticos.

Además, las colas de llamadas en la nube pueden proporcionar:

- Música mientras los autores de llamadas esperan en espera
- Configuración personalizada para el tamaño máximo de la cola de llamadas, el tiempo de espera y las opciones de administración de llamadas

Cada cola de llamadas tiene asignada una **cuenta de recursos** (consulte [configurar cuentas de recursos](configure-onprem-ra.md)) en el sistema de Skype empresarial Server 2019, que se vinculará directamente a una cola de llamadas en el centro de administración de Microsoft Teams. Consulte [crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue) para obtener más información sobre qué son las colas de llamadas y qué opciones y características existen para las colas de llamadas.

> [!NOTE]
> Puede asignar varios números de teléfono a una cola de llamadas, pero deben ser números de servicio de Microsoft o números híbridos.

## <a name="requirements"></a>Requisitos

En los siguientes requisitos se da por sentado que ya ha implementado Skype empresarial Server 2019 en una topología compatible.  Sus requisitos dependen de su escenario:

- Para una nueva configuración de colas de llamadas en la nube, siga los pasos descritos en [Configure Resource accounts](configure-onprem-ra.md). Tendrá que crear cuentas de recursos en línea o en Skype empresarial Server 2019, y es posible que también deba asociar un número de teléfono con la cola de llamadas.

Además de los requisitos anteriores, deben configurarse los siguientes requisitos para conectarse al servicio cola de llamadas en la nube de Microsoft:

- Conectividad híbrida. Si ya ha implementado Skype empresarial Server y desea habilitar las colas de llamadas en la nube para los usuarios locales, debe asegurarse de que tiene una conectividad híbrida configurada entre su entorno local y el entorno en línea. A veces, se denomina configuración de dominio dividido.

   Para obtener más información, consulte [planear la conectividad híbrida entre Skype empresarial Server y office 365](plan-hybrid-connectivity.md) y [configurar la conectividad híbrida entre Skype empresarial server y Office 365](configure-hybrid-connectivity.md).

- Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual de sistema telefónico de sistema gratuito. Esto proporciona funciones del sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y operador automático.

- Cree una [cuenta de recursos](configure-onprem-ra.md) local para cada cola de llamadas y asigne una licencia y un número de teléfono si es necesario.  

## <a name="additional-planning-resources"></a>Recursos de planeación adicionales

En el tutorial titulado [Small Business example-set up an operador automático](/microsoftteams/tutorial-org-aa) se recorre el proceso de recopilar información sobre las necesidades de los usuarios, planear una estructura de operadores automáticos y usuarios (y, posiblemente, colas de llamadas), escribir los mensajes del menú e implementar el plan en el centro de administración en línea. Revise el tutorial y use los ejercicios en los que se crea el plan.

Cuando tenga una estructura sólida que satisfaga sus necesidades y un script que guíe a los clientes con eficacia, continúe con la [configuración de las cuentas de recursos](configure-onprem-ra.md).

## <a name="see-also"></a>Vea también

[Configurar cuentas de recursos](configure-onprem-ra.md)

[Habilitar la grabación de mensajes personalizados con la interfaz de usuario de teléfono](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[¿Qué son los operadores automáticos de la nube?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Configurar un operador automático de la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[Planeación de la conectividad híbrida entre Skype empresarial Server y Office 365](plan-hybrid-connectivity.md)

[Configurar la conectividad híbrida entre Skype empresarial Server y Office 365](configure-hybrid-connectivity.md)

[Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)
