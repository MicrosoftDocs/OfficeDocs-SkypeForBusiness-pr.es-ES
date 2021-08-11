---
title: Implementar un grupo de servidores piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Uno de los primeros pasos necesarios para la migración a Skype Empresarial Server 2019 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia Skype Empresarial Server 2019 con la implementación heredada. La coexistencia es un estado temporal que dura hasta que se han movido todos los usuarios y grupos a Skype Empresarial Server 2019.
ms.openlocfilehash: d7e02d1cb921f973d8851cfc3c8bbff0f3e81aa92f1945584ee94fa59a45e9ee
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279608"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implementar Skype Empresarial Server grupo piloto de 2019

Uno de los primeros pasos necesarios para la migración a Skype Empresarial Server 2019 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia Skype Empresarial Server 2019 con la implementación heredada. La coexistencia es un estado temporal que dura hasta que se han movido todos los usuarios y grupos a Skype Empresarial Server 2019. 
  
Cuando se implementa un grupo piloto, se utiliza el Asistente para definir nuevo grupo de servidores front-end. Debe implementar las mismas características y cargas de trabajo en el grupo piloto de Skype Empresarial Server 2019 que tiene en el grupo heredado. Si implementó el servidor de archivado, el servidor de supervisión o System Center Operations Manager para archivar o supervisar el entorno heredado y desea seguir archivando o supervisando durante la migración, también debe implementar estas características en el entorno piloto. La versión que implementó para archivar o supervisar el entorno heredado no capturará datos en su Skype Empresarial Server 2019. 
  
> [!NOTE]
> El siguiente procedimiento trata las funciones y configuración que se deben tener en cuenta como parte del proceso de implementación del grupo piloto. Esta sección solo subraya puntos clave que se deberían tener en cuenta como parte de la implementación de grupo piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implementar un grupo Skype Empresarial Server piloto de 2019

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
2. Expanda el árbol hasta que llegue a **Skype Empresarial Server 2019** Enterprise Edition  >  **grupos de servidores front-end**.
    
3. Haga clic con el **botón Enterprise Edition grupos de servidores front-end y** seleccione Nuevo grupo de servidores **front-end**.
  
4. Escriba el nombre de dominio completo (FQDN) del grupo. Al definir el grupo piloto, puede elegir implementar un grupo de servidores front-end Enterprise Edition un servidor Standard Edition cliente. Skype Empresarial Server 2019 no requiere que las características del grupo piloto coincidan con lo que se implementó en el grupo heredado.
    
    > [!CAUTION]
    > El FQDN de grupo o servidor que defina para el grupo piloto debe ser único. No puede coincidir con el nombre del grupo heredado implementado actualmente ni con ningún otro servidor implementado actualmente. 
  
5. En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar solo las características de mensajería instantánea (MI) y presencia, activaría la casilla conferencia para permitir la mensajería instantánea multiparte, pero no activaría las casillas conferencia de acceso telefónico local (RTC), Telefonía IP empresarial o Control de admisión de llamadas, ya que representan características de conferencia de voz, vídeo y colaboración. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. En la **página Seleccionar** roles de servidor con colocación, se recomienda que elija colocar el servidor de mediación en Skype Empresarial Server 2019. Al combinar una topología heredada con Skype Empresarial Server 2019, es necesario que primero se coloque el servidor de mediación heredado. Después de combinar las topologías y configurar el servidor de mediación de Skype Empresarial Server 2019, puede decidir si desea mantener el servidor de mediación ubicado o cambiarlo a un servidor independiente cuando mueva el rol servidor de mediación Skype Empresarial Server Skype Empresarial Server 2019 más adelante en el proceso de implementación. 
   
7. En  la página Asociar roles de servidor con este grupo de servidores front-end, durante la implementación del grupo *piloto,* no elija la opción Habilitar un grupo de servidores perimetrales que usará el componente multimedia de este grupo de **servidores front-end.** Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento. 
  
8. En la página **Seleccionar un servidor de aplicaciones web para Office**, haga clic en **Nuevo** y especifique el FQDN del servidor de aplicaciones.
  
9. En la página Definir el almacén **de SQL Server** de archivado, al definir el almacén de SQL Server para el archivado y la supervisión de Skype Empresarial Server, seleccione la instancia de SQL Server creada anteriormente para Skype Empresarial Server 2019. 
  
10. Para publicar la topología, haga clic con el botón secundario **en el Skype Empresarial Server** y, a continuación, haga clic en Publicar **topología**.
  
11. Una vez completado el proceso de publicación, haga clic en **Finalizar**.

12. Antes de pasar a la siguiente sección denominada "Comprobar la coexistencia del grupo piloto con el grupo heredado Skype Empresarial Server", debe instalar el nuevo grupo piloto front-end que hemos definido en la topología publicada, siga los procedimientos descritos aquí Instalar [Skype Empresarial Server](../../SfbServer/deploy/install/install-skype-for-business-server.md) en servidores de la topología

13. Una vez completado el paso anterior, pase a la sección siguiente a Comprobar la coexistencia del grupo piloto con el grupo heredado.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
