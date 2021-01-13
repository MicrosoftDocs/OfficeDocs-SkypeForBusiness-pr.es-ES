---
title: Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813430"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server

Decisiones necesarias para planear una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.

Antes de configurar Skype Empresarial para E9-1-1, debe planear la implementación de E9-1-1. Algunas de las preguntas que se deben tener en cuenta son:

 **¿Cuáles son las obligaciones legales y la directiva de su organización con respecto a E9-1-1?**

 Los requisitos legales de E9-1-1 para PBX (denominados sistemas telefónicos de varias líneas o MLTS, en la parlidad E9-1-1) difieren de un estado a otro. Debe consultar con su equipo legal para comprender las obligaciones que pueden aplicarse a la implementación de Skype Empresarial en sus ubicaciones geográficas relevantes.

 **¿Qué áreas de la empresa deben habilitarse para E9-1-1?**

 Puede habilitar E9-1-1 para toda la empresa o para ubicaciones seleccionadas. Por ejemplo, puede que tenga distintos requisitos de E9-1-1 para las oficinas en diferentes estados o que desee excluir sitios fuera de los Estados Unidos.

 **¿Cómo implementará E9-1-1 en sitios de sucursal?**

 La resistencia de voz es un concepto importante que se debe comprender al implementar E9-1-1 en un sitio de sucursal. Si tiene troncos SIP E-9-1-1 centralizados y se produce una interrupción de la WAN, es posible que los clientes que inician sesión no puedan obtener una ubicación del servicio de información de ubicación o conectarse al proveedor de servicios de emergencia. Skype Empresarial ofrece varias estrategias para controlar la resistencia de voz en las sucursales, entre las que se incluyen: tener redes de datos resistentes, implementar un tronco SIP en cada sucursal o forzar llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, consulte [Planeación Branch-Site resistencia de voz.](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)

 **¿Habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**

 La adquisición automática de la ubicación solo está disponible para los clientes ubicados dentro de la red de la organización, por lo que su organización debe decidir si admitirá las llamadas E9-1-1 realizadas desde clientes de Skype Empresarial fuera de las instalaciones. Por ejemplo, ¿permitirá a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio de cliente? Si un cliente se encuentra fuera de la red de empresa, se puede configurar para solicitar al usuario una ubicación. Sin embargo, dado que estas ubicaciones proporcionadas por el usuario no se pueden validar previamente con la Guía de direcciones principal de la calle (MSAG), el distribuidor del proveedor de servicios de emergencia deberá confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de enrutar la llamada al punto de respuesta de seguridad pública (PSAP).

> [!NOTE]
> Los clientes de Skype Empresarial de los usuarios que se conectan a la red de su organización mediante VPN pueden obtener información de direcciones IP internas, pero como estas direcciones no se pueden usar para identificar la ubicación real del usuario, es esencial que las subredes VPN se excluyan del servicio de información de ubicación.

 **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios fuera de Estados Unidos?**

 Es posible que desee proporcionar enrutamiento de emergencia a áreas de su empresa que no son atendidas por un proveedor de servicios de emergencia (por ejemplo, ubicaciones internacionales). Para ello, cree un nuevo sitio y, a continuación, asigne directivas de voz a los sitios que hacen referencia a un uso de RTC que enruta la llamada a través de la puerta de enlace RTC local.


