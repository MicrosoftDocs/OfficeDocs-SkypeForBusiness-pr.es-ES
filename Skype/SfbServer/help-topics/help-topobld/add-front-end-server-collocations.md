---
title: Agregar colocación de servidor front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: En una implementación de Enterprise Edition, el servicio de conferencia A/V se combina en el grupo de servidores front-end. También puede combinar el servidor de mediación en el grupo de servidores front-end o puede implementarlo como servidor independiente. El servicio de conferencia A/V siempre se combina si la conferencia está habilitada.
ms.openlocfilehash: 015570d42482b0e4f34e6679bab27aa2c40f2f88
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216511"
---
# <a name="add-front-end-server-collocations"></a>Agregar colocación de servidor front-end

En una implementación de Enterprise Edition, el servicio de conferencia A/V se combina en el grupo de servidores front-end. También puede combinar el servidor de mediación en el grupo de servidores front-end o puede implementarlo como servidor independiente. El servicio de conferencia A/V siempre se combina si la conferencia está habilitada.

> [!NOTE]
> Se necesita un servicio de conferencia A/V si **Conferencia** se ha seleccionado en la página **Seleccione las características**. Un grupo de servidores front-end de Enterprise Edition usa un servicio de conferencia A/V combinado. Si no se ha seleccionado Conferencia, no estará disponible el servicio para combinar de servicio de conferencia A/V.

La función de servidor de mediación puede combinarse en un servidor front-end Standard Edition o un grupo de servidores front-end Enterprise Edition. Si implementa conexiones SIP directas para una puerta de enlace de una red telefónica conmutada (RTC) cualificada que admite omisión de medios y equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario un grupo independiente de servidores de mediación. No se necesita un servidor de mediación independiente, ya que las puertas de enlace cualificadas pueden realizar el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo. También le recomendamos que combinar el servidor de mediación en un grupo de servidores front-end cuando implemente IP-PBX o se conecte a un controlador de borde de sesión (SBC) del proveedor del servidor de telefonía por Internet, siempre que se cumpla alguna de las siguientes condiciones:

- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.

Puede usar la herramienta de planeación 2013 de Microsoft Lync Server para evaluar si el grupo de servidores front-end en el que desea combinar el servidor de mediación puede controlar la carga. Si su entorno no cumple con estos requisitos, debe implementar un grupo independiente de servidores de mediación.

En general, no se recomienda combinar un servidor de mediación si la organización tiene requisitos de escalabilidad y alta disponibilidad. Para obtener más información sobre cómo combinar estos roles de servidor en un grupo de servidores front-end en una implementación Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación sobre implementación. Para obtener más información sobre las características y los componentes de conferencia A/V, consulte [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación sobre planeación. Para obtener más información sobre las características y los componentes de Enterprise Voice, incluido el servidor de mediación, consulte [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación referente a la planeación.


