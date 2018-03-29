---
title: Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisiones necesarias para planear una implementación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: f81a2c56642557bf92a965de025aecbdbcadadcd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server-2015"></a>Definir el ámbito de la implementación de E9-1-1 en Skype Empresarial Server 2015
 
Decisiones necesarias para planear una implementación de E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
  
Antes de configurar Skype para empresas para E9-1-1, debe planear la implementación de E9-1-1. Algunas de las cuestiones que necesitas tener en cuenta son:
  
 **¿Su organización política y obligación legal de E9-1-1?**
  
 Los requisitos legales de E9-1-1 para sistemas PBX (llamados sistemas telefónicos de varias líneas o MLTS, en la terminología de E9-1-1) difieren de un estado a otro. Debe consultar a su equipo legal para comprender las obligaciones que podrían aplicarse a la implementación de Skype para el negocio en sus zonas geográficas pertinentes.
    
 **¿Qué áreas de la empresa necesitan habilitarse para E9-1-1?**
  
 Puedes habilitar E9-1-1 para determinadas ubicaciones o para toda la empresa. Por ejemplo, puedes tener distintos requisitos de E9-1-1 para oficinas en diferentes estados o quizás desee excluir sitios fuera de EE. UU. 
    
 **¿Cómo implementará E9-1-1 en las sucursales?**
  
 La resistencia de voz es un concepto que es importante tener en cuenta al implementar E9-1-1 en un sitio de sucursal. Si centralizada de troncos SIP E-9-1-1 y se produce una interrupción de la WAN, los clientes la firma no podrán obtener una ubicación de servicio de información de ubicación o para conectar con el proveedor de servicio de los servicios de emergencia. Skype para empresas proporciona varias estrategias para controlar la resistencia de voz en las sucursales, incluyendo: necesidad de redes de datos adaptable, implementar un troncal SIP en cada sucursal o extraer las llamadas de emergencia a la puerta de enlace local durante las interrupciones. Para obtener más información, vea [Planear resistencia de voz del sitio de la sucursal](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).
    
 **¿Se habilitará E9-1-1 para los usuarios que trabajan fuera de la red?**
  
 Adquisición de ubicación automática sólo está disponible para los clientes ubicados dentro de la red de la organización, por lo que su organización necesita para decidir si admitirá E9-1-1 las llamadas realizadas desde Skype para clientes de negocios mientras fuera de los locales. Por ejemplo, ¿permitirás a los usuarios realizar llamadas de emergencia si trabajan desde casa o desde un sitio del cliente? Si un cliente se encuentra fuera de la red empresarial, puede configurarse para solicitar al usuario una ubicación. Pero como estas ubicaciones proporcionadas por el usuario no pueden validarse previamente con la Guía de calles maestra (MSAG), el distribuidor del proveedor de servicios de emergencia tendrá que confirmar la validez de la ubicación verbalmente con el autor de la llamada antes de redirigir la llamada al punto de respuesta de seguridad pública (PSAP).
    
> [!NOTE]
> Skype para clientes empresariales de los usuarios que se conectan a la red de su organización mediante VPN puede recoger información de dirección IP interna, pero debido a que estas direcciones no puede utilizarse para identificar la ubicación del usuario real, es esencial que se excluyen las subredes VPN desde el servicio de información de ubicación. 
  
 **¿Desea proporcionar el enrutamiento de llamadas de emergencia a sitios de fuera de Estados Unidos?**
  
 Puede que quieras proporcionar el enrutamiento de emergencia en áreas de la compañía donde no sirve el proveedor de servicios de emergencia (por ejemplo, en ubicaciones internacionales). Para ello, crea un sitio y luego asigna directivas de voz a los sitios que hagan referencia a un uso de RTC que redirige la llamada a través de la puerta de enlace RTC local.
    

