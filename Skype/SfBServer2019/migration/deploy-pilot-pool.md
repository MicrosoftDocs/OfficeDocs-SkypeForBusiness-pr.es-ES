---
title: Implementar un grupo de servidores piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uno de los primeros pasos necesarios para la migración a Skype para Business Server 2019 consiste en implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Skype para Business Server 2019 con su implementación heredada. La coexistencia es un estado temporal que dura hasta que mueva todos los usuarios y grupos de servidores a Skype para Business Server 2019.
ms.openlocfilehash: e0ac949b0cc7a52e1da5edd9f150e5f59717c08f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890658"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implementación de Skype para el grupo piloto de Business Server 2019

Uno de los primeros pasos necesarios para la migración a Skype para Business Server 2019 consiste en implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Skype para Business Server 2019 con su implementación heredada. La coexistencia es un estado temporal que dura hasta que mueva todos los usuarios y grupos de servidores a Skype para Business Server 2019. 
  
Al implementar un grupo piloto, use el Asistente para definir nuevo Front-End del grupo. Debe implementar las mismas características y cargas de trabajo en su Skype para Business Server 2019 grupo piloto que tiene en su grupo heredado. Si ha implementado el servidor de archivado, el servidor de supervisión o System Center Operations Manager para archivado o supervisión del entorno heredado y, desea continuar archivado o supervisión durante la migración, debe también implementar estas características en su entorno piloto. La versión implementa para archivar o supervisar su heredado entorno no capturará datos en su Skype para entorno empresarial Server 2019. 
  
> [!NOTE]
> El procedimiento siguiente describe las características y configuración que se debe tener en cuenta como parte de su proceso de implementación del grupo piloto en general. Esta sección resalta sólo puntos clave que debe tener en cuenta como parte de la implementación del grupo piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implementar un Skype para Business Server 2019 el grupo piloto

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
2. Expanda el árbol hasta llegar a **Skype para Business Server 2019** > **los grupos de servidores Front-End de Enterprise Edition**.
    
3. Haga clic en **grupos de servidores Front-End de Enterprise Edition** y seleccione **Nuevo grupo de servidores Front-End**.
  
4. Escriba el nombre de dominio completo (FQDN) de grupo de servidores. Al definir el grupo piloto, puede elegir implementar un servidor Standard Edition o un grupo de servidores de Front-End de Enterprise Edition. Skype para Business Server 2019 no requiere que las características de grupo piloto coinciden con lo que se implementó en su grupo heredado.
    
    > [!CAUTION]
    > El grupo de servidores o el servidor FQDN que se define para el grupo piloto debe ser único. No puede coincidir con el nombre del grupo heredado de implementada actualmente o cualquier otro servidor implementada actualmente. 
  
5. En la página **Seleccionar características** , seleccione las casillas de verificación de las características que desee en este grupo de servidores Front-End. Por ejemplo, si va a implementar sólo mensajería instantánea (mi) y características de presencia, se selecciona la casilla de verificación de conferencia para permitir la mensajería instantánea con varios participantes, pero no se seleccionan la conferencia Dial-in (RTC), Enterprise Voice, o comprobar el Control de admisión de llamadas cuadros, ya que representan la voz, las características de conferencia de vídeo y de colaboración. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. En la página **Seleccionar servidor combinado roles** , se recomienda que elija instalar el servidor de mediación en Skype para Business Server 2019. Al combinar una topología heredada con Skype para Business Server 2019, es necesario que primero instala el servidor de mediación heredado. Después de combinar las topologías y configurar el Skype para servidor de mediación 2019 Business Server, puede decidir si desea mantener el servidor de mediación combinado, o cámbiela a un servidor independiente, cuando se mueve el rol de servidor de mediación para Skype para Business Server 2019 más adelante en el proceso de implementación. 
   
7. En la página **asociar funciones de servidor con este grupo de servidores Front-End** , durante la implementación del grupo piloto, *de lo contrario* elija la opción de **Habilitar un grupo de servidores perimetrales que va a usar el componente de medios de este grupo de servidores Front-End** . Esta es una característica se habilitará y poner en línea en una fase posterior de la migración. Mantener esta opción desactivada por ahora. 
  
8. En la página **Seleccionar un servidor de Office Web Apps** , haga clic en **nuevo**y especifique el FQDN del servidor de aplicaciones.
  
9. En la página **definir el almacén de SQL Server de archivado** , al definir el almacén de SQL Server para ambos Skype para archivado de servidor empresarial y la supervisión, seleccione la instancia de SQL Server creada anteriormente para Skype para Business Server 2019. 
  
10. Para publicar su topología, haga clic en el nodo de **Skype para Business Server** y, a continuación, haga clic en **Publicar topología**.
  
11. Cuando haya finalizado el proceso de publicación, haga clic en **Finalizar**.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

