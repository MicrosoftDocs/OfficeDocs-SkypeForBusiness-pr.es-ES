---
title: Crear un grupo de VIS en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumen: cree un grupo de servidores de interoperabilidad de vídeo en Skype empresarial Server con el generador de topologías.'
ms.openlocfilehash: 3e01659c4cef268a8748bd14c658eb5168b3ac97
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302731"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Crear un grupo de VIS en Skype empresarial Server
 
**Resumen:** Cree un grupo de servidores de interoperabilidad de vídeo en Skype empresarial Server con el generador de topologías.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Crear un VIS o un grupo de VIS con el Generador de topologías

1. Abra el Generador de topologías en el servidor front-end. En el panel izquierdo del creador de topología, haga clic con el botón secundario en **grupos de servidores** de interoperabilidad y seleccione **nuevo grupo de servidores**de interoperabilidad de vídeo. 
    
2. De este modo, se abrirá un asistente para **Crear un grupo de servidores de interoperabilidad de vídeo**. Proporcione el FQDN del grupo para el nuevo servidor de interoperabilidad de vídeo y seleccione **este grupo tiene un servidor** o **este grupo tiene varios servidores** en función de su requisito y, a continuación, haga clic en **siguiente**.
    
    Si desea implementar un grupo de servidores de interoperabilidad de vídeo para proporcionar alta disponibilidad, seleccione **este grupo tiene varios servidores**. Recuerde lo siguiente en relación con esta opción: 
    
    - Debe implementar el equilibrio de carga de DNS para admitir grupos de servidores de interoperabilidad. 
    
   - En la siguiente página, en el elemento **Definir los equipos de este grupo de servidores**, escriba el **FQDN de equipo** de cada servidor del grupo en el campo de texto y, luego, haga clic en **Agregar**. Repita este paso para agregar otro servidor de interoperabilidad de vídeo al grupo. Cuando haya definido todos los equipos en el grupo, presione **Siguiente**.
    
     Si desea implementar solo un servidor de interoperabilidad de vídeo en el grupo porque no necesita alta disponibilidad, seleccione **este grupo tiene un servidor** y pulse **siguiente**.
    
3. Seleccione el grupo de servidores del próximo salto/FE de la lista desplegable y presione **Siguiente**.
    
4. Seleccione un grupo de servidores perimetrales para asociarlo al VIS y presione **Finalizar**.
    
5. Defina un puerto TCP o TLS.
    
    Seleccione el servidor de interoperabilidad de vídeo recién agregado en el panel izquierdo del generador de topología, haga clic con el botón secundario en él y elija **Editar propiedades**. Habilite o actualice el puerto TCP o TLS (lo que corresponda en su caso) y seleccione **Aceptar**. Aunque se agrega TLS de forma predeterminada, solo se ha probado TCP con Cisco Unified Communications Manager (CallManager o CUCM).
    
6. Agregue una puerta de enlace de vídeo. Para ello, expanda Componentes compartidos, haga clic con el botón secundario en **Puertas de enlace de vídeo** y, luego, seleccione **Nueva puerta de enlace de vídeo**.
    
7. Escriba el FQDN o la dirección IP para la puerta de enlace de vídeo. Esta puerta de enlace de vídeo puede estar en un subdominio o en un dominio distinto. El CUCM que usan los VTC del sistema puede servir como puerta de enlace de vídeo.
    
8. Seleccione IPv4 o IPv6, lo que corresponda. Puede usar todas las direcciones IP configuradas o acotar el uso del servicio a determinadas direcciones IP.
    
9. Seleccione el puerto de escucha de la puerta de enlace de vídeo. Seleccione el protocolo de transporte (TCP o TLS) y asócielo con un servidor de interoperabilidad de video configurado para un tronco de video SIP. El protocolo de transporte de la puerta de enlace de vídeo tiene que ser el mismo que el que se ha configurado para el VIS.
    
10. Tras completar el paso anterior, se agrega el tronco SIP de vídeo pertinente. Haga clic con el botón secundario en el tronco SIP de vídeo y seleccione el tronco que acaba de agregar. Se puede cambiar el nombre del tronco del SIP de video, el servidor de interoperabilidad del video asociado, el protocolo de transporte SIP y el puerto. 
    
    > [!NOTE]
    >  Un servidor de interoperabilidad de vídeo admite los troncos de 1: N. Por eso se pueden agregar varios troncos, que están asociados con un único servidor de interoperabilidad de video, en el que cada tronco termina en una puerta de enlace de video diferente. La limitación es que una puerta de enlace de vídeo determinada tiene solo un tronco que puede definirse para la implementación de Skype empresarial Server.
  
11. Publique el documento de topología como se describe en [crear y publicar una nueva topología en Skype empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Para mejorar la resistencia, es posible que desee configurar un segundo servidor de interoperabilidad de vídeo o un grupo de servidores de interoperabilidad de copia de seguridad o un grupo de aplicaciones para el usuario. Consulte [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) para más información.
  
Todas las tareas realizadas con el Generador de topologías tendrían que finalizar aquí. Continúe con la instalación del software en el nuevo servidor o en los nuevos servidores VIS.
## <a name="see-also"></a>Vea también

[Implementar el rol de servidor VIS en Skype empresarial Server](deploy-the-vis-server-role.md)

[Planear el servidor de interoperabilidad de vídeo en Skype empresarial Server](../../plan-your-deployment/video-interop-server.md)
  
[Crear y publicar una nueva topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md)
