---
title: Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: b576f2d9e7dbf9cb82484803ca6e93afb4440795
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778000"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server

Decisiones necesarias para planear una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.

Antes de configurar Skype Empresarial para E9-1-1, debe planear la implementación de E9-1-1. Algunas de las preguntas que se deben tener en cuenta son:

 **¿Cuáles son las obligaciones legales y de directiva de su organización con respecto a E9-1-1?**

 Los requisitos legales de E9-1-1 para PBX (denominados Sistemas telefónicos de varias líneas o MLTS, en la parlancia E9-1-1) difieren de un estado a otro. Debe consultar con su equipo legal para comprender las obligaciones que pueden aplicarse a la implementación de Skype Empresarial en sus geografías relevantes.

 **¿Qué áreas dentro de su empresa deben habilitarse para E9-1-1?**

 Puede habilitar E9-1-1 para toda la empresa o para ubicaciones seleccionadas. Por ejemplo, es posible que tenga distintos requisitos E9-1-1 para oficinas en distintos estados o que desee excluir sitios fuera de los Estados Unidos.

 **¿Cómo implementarÁ E9-1-1 en sitios de sucursal?**

 La resistencia de voz es un concepto importante que se debe comprender al implementar E9-1-1 en un sitio de sucursal. Si tiene troncos SIP E-9-1-1 centralizados y se produce una interrupción de WAN, es posible que los clientes que inicien sesión no puedan obtener una ubicación del servicio de información de ubicación o conectarse al proveedor de servicios de emergencia. Skype Empresarial proporciona varias estrategias para controlar la resistencia de voz en las sucursales, como tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o llevar llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, [vea Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).

 **¿Habilitará E9-1-1 para usuarios que trabajen fuera de la red?**

 La adquisición automática de ubicación solo está disponible para clientes ubicados dentro de la red de la organización, por lo que su organización debe decidir si admitirá llamadas E9-1-1 realizadas desde clientes de Skype Empresarial mientras está fuera de la instalación. Por ejemplo, ¿permitirá a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio de cliente? Si un cliente se encuentra fuera de la red empresarial, se puede configurar para solicitar al usuario una ubicación. Sin embargo, dado que estas ubicaciones proporcionadas por el usuario no se pueden validar previamente con la Guía principal de direcciones de calle (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de enrutar la llamada al Punto de respuesta de seguridad pública (PSAP).

> [!NOTE]
> Skype Empresarial clientes de usuarios que se conectan a la red de su organización mediante VPN pueden recoger información interna de direcciones IP, pero como estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan del servicio de información de ubicación.

 **¿Desea proporcionar un enrutamiento de llamadas de emergencia a sitios fuera de LOS ESTADOS UNIDOS?**

 Es posible que desee proporcionar enrutamiento de emergencia a áreas de su empresa que no son atendidas por un proveedor de servicios de emergencia (por ejemplo, ubicaciones internacionales). Para ello, cree un nuevo sitio y, a continuación, asigne directivas de voz a los sitios que hacen referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace RTC local.