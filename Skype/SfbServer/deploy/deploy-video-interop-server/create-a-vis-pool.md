---
title: Crear un grupo de vis en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Resumen: cree un grupo de servidores de interoperabilidad de vídeo Skype Empresarial Server mediante el Generador de topologías.'
ms.openlocfilehash: 91a1ed8b5b8d5ce728a666be507a1c1026b0c88460d9ba33b519f1f3d3825aa8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283582"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>Crear un grupo de vis en Skype Empresarial Server
 
**Resumen:** Cree un grupo de servidores de interoperabilidad de vídeo Skype Empresarial Server mediante el Generador de topologías.
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>Crear un grupo vis o vis mediante el Generador de topologías

1. Abra el Generador de topologías en el servidor front-end. En el panel izquierdo del Generador de topologías, haga clic con el botón secundario en **Grupos** de servidores de interoperabilidad de vídeo y elija Nuevo grupo de servidores **de interoperabilidad de vídeo.** 
    
2. Se abrirá un asistente para crear un nuevo grupo de **servidores de interoperabilidad de** vídeo. Proporcione el FQDN del grupo para el  nuevo servidor de  interoperabilidad de vídeo y seleccione Este grupo de servidores tiene un servidor o Este grupo de servidores tiene varios servidores según su requisito y, a continuación, presione **Siguiente**.
    
    Si desea implementar un grupo de servidores de interoperabilidad de vídeo para proporcionar alta disponibilidad, seleccione **Este grupo tiene varios servidores.** Tenga en cuenta esta opción que: 
    
    - Debe implementar el equilibrio de carga DNS para admitir grupos de servidores de interoperabilidad de vídeo. 
    
   - En la página siguiente, para el elemento Definir los equipos de este grupo de servidores, escriba el **FQDN** del equipo de cada servidor del grupo en el campo de texto y, a continuación, haga clic en **Agregar**.  Repita este paso para agregar otro servidor de interoperabilidad de vídeo al grupo. Cuando haya definido todos los equipos del grupo, presione **Siguiente**.
    
     Si desea implementar solo un servidor de interoperabilidad de vídeo en el grupo de servidores porque no necesita alta disponibilidad, seleccione Este grupo de servidores **tiene un** servidor y presione **Siguiente**.
    
3. Seleccione el grupo de servidores/FE del próximo salto de la lista desplegable y presione **Siguiente**.
    
4. Seleccione un grupo de servidores perimetrales para asociarlo con el VIS y presione **Finalizar**.
    
5. Establezca un puerto TCP o TLS.
    
    Seleccione el servidor de interoperabilidad de vídeo recién agregado en el panel izquierdo del Generador de topologías, haga clic con el botón secundario en él y elija **Editar propiedades**. Habilite o actualice el puerto TCP o TLS según su requisito y elija **Aceptar**. Aunque de forma predeterminada se agrega TLS, solo TCP se ha probado completamente con el Administrador de comunicaciones unificadas de Cisco (CallManager o CUCM).
    
6. Agregar una puerta de enlace de vídeo. Para ello, expanda Componentes compartidos, haga clic con el botón secundario en **Puertas de enlace** de vídeo y seleccione Nueva puerta de enlace de **vídeo.**
    
7. Proporcione el FQDN de la puerta de enlace de vídeo o la dirección IP. La puerta de enlace de vídeo podría estar en un subdominio o en un dominio diferente. El CUCM usado por los VTC del sistema sirve como puerta de enlace de vídeo.
    
8. Seleccione IPv4 o IPv6 según corresponda. Puede usar todas las direcciones IP configuradas o limitar el uso del servicio a las direcciones IP seleccionadas.
    
9. Seleccione el puerto de escucha de la puerta de enlace de vídeo. Seleccione el protocolo de transporte (TCP o TLS) y asócialo a un servidor de interoperabilidad de vídeo configurado para un tronco SIP de vídeo. El protocolo de transporte para la puerta de enlace de vídeo debe coincidir con el protocolo de transporte configurado para el VIS.
    
10. Después de completar el paso anterior, se agrega un tronco de vídeo SIP correspondiente. Haga clic con el botón secundario en el tronco de vídeo SIP y seleccione el tronco que se acaba de agregar. El nombre del tronco SIP de vídeo, el servidor de interoperabilidad de vídeo asociado, el protocolo de transporte SIP y el puerto se pueden cambiar. 
    
    > [!NOTE]
    >  Un servidor de interoperabilidad de vídeo admite troncos 1:N. Por lo tanto, se pueden agregar varios troncos, que están asociados a un único servidor de interoperabilidad de vídeo, donde cada tronco termina en una puerta de enlace de vídeo diferente. La limitación es que una puerta de enlace de vídeo determinada tiene uno y solo un tronco que se puede definir para la Skype Empresarial Server implementación.
  
11. Publique el documento de topología tal como se describe en Crear y publicar nueva [topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md).
    
    > [!NOTE]
    > Para mejorar la resistencia, es posible que desee configurar un segundo servidor de interoperabilidad de vídeo o un grupo vis, o un grupo de servidores front-end de copia de seguridad. Vea [Mecanismos de resistencia para](../../plan-your-deployment/video-interop-server.md#resiliency) obtener más información.
  
Todas las tareas realizadas con el Generador de topologías ahora deben completarse. Continúe con la instalación del software en el nuevo servidor o servidores VIS.
## <a name="see-also"></a>Consulte también

[Implementar el rol de servidor VIS en Skype Empresarial Server](deploy-the-vis-server-role.md)

[Planear el servidor de interoperabilidad de vídeo en Skype Empresarial Server](../../plan-your-deployment/video-interop-server.md)
  
[Crear y publicar nueva topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md)
