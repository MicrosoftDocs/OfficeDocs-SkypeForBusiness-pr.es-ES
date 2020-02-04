---
title: Agregar colocación de servidor front-end 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Para una implementación de Enterprise Edition, puede Collocate el servicio de conferencias A/V, el servidor de mediación o ambos en el grupo de servidores front-end, o puede implementar cada uno como servidores independientes. Para una implementación de servidor Standard Edition, el servicio conferencia A/V siempre se encuentra en la que se encuentra habilitada la Conferencia.
ms.openlocfilehash: 371643491438b7f1711c2a023f1b8a6d7a39525c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685153"
---
# <a name="add-front-end-server-collocations-2010"></a>Agregar colocación de servidor front-end 2010

Para una implementación de Enterprise Edition, puede Collocate el servicio de conferencias A/V, el servidor de mediación o ambos en el grupo de servidores front-end, o puede implementar cada uno como servidores independientes. Para una implementación de servidor Standard Edition, el servicio conferencia A/V siempre se encuentra en la que se encuentra habilitada la Conferencia.

> [!NOTE]
> Se necesita un servicio de conferencia A/V si se seleccionó **Conferencia** en la página **seleccionar características** . Un grupo de aplicaciones para el usuario de Enterprise Edition puede usar un servicio de conferencias A/V o un grupo de conferencias A/V independiente. Si no se seleccionó Conferencia, el servicio de conferencias de Collocate A/V no estará disponible.

Puede Collocate el rol de servidor de mediación en un servidor front end Standard Edition o un grupo de servidores front-end Enterprise Edition. Si implementa conexiones SIP directas en una puerta de enlace de red telefónica pública conmutada (RTC) que admita el equilibrio de carga multimedia y el equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario disponer de un grupo de servidores de mediación independiente. No es necesario un grupo de servidores de mediación independiente porque las puertas de enlace válidas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo. También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:

- El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.

- El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.

Puede usar la herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end en el que desea Collocate el servidor de mediación puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.

En general, no se recomienda el collocation de servidor de conferencia A/V o servidor de mediación si su organización tiene alta disponibilidad y escalabilidad requirementsFor detalles sobre collocating estos roles de servidor en un grupo de servidores front-end en una implementación de Enterprise Edition, consulte [definir y configurar un grupo de servidores front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación. Para obtener más información sobre la característica y los componentes de conferencias A/V, consulte [planificación de conferencias](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación de planificación. Para obtener más información sobre las características y los componentes de telefonía IP, incluido el servidor de mediación, consulte [plan de telefonía IP empresarial en Skype empresarial server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación de planificación.


