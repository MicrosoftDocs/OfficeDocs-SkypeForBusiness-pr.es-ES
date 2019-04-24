---
title: Crear un grupo de servidores con respecto de Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumen: Cree un grupo de servidores de interoperabilidad de vídeo en Skype para Business Server mediante el generador de topología.'
ms.openlocfilehash: 484cb1c504680dde393d24ce65606e415d070edb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219639"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Crear un grupo de servidores con respecto de Skype para Business Server
 
**Resumen:** Crear un grupo de servidores de interoperabilidad de vídeo en Skype para Business Server mediante el generador de topología.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Crear un VIS o un grupo de VIS con el Generador de topologías

1. Abra el Generador de topologías en el servidor front-end. En el panel izquierdo del generador de topología, haga clic con el botón secundario en **Grupos de servidores de interoperabilidad de vídeo** y elija **Nuevo grupo de servidores de interoperabilidad de vídeo**. 
    
2. De este modo, se abrirá un asistente para **Crear un grupo de servidores de interoperabilidad de vídeo**. Proporcionar el FQDN del grupo de servidores para el nuevo servidor de interoperabilidad de vídeo y seleccione **este grupo de servidores tiene un servidor** o **este grupo de servidores tiene varios servidores** en función de sus requisitos, a continuación, haga clic en **siguiente**.
    
    Si desea implementar un grupo de servidores de interoperabilidad de vídeo para proporcionar una alta disponibilidad, seleccione **este grupo de servidores tiene varios servidores**. Recuerde lo siguiente en relación con esta opción: 
    
    - Debe implementar el equilibrio de carga DNS para admitir grupos de servidores de interoperabilidad de vídeo. 
    
   - En la siguiente página, en el elemento **Definir los equipos de este grupo de servidores**, escriba el **FQDN de equipo** de cada servidor del grupo en el campo de texto y, luego, haga clic en **Agregar**. Repita este paso para agregar otro servidor de interoperabilidad de vídeo al grupo de servidores. Cuando haya definido todos los equipos en el grupo, presione **Siguiente**.
    
     Si desea implementar un solo servidor de interoperabilidad de vídeo en el grupo de servidores debido a que no requieran una alta disponibilidad, a continuación, seleccione **este grupo de servidores tiene un servidor** y haga clic en **siguiente**.
    
3. Seleccione el grupo de servidores del próximo salto/FE de la lista desplegable y presione **Siguiente**.
    
4. Seleccione un grupo de servidores perimetrales para asociarlo al VIS y presione **Finalizar**.
    
5. Defina un puerto TCP o TLS.
    
    Seleccione el servidor de interoperabilidad de vídeo recién agregado en el panel izquierdo del generador de topología, botón secundario haga clic en él y elija **Editar propiedades**. Habilite o actualice el puerto TCP o TLS (lo que corresponda en su caso) y seleccione **Aceptar**. Aunque de forma predeterminada se agrega TLS, TCP sólo se ha comprobado exhaustivamente con Cisco Unified Communications Manager (CallManager o CUCM).
    
6. Agregue una puerta de enlace de vídeo. Para ello, expanda Componentes compartidos, haga clic con el botón secundario en **Puertas de enlace de vídeo** y, luego, seleccione **Nueva puerta de enlace de vídeo**.
    
7. Escriba el FQDN o la dirección IP para la puerta de enlace de vídeo. Esta puerta de enlace de vídeo puede estar en un subdominio o en un dominio distinto. El CUCM que usan los VTC del sistema puede servir como puerta de enlace de vídeo.
    
8. Seleccione IPv4 o IPv6, lo que corresponda. Puede usar todas las direcciones IP configuradas o acotar el uso del servicio a determinadas direcciones IP.
    
9. Seleccione el puerto de escucha de la puerta de enlace de vídeo. Seleccione el protocolo de transporte (TCP o TLS) y asociarlo con un servidor de interoperabilidad de vídeo que se configura para un tronco SIP vídeo. El protocolo de transporte de la puerta de enlace de vídeo tiene que ser el mismo que el que se ha configurado para el VIS.
    
10. Tras completar el paso anterior, se agrega el tronco SIP de vídeo pertinente. Haga clic con el botón secundario en el tronco SIP de vídeo y seleccione el tronco que acaba de agregar. El nombre del tronco SIP vídeo, asociado vídeo de interoperabilidad de servidor, el protocolo de transporte SIP y puerto se pueden cambiar. 
    
    > [!NOTE]
    >  Un servidor de interoperabilidad de vídeo admite troncos de 1: n. Por lo tanto, varios troncos pueden agregarse, que se asocia con un único servidor de interoperabilidad de vídeo, donde cada tronco termina en una puerta de enlace de vídeo diferentes. La limitación es que una puerta de enlace de vídeo determinado tiene solo un tronco que puede definirse para la Skype para la implementación de Business Server.
  
11. Publicar el documento de topología tal como se describe en [crear y publicar la nueva topología de Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Para mejorar la resistencia, es posible que desee configurar un segundo grupo de servidor de interoperabilidad de vídeo o con respecto, o un grupo de servidores Front-End copia de seguridad. Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para más información.
  
Todas las tareas realizadas con el Generador de topologías tendrían que finalizar aquí. Continúe con la instalación del software en el nuevo servidor o en los nuevos servidores VIS.
## <a name="see-also"></a>Vea también

[Implementar el rol de servidor de respecto de Skype para Business Server](deploy-the-vis-server-role.md)

[Planeación de servidor de interoperabilidad vídeo en Skype para Business Server](../../plan-your-deployment/video-interop-server.md)
  
[Crear y publicar una nueva topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md)
