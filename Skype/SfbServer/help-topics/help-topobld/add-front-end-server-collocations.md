---
title: Agregar combinaciones léxicas de servidor Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Para una implementación de Enterprise Edition, el A / servicio de conferencias audiovisuales está ubicado en el grupo de servidores Front-End. También puede colocar el servidor de mediación en el grupo de servidores Front-End, o se puede implementar como un servidor independiente. A / siempre está ubicado en el servicio de conferencias audiovisuales si está habilitada la conferencia.
ms.openlocfilehash: c68ed9e05252d72739f2912f109951d0be723699
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations"></a>Agregar combinaciones léxicas de servidor Front-End
 
Para una implementación de Enterprise Edition, el A / servicio de conferencias audiovisuales está ubicado en el grupo de servidores Front-End. También puede colocar el servidor de mediación en el grupo de servidores Front-End, o se puede implementar como un servidor independiente. A / siempre está ubicado en el servicio de conferencias audiovisuales si está habilitada la conferencia.
  
> [!NOTE]
> Una A / servicio de conferencias audiovisuales es necesario si se ha seleccionado la **conferencia** en la página **Seleccionar características** . Un grupo de servidores Enterprise Edition Front-End utiliza un colocadas A / servicio de conferencias audiovisuales. Si la conferencia no fue seleccionado, la coloca A / servicio de conferencias audiovisuales no estará disponible.
  
Puede colocar la función de servidor de mediación en un Front End un servidor Standard Edition o un grupo de servidores Enterprise Edition Front-End. Si implementa conexiones SIP directo a una puerta de enlace de calificado telefónica pública conmutada (RTC) de red que admite equilibrio de carga de sistema de nombres de dominio (DNS) y la omisión de medios, no es necesario un grupo independiente del servidor de mediación. Un grupo de servidor de mediación de independiente no es necesario porque completos de puertas de enlace no son capaces de DNS equilibrio de carga en un grupo de servidores de mediación y pueden recibir tráfico desde cualquier servidor de mediación en una agrupación. También se recomienda colocar el servidor de mediación en un grupo de servidores Front-End cuando se ha implementado IP-PBX o conectar a telefonía servidor del proveedor de Internet sesión Border Controller (SBC), siempre y cuando se cumple alguna de las condiciones siguientes:
  
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación en la piscina y puede enrutar tráfico de manera uniforme a todos los servidores de mediación en el grupo.
    
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación en la piscina y puede enrutar tráfico de manera uniforme a todos los servidores de mediación en el grupo.
    
Puede utilizar el 2013 de Microsoft Lync Server, herramienta de planeación para evaluar si el grupo de Front-End donde desee colocar el servidor de mediación puede manejar la carga. Si su entorno no cumple estos requisitos, se debe implementar un conjunto de servidor de mediación de independiente.
  
En general, no se recomienda la colocación del servidor de mediación si su organización tiene requerimientos de escalabilidad y alta disponibilidad. Para obtener más información acerca de la colocación de estos roles de servidor en un grupo de Front-End en una implementación Enterprise Edition, vea [definir y configurar un grupo de servidores frontales](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación. Para obtener más información acerca de la característica de conferencias audiovisuales y componentes, vea [Planear la conferencia](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación de planificación. Para obtener más información acerca de las características de Telefonía IP empresarial y componentes, incluido el servidor de mediación, consulte [Plan para Telefonía IP empresarial en Skype para el año 2015 de Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación de planeamiento.
  

