---
title: Agregar colocación de servidor front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Para una implementación de Enterprise Edition, el servicio de conferencia A/V se encuentra en el grupo de servidores front-end. También puede Collocate el servidor de mediación en el grupo de servidores front-end o puede implementarlo como servidor independiente. El servicio de conferencia A/V siempre se encuentra en el que se encuentra habilitada la Conferencia.
ms.openlocfilehash: fe9eccaa7a59963b202009eba68aa0fdb9f1a15d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702925"
---
# <a name="add-front-end-server-collocations"></a>Agregar colocación de servidor front-end

Para una implementación de Enterprise Edition, el servicio de conferencia A/V se encuentra en el grupo de servidores front-end. También puede Collocate el servidor de mediación en el grupo de servidores front-end o puede implementarlo como servidor independiente. El servicio de conferencia A/V siempre se encuentra en el que se encuentra habilitada la Conferencia.

> [!NOTE]
> Se necesita un servicio de conferencia A/V si se seleccionó **Conferencia** en la página **seleccionar características** . Un grupo de aplicaciones para el usuario de Enterprise Edition usa un servicio de conferencia A/V de prolado. Si no se seleccionó Conferencia, el servicio de conferencias de Collocate A/V no estará disponible.

Puede Collocate el rol de servidor de mediación en un servidor front end Standard Edition o un grupo de servidores front-end Enterprise Edition. Si implementa conexiones SIP directas en una puerta de enlace de red telefónica pública conmutada (RTC) que admita el equilibrio de carga multimedia y el equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario disponer de un grupo de servidores de mediación independiente. No es necesario un grupo de servidores de mediación independiente porque las puertas de enlace válidas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo. También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:

- El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.

- El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.

Puede usar la herramienta de planeación para evaluar si el grupo de servidores front end en el que desea Collocate el servidor de mediación puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.

En general, no se recomienda collocation del servidor de mediación si su organización tiene requisitos de disponibilidad y escalabilidad elevados. Para obtener más información sobre collocating estos roles de servidor en un grupo de servidores front-end en una implementación de Enterprise Edition, consulte [definir y configurar un grupo de servidores front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación. Para obtener más información sobre la característica y los componentes de conferencias A/V, consulte [planificación de conferencias](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación de planificación. Para obtener más información sobre las características y los componentes de telefonía IP, incluido el servidor de mediación, consulte [planear la telefonía IP empresarial en Skype empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación de planificación.


