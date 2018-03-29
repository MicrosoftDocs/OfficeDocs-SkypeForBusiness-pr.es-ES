---
title: Agregar colocaciones de Front-End Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Para una implementación de Enterprise Edition, puede colocar A la / servicio de conferencias audiovisuales, el servidor de mediación o ambos en el grupo de servidores Front-End, o se pueden implementar como servidores independientes. Para una implementación de servidor Standard Edition, el A / siempre está ubicado en el servicio de conferencias audiovisuales si está habilitada la conferencia.
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations-2010"></a>Agregar colocaciones de Front-End Server 2010
 
Para una implementación de Enterprise Edition, puede colocar A la / servicio de conferencias audiovisuales, el servidor de mediación o ambos en el grupo de servidores Front-End, o se pueden implementar como servidores independientes. Para una implementación de servidor Standard Edition, el A / siempre está ubicado en el servicio de conferencias audiovisuales si está habilitada la conferencia.
  
> [!NOTE]
> Una A / servicio de conferencias audiovisuales es necesario si se ha seleccionado la **conferencia** en la página **Seleccionar características** . Un grupo de servidores Front-End de Enterprise Edition puede utilizar un colocadas A / servicio de conferencias audiovisuales o una independiente o grupo de conferencias V. Si la conferencia no fue seleccionado, la coloca A / servicio de conferencias audiovisuales no estará disponible.
  
Puede colocar la función de servidor de mediación en un Front End un servidor Standard Edition o un grupo de servidores Enterprise Edition Front-End. Si implementa conexiones SIP directo a una puerta de enlace de calificado telefónica pública conmutada (RTC) de red que admite equilibrio de carga de sistema de nombres de dominio (DNS) y la omisión de medios, no es necesario un grupo independiente del servidor de mediación. Un grupo de servidor de mediación de independiente no es necesario porque completos de puertas de enlace no son capaces de DNS equilibrio de carga en un grupo de servidores de mediación y pueden recibir tráfico desde cualquier servidor de mediación en una agrupación. También se recomienda colocar el servidor de mediación en un grupo de servidores Front-End cuando se ha implementado IP-PBX o conectar a telefonía servidor del proveedor de Internet sesión Border Controller (SBC), siempre y cuando se cumple alguna de las condiciones siguientes:
  
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación en la piscina y puede enrutar tráfico de manera uniforme a todos los servidores de mediación en el grupo.
    
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación en la piscina y puede enrutar tráfico de manera uniforme a todos los servidores de mediación en el grupo.
    
Puede utilizar el 2013 de Microsoft Lync Server, herramienta de planeación para evaluar si el grupo de Front-End donde desee colocar el servidor de mediación puede manejar la carga. Si su entorno no cumple estos requisitos, se debe implementar un conjunto de servidor de mediación de independiente.
  
En general, colocación de A / V Conferencing Server o servidor de mediación no se recomienda si su organización tiene alta disponibilidad y escalabilidad requirementsFor detalles acerca de la colocación de estos roles de servidor en un grupo de Front-End en una edición Enterprise implementación, vea [definir y configurar un grupo de servidores frontales](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación. Para obtener más información acerca de la característica de conferencias audiovisuales y componentes, vea [Planear la conferencia](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación de planificación. Para obtener más información acerca de las características de Telefonía IP empresarial y componentes, incluido el servidor de mediación, consulte [Plan para Telefonía IP empresarial en Skype para el año 2015 de Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación de planeamiento.
  

