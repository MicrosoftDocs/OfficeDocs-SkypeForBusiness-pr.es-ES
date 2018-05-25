---
title: Agregar colocaciones de servidor Front-End 2010
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
description: Para una implementación de Enterprise Edition, puede combinar cualquiera el A / servicio de conferencia A/v, el servidor de mediación o ambos en el grupo de servidores Front-End, o se pueden implementar cada uno de ellos como servidores independientes. Para una implementación de servidor Standard Edition, el servicio de conferencia A/v siempre se instala también si se habilita la conferencia.
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-server-collocations-2010"></a>Agregar colocaciones de servidor Front-End 2010
 
Para una implementación de Enterprise Edition, puede combinar cualquiera el A / servicio de conferencia A/v, el servidor de mediación o ambos en el grupo de servidores Front-End, o se pueden implementar cada uno de ellos como servidores independientes. Para una implementación de servidor Standard Edition, el servicio de conferencia A/v siempre se instala también si se habilita la conferencia.
  
> [!NOTE]
> Un servicio de conferencia A/v es necesario si se ha seleccionado **conferencias** en la página **Seleccionar características** . Un grupo de servidores Front-End de Enterprise Edition puede usar un combinados A / servicio de conferencia A/v o independiente o grupo de servidores de conferencia A/v. Si conferencia no se ha seleccionado el combinar A / servicio de conferencia A/v no estará disponible.
  
Puede combinar el rol de servidor de mediación en una Standard Edition Front-End o grupo de servidores Front-End de Enterprise Edition. Si implementa conexiones SIP directas a una puerta de enlace de completa telefónica conmutada (RTC) que admite el desvío de medios y el equilibrio de carga del sistema de nombres de dominio (DNS), no es necesario un grupo de servidores de mediación independiente. Un grupo de servidores de mediación independiente no es necesario porque las puertas de enlace completa son capaces de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico desde cualquier servidor de mediación en un grupo de servidores. También se recomienda instalar el servidor de mediación en un grupo de servidores Front-End cuando se han implementado el IP-PBX o conectarse para el controlador de borde de sesión de telefonía Server del proveedor de Internet (SBC), siempre y cuando se cumple alguna de las siguientes condiciones:
  
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los servidores de mediación en el grupo de servidores.
    
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los servidores de mediación en el grupo de servidores.
    
Puede usar Microsoft Lync Server 2013, herramienta de planeación para evaluar si el grupo de servidores Front-End donde desea colocar el servidor de mediación puede administrar la carga. Si el entorno no cumple estos requisitos, a continuación, debe implementar un grupo de servidores de mediación independiente.
  
En general, combinación de A / servidor de conferencia A/v o servidor de mediación no se recomienda si su organización tiene una alta disponibilidad y escalabilidad requirementsFor detalles acerca de combinar estas funciones de servidor en un grupo de servidores Front-End de Enterprise Edition implementación, consulte [definir y configurar un grupo de servidores Front-End](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) en la documentación de implementación. Para obtener información detallada acerca de los / característica de conferencia A/v y de los componentes, consulte [Planning for Conferencing](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) en la documentación de planeación. Para obtener información detallada sobre las características de Enterprise Voice y componentes, incluido el servidor de mediación, consulte [Plan para Enterprise Voice en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) en la documentación de planeación.
  

