---
title: Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: Aprender a definir e implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015.'
ms.openlocfilehash: bfb915528ba73851d3bd60cc8ff3b33b968376e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a>Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a definir e implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015.
  
La carga de trabajo de la Telefonía IP empresarial, conferencias de acceso telefónico y aplicaciones avanzadas de Telefonía IP empresarial (aplicación de grupo de respuesta, aplicación llamada Park, control de admisión de llamadas (CAC) y así sucesivamente), están disponibles en grupos de Front-End. La funcionalidad del servidor de mediación está integrada en el servidor Front-End. No es necesario un servidor de mediación de independiente independiente. 
  
La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet. Para conectar la infraestructura de Telefonía IP empresarial con su proveedor de tronco SIP, se debe implementar un servidor de mediación de independiente.
  
La conexión entre Skype para Business Server (un servidor de mediación ubicado en un grupo de servidores Front-End o un servidor de mediación de independiente) y una puerta de enlace se define como una asociación lógica que se denomina un tronco. En los temas de esta sección describen cómo definir un tronco y cómo implementar un servidor de mediación de independiente, si se conecta a un troncal SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir un servidor de mediación en el Generador de topologías

Puede agregar el servidor de mediación como una función colocada en un grupo de servidores Front-End, o definir un grupo de servidor de mediación de independiente.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para agregar un servidor de mediación a un grupo de servidores Front-End

1. Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. Generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores Front-End.
    
3. En el árbol de consola, haga clic en el tipo de grupo de servidores Front-End que desee y, a continuación, haga clic en **grupo nuevo Front-End..**.
    
4. Avance por el asistente para **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.
    
5. En **funciones de servidor colocadas Select**, seleccione la opción **Colocar el servidor de mediación**.
    
    > [!NOTE]
    > Si el tipo de grupo de Front-End que seleccionó es la edición Enterprise, se instalará el componente de servidor de mediación en todos los servidores frontales de ese grupo de Front-End. 
  
    > [!NOTE]
    > El **siguiente grupo de salto** utilizado por el servidor de mediación será donde está ubicado el servidor de mediación en el grupo de Front-End.
  
    > [!NOTE]
    > La **piscina de borde** utilizado por el servidor de mediación será el mismo grupo de borde que se asociado con el grupo de Front-End donde está ubicado el servidor de mediación en.
  
6. Haga clic en **Establecer como predeterminado** para utilizar este grupo de servidores Front-End para enrutar las llamadas a la RTC.
    
7. Haga clic en **Finalizar** cuando haya terminado de asociar uno o varios elementos del mismo nivel para el grupo de servidores Front-End.
    
    > [!NOTE]
    > Antes de continuar con el siguiente paso en el proceso de implementación de Telefonía IP empresarial, asegúrese de que el grupo de servidor de mediación (es decir, Front-End ubicado de grupo con el componente de servidor de mediación) utiliza el FQDN que ha especificado. 
  
8. Haga clic en el nodo de **Skype para Business Server 2015** y, a continuación, haga clic en **Publicar la topología**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Para agregar un servidor de mediación independiente

1. Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. Generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.
    
3. En el árbol de consola, haga clic en el nodo **grupos de mediación** y, a continuación, haga clic en **grupo de servidor de mediación**.
    
4. En **Definir agrupación de mediación**, escriba el nombre de dominio completo del grupo de servidor de mediación (FQDN).
    
5. A continuación, siga uno de los procedimientos siguientes:
    
   - Si desea implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, a continuación, seleccione el **grupo de equipo múltiple**.
    
    > [!NOTE]
    > Debe desplegar (.. /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para admitir grupos de servidores de mediación que tienen varios servidores de mediación.
  
   - Si desea implementar sólo un servidor de mediación en el grupo, ya que no requieren alta disponibilidad, a continuación, seleccione el **grupo de equipo único**. Omita el paso siguiente.
    
6. Si ha seleccionado **Grupo de varios equipos** en el paso anterior, en el elemento **Definir equipos de este grupo**, haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los demás servidores de mediación que desea agregar al grupo. Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente**.
    
7. En la página **Seleccionar el siguiente salto** , haga clic en **grupo de salto siguiente**, el FQDN del grupo de servidores Front-End que utilizará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.
    
8. En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:
    
   - Si desea proporcionar conectividad PSTN a usuarios externos habilitados para Telefonía IP empresarial, **Seleccione grupo de borde utilizado por este servidor de mediación**, haga clic en el FQDN del grupo de servidores de borde que se va a utilizar este grupo de servidores de mediación para proporcionar conectividad PSTN a los usuarios externos y, a continuación, haga clic en **siguiente**.
    
   - Si no va a permitir que los usuarios externos para Telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando se encuentran fuera de la red interna, haga clic en **siguiente**.
    
9. Haga clic en el nodo de **Skype para Business Server 2015** y, a continuación, haga clic en **Publicar la topología**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir los puertos de escucha del servidor de mediación

Siga los pasos de este tema para utilizar el generador de topología para definir los puertos de escucha de un servidor de mediación o grupo aceptará conexiones entrantes de un interlocutor de puerta de enlace.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar los puertos de escucha del servidor de mediación

1. Iniciar el generador de topología: Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En el generador de topología, en el árbol de consola, expanda el nodo **grupos de mediación** y (ratón) en el servidor de mediación creado previamente.
    
3. De forma predeterminada, los puertos de escucha de SIP en el servidor de mediación son 5070 para el tráfico TLS de Skype para Business Server y 5067 para tráfico TLS de colegas (como puertas de enlace, PBXe o SBCs). El puerto TCP está deshabilitado de forma predeterminada. Debe habilitar el puerto TCP si dispone de puertas de enlace que no admitan TLS.
    
4. Especificar que el deseado TLS o TCP escucha intervalo de puertos del servidor de mediación aceptará conexiones entrantes de puertas de enlace PSTN.
    
    > [!NOTE]
    > No es necesario indicar este intervalo si no se ha seleccionado **Habilitar puerto TCP**. Este valor es opcional.
  

