---
title: Agregar colocaciones de servidor Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Para una implementación de Enterprise Edition, el servicio de conferencia A/v se instala también en el grupo de servidores Front-End. También puede instalar el servidor de mediación en el grupo de servidores Front-End, o puede implementar como un servidor independiente. El servicio de conferencia A/v siempre se instala también si se habilita la conferencia.
ms.openlocfilehash: 376a5f7a878f4760a832c998aaae3f5ddd6eee90
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263798"
---
# <a name="add-front-end-server-collocations"></a>Agregar colocaciones de servidor Front-End

Para una implementación de Enterprise Edition, el servicio de conferencia A/v se instala también en el grupo de servidores Front-End. También puede instalar el servidor de mediación en el grupo de servidores Front-End, o puede implementar como un servidor independiente. El servicio de conferencia A/v siempre se instala también si se habilita la conferencia.

> [!NOTE]
> Un servicio de conferencia A/v es necesario si se ha seleccionado **conferencias** en la página **Seleccionar características** . Un grupo de servidores Front-End de Enterprise Edition utiliza un combinados A / servicio de conferencia A/v. Si conferencia no se ha seleccionado el combinar A / servicio de conferencia A/v no estará disponible.

Puede combinar el rol de servidor de mediación en una Standard Edition Front-End o grupo de servidores Front-End de Enterprise Edition. Si implementa conexiones SIP directas a una puerta de enlace de completa telefónica conmutada (RTC) que admite el desvío de medios y el equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario un grupo de servidores de mediación independiente. Un grupo de servidores de mediación independiente no es necesario porque las puertas de enlace completa son capaces de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico desde cualquier servidor de mediación en un grupo de servidores. También se recomienda instalar el servidor de mediación en un grupo de servidores Front-End cuando se han implementado el IP-PBX o conectarse para el controlador de borde de sesión de telefonía Server del proveedor de Internet (SBC), siempre y cuando se cumple alguna de las siguientes condiciones:

- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los servidores de mediación en el grupo de servidores.

- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los servidores de mediación en el grupo de servidores.

Puede usar Microsoft Lync Server 2013, herramienta de planeación para evaluar si el grupo de servidores Front-End donde desea colocar el servidor de mediación puede administrar la carga. Si el entorno no cumple estos requisitos, a continuación, debe implementar un grupo de servidores de mediación independiente.

En general, la combinación de servidor de mediación no se recomienda si su organización tiene requisitos de escalabilidad y alta disponibilidad. Para obtener información detallada acerca de combinar estas funciones de servidor en un grupo de servidores Front-End en una implementación de Enterprise Edition, consulte [definir y configurar un grupo de servidores Front-End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación. Para obtener información detallada acerca de los / característica de conferencia A/v y de los componentes, consulte [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación de planeación. Para obtener información detallada sobre las características de Enterprise Voice y componentes, incluido el servidor de mediación, consulte [Plan para Enterprise Voice en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación de planeación.


