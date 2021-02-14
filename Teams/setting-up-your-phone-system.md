---
title: Configurar el Sistema telefónico en su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Guía paso a paso que detalla cómo configurar un sistema telefónico (PBX en la nube) para su organización en Microsoft 365 u Office 365.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701218"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar Sistema telefónico en su organización

La siguiente es una guía paso a paso para configurar Sistema telefónico en Microsoft 365 u Office 365. Los vínculos a información detallada adicional están disponibles al final de cada paso.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Paso 1: asegurarse de que el sistema telefónico está disponible en su país o región

1.    En primer lugar vaya a [Disponibilidad de país y región para los planes de audioconferencia y llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) y seleccione su país o región en la lista de la parte superior de la página. 
2.    Bajo **Sistema telefónico**, revise la lista de las características y los detalles. 
3.    Si el sistema telefónico está disponible, vaya al paso 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Paso 2: comprar y asignar licencias del sistema telefónico y del plan de llamadas

Para asignar una licencia de Sistema telefónico y Plan de llamadas a un solo usuario, los pasos son los mismos que para asignar una licencia de Microsoft 365 u Office 365.  También puede asignar licencias a varios usuarios de forma masiva. Para obtener más información, [consulte Asignar licencias de complementos de Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

Si los planes de llamadas no están disponibles para su país o región, considere la posibilidad de usar enrutamiento directo para conectar su infraestructura de telefonía local a Sistema telefónico.  Para obtener más información, vea [Enrutamiento directo de Sistema telefónico.](direct-routing-landing-page.md)

## <a name="step-3-get-phone-numbers-for-your-users"></a>Paso 3: Obtener números de teléfono para los usuarios

[] Para poder configurar los usuarios de su organización para que puedan recibir y realizar llamadas telefónicas, debe usar el Centro de administración de Skype Empresarial para obtener los números de teléfono.

Puede obtener números de tres maneras para los usuarios:
- Obtenga nuevos números con el Centro de administración de Teams.
- Obtenga números nuevos que no están disponibles en el Centro de administración de Teams.
- Transferir o transferir los números existentes de su proveedor de servicios u operador telefónico actual a Microsoft 365 u Office 365.

Debe usar la **página Agregar números** para ver, buscar, adquirir y reservar dichos números. Puede buscar por País o región, Estado y Ciudad y, a continuación, escribir la cantidad de números de teléfono que necesitará para los usuarios.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Obtener nuevos números de teléfono de usuario con el Centro de administración de Teams

1. Inicie sesión en Microsoft 365 con su cuenta de trabajo o escuela.

2. Vaya al Centro **de administración de Teams.**
    
3. En el panel de navegación izquierdo, vaya **a Números de** teléfono de voz, haga clic en Agregar y siga las  >  indicaciones. 
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obtener nuevos números que no están disponibles en el Centro de administración de Teams
  
En ocasiones (según el país o región) no podrá obtener los nuevos números mediante el Centro de administración de Teams. En este caso, tendrá que descargar un formulario y volver a enviárnoslo. Para obtener información sobre cómo solicitar nuevos números de usuario, vea [Administrar números de teléfono para su organización.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Port or transfer phone numbers from your service provider or phone carrier
  
- Si necesita 999 o menos números de teléfono para sus usuarios, puede usar el asistente para nueva portabilidad de número **local** en el Centro de administración de Teams. Siga los pasos que se indican en [Transferir números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) para transferir sus números de teléfono.
    
- Si necesita realizar una portabilidad superior a [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 999 números de teléfono, vea Administrar números de teléfono para que su organización envíe una solicitud de servicio o una solicitud de portabilidad. 

Para obtener información detallada acerca de la obtención de nuevos números de teléfono o sobre transferir los números existentes, consulte [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 4: obtener los números de teléfono de servicio (audioconferencia, colas de llamadas, operadores automáticos)

Además de obtener números de teléfono para los usuarios de Microsoft 365 u Office 365, puede buscar y adquirir números de teléfono de pago o gratuitos para servicios como audioconferencia (para puentes de conferencia), operadores automáticos y colas de llamadas. Los números de teléfono de servicio tienen una mayor capacidad de llamadas simultáneas que los números de teléfono de usuario o suscriptor. Por ejemplo, un número de servicio puede gestionar cientos de llamadas simultáneamente, mientras que el número de teléfono de un usuario solo puede gestionar unas pocas llamadas simultáneamente.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Obtener nuevos números de servicio con el Centro de administración de Teams


1. Inicie sesión con su cuenta del trabajo o de la escuela.

2. Vaya al Centro **de administración de Teams.**

3. En el panel de navegación izquierdo, vaya a **Números de** teléfono de voz Agregar nuevo número y, a continuación, haga clic  >    >  en **Nuevos números de servicio.**

    > [!IMPORTANT]
    > Para que vea  la opción Voz en el panel de navegación izquierdo del Centro de administración  de Teams, primero debe comprar al menos una licencia **de Enterprise E5,** una licencia del complemento Sistema telefónico o una licencia del complemento **Audioconferencia.**

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obtener nuevos números que no están disponibles en el Centro de administración de Teams
  
En ocasiones (según el país o región) no podrá obtener los nuevos números mediante el Centro de administración de Teams. En este caso, tendrá que descargar un formulario y volver a enviárnoslo. Para obtener información sobre cómo solicitar números nuevos, consulte [Administrar números de teléfono para su organización.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

### <a name="port-or-transfer-existing-service-numbers"></a>Portabilidad o trasferencia de números de servicio existentes

Si quiere transferir números de servicio de su proveedor de servicios u operador de telefonía actual, debe enviar manualmente una solicitud de portabilidad a Microsoft. Debe enviar solicitudes de portabilidad separadas para cada tipo de número de servicio (gratuito o de pago) que va a transferir mediante una Carta de autorización (LOA). En la Carta de autorización (LOA), debe seleccionar el tipo de número de servicio correcto. Al ponerse en contacto con el soporte técnico de Microsoft, especifique que va *a* transferir un número de servicio (y no un número de usuario o suscriptor), o la capacidad de llamadas simultáneas puede no ser suficiente para gestionar volúmenes de llamadas. Si desea transferir los números de teléfono o hacer otras cosas con ellos, consulte [Administrar los números de teléfono de su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Paso 5: si desea configurar planes de llamadas

Si ha sido siguiendo los pasos anteriores, ya habrá comprado y asignado el sistema telefónico, las licencias y un plan de llamadas (paso 2), y adquirido números de teléfono para los usuarios (paso 3), por lo que su plan de llamadas ya estará parcialmente configurado. Para completar los procedimientos para configurar el plan de llamadas, consulte [Configurar planes de llamadas.](set-up-calling-plans.md)


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Paso 6: si desea configurar la audioconferencia

En algunas ocasiones, en su organización se necesitará un teléfono para llamar a una reunión. Microsoft Teams incluye la característica de Audioconferencia para este tipo de situaciones. Las personas pueden llamar a las reuniones de Teams con un teléfono, en lugar de usar la aplicación Teams en un dispositivo móvil o PC.
Para obtener información sobre cómo configurar Audioconferencia, consulte Configurar [Audioconferencia para Teams.](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Paso 7: Si quiere configurar una cola de llamadas en la nube

Las colas de llamadas en la nube incluyen saludos que se usan cuando alguien llama a un número de teléfono de su organización, la capacidad para poner automáticamente las llamadas en espera y la capacidad de buscar el siguiente agente de llamada disponible para que se ocupará de la llamada mientras las personas que realiza la llamada escuchan música en espera. Puede crear una o varias colas de llamadas para su organización.

Para obtener más información sobre las colas de llamadas, vea [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Paso 8: Si desea configurar un operador automático en la nube

Los operadores automáticos permiten a los usuarios que llaman a su organización y naveguen por un sistema de menús para llegar al departamento, la cola de llamadas, la persona o el operador adecuados. Puede crear un operador automático para su organización mediante el Centro de administración de Teams.

Para obtener información sobre cómo configurar un operador automático de la nube, consulte [Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md)


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Paso 9: asignar los números de teléfono de servicio (audioconferencia, colas de llamadas, operadores automáticos)

Una vez que obtenga sus números de servicio mediante el **Paso 4 de arriba**, debe asignarlos a cada tipo de servicio que desee. Por ejemplo, si desea un número de teléfono de servicio dedicado (de pago o gratuito), tendrá que asignar el número al puente de conferencia.

- Para las Audioconferencias, puede asignar un número dedicado a un puente de conferencia si va a los puentes de conferencia de reuniones del centro de administración de Teams y sigue las  >    >   indicaciones.  Para obtener más información, vea Cambiar los números de pago o [gratuitos en su puente de Audioconferencia.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

- Para los operadores automáticos, puede asignar un número dedicado a un operador automático si va a operadores automáticos de voz del Centro de administración de **Teams** y  >    >   sigue las indicaciones.  Para obtener más información, [vea Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md)

- Para las colas de llamadas, puede asignar un número dedicado a una cola de llamadas yendo a las colas de llamadas de voz del centro de administración de **Teams** y  >    >   siguiendo las indicaciones. Para obtener más información, vea [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)

Para ver información detallada sobre cómo obtener nuevos números de servicio y hacer la portabilidad de otros ya existentes, consulte [Obtener números de teléfono de servicio](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Paso 10: Configurar créditos de comunicaciones para su organización

Si desea usar números gratuitos con Microsoft Teams, debe configurar los créditos de comunicaciones. Microsoft recomienda configurar los créditos de comunicaciones para los planes de llamadas (nacionales o internacionales) y los usuarios de audioconferencia que necesiten poder llamar a cualquier destino. Se incluyen muchos países o regiones, pero es posible que algunos destinos no se incluyan en los planes de plan de llamadas o audioconferencias. 

Si no configura la facturación de créditos de comunicaciones y asigna una licencia de Créditos de comunicaciones **a** sus usuarios y se le están a punto los minutos para su organización (según el plan de llamadas o audioconferencia de su país o región), los usuarios no podrán realizar llamadas ni llamar desde reuniones de Audioconferencia. Para obtener más información, incluidas las cantidades de financiación recomendadas, consulta [¿Qué](what-are-communications-credits.md) son los créditos de comunicaciones? y Configurar créditos de [comunicaciones para tu organización.](set-up-communications-credits-for-your-organization.md)
  

## <a name="related-topics"></a>Temas relacionados
[Esto es lo que obtiene con Sistema telefónico en Microsoft 365 u Office 365](here-s-what-you-get-with-phone-system.md)

[Administrar los números de teléfono de la organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](getting-service-phone-numbers.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
