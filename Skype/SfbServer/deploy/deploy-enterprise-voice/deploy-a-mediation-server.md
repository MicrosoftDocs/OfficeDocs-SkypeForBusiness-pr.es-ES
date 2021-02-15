---
title: Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: obtenga información sobre cómo definir e implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server.'
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836920"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Implementar un servidor de mediación en el Generador de topologías en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo definir e implementar un servidor de mediación en topology Builder en Skype Empresarial Server.
  
La carga Telefonía IP empresarial de trabajo de Telefonía IP empresarial, las conferencias de acceso telefónico local y las aplicaciones avanzadas de Telefonía IP empresarial (aplicación grupo de respuesta, aplicación de estacionamiento de llamadas, control de admisión de llamadas, entre otros) están disponibles en los grupos de servidores front-end. La funcionalidad del servidor de mediación está integrada en el servidor front-end. No es necesario un servidor de mediación independiente. 
  
La única excepción es si configura un tronco SIP para conectarse a un controlador de borde de sesión para un proveedor de servicios de telefonía por Internet. Para conectar la infraestructura Telefonía IP empresarial con el proveedor de troncos SIP, debe implementarse un servidor de mediación independiente.
  
La conexión entre Skype Empresarial Server (un servidor de mediación que se coloca en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica denominada tronco. En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente si se conecta a un tronco SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir un servidor de mediación en el Generador de topologías

Puede agregar un servidor de mediación como rol de instalación en un grupo de servidores front-end o definir un grupo de servidores de mediación independiente independiente.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para agregar un servidor de mediación a un grupo de servidores front-end

1. Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**
    
2. En el Generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.
    
3. En el árbol de consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en Nuevo grupo **de servidores front-end.**
    
4. Navegue por el Asistente para definir nuevo grupo **de servidores front-end** hasta que llegue a la página Seleccionar **roles de servidor juntos.**
    
5. En **Select collocated server roles**, active la opción **Collocate Mediation Server**.
    
    > [!NOTE]
    > Si el tipo de grupo de servidores front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end. 
  
    > [!NOTE]
    > El **grupo de servidores del** próximo salto usado por el servidor de mediación será el grupo de servidores front-end en el que se coloca el servidor de mediación.
  
    > [!NOTE]
    > El **grupo de servidores perimetrales** usado por el servidor de mediación será el mismo grupo de servidores perimetrales asociado al grupo de servidores front-end en el que se coloca el servidor de mediación.
  
6. Haga **clic en Convertir en** predeterminado para usar este grupo de servidores front-end para enrutar las llamadas a la RTC.
    
7. Haga **clic en** Finalizar cuando haya terminado de asociar uno o varios sistemas del mismo nivel al grupo de servidores front-end.
    
    > [!NOTE]
    > Antes de continuar con el siguiente paso del proceso de implementación de Telefonía IP empresarial, asegúrese de que el grupo de servidores de mediación (es decir, el grupo de servidores front-end con el componente de servidor de mediación junto) usa los FQDN especificados. 
  
8. Haga clic con el botón secundario en el nodo **de Skype Empresarial Server 2015** y, a continuación, haga clic en Publicar **topología.**
    
### <a name="to-add-a-standalone-mediation-server"></a>Para agregar un servidor de mediación independiente

1. Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**
    
2. En el Generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.
    
3. En el árbol de consola, haga clic con el botón secundario en el nodo **Grupos de servidores de** mediación y, a continuación, haga clic en Grupo de servidores de **mediación.**
    
4. En **Definir nuevo grupo de servidores de mediación,** escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.
    
5. A continuación, realice una de las siguientes acciones:
    
   - Si desea implementar varios servidores de mediación en el grupo de servidores para proporcionar alta disponibilidad, seleccione **Grupo de varios equipos.**
    
     > [!NOTE]
     > Debe implementar [para admitir grupos](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) de servidores de mediación que tengan varios servidores de mediación.
  
   - Si desea implementar solo un servidor de mediación en el grupo de servidores porque no necesita alta disponibilidad, seleccione Grupo **de servidores de un solo equipo.** Omita el paso siguiente.
    
6. Si seleccionó grupo de varios equipos  en el paso anterior, en Definir los equipos de este elemento de grupo, haga clic en **FQDN** del equipo, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en Agregar **.**  Repita este paso para todos los demás servidores de mediación que desee agregar al grupo de servidores. Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente.**
    
7. En **la** página Seleccionar el próximo salto, haga clic en Grupo de servidores del próximo **salto,** en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **Siguiente**.
    
8. En la **página Seleccionar un servidor perimetral,** realice una de las siguientes acciones:
    
   - Si desea proporcionar conectividad RTC a usuarios externos habilitados para Telefonía IP empresarial, en Seleccionar grupo de servidores perimetrales usado por este servidor de mediación, haga clic en el FQDN del grupo de servidores perimetrales que usará este grupo de servidores de mediación para proporcionar conectividad RTC a esos usuarios externos y, a continuación, haga clic en Siguiente **.**
    
   - Si no tiene previsto habilitar usuarios externos para Telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando están fuera de la red interna, haga clic en **Siguiente**.
    
9. Haga clic con el botón secundario en el nodo **de Skype Empresarial Server 2015** y, a continuación, haga clic en Publicar **topología.**
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir los puertos de escucha del servidor de mediación

Siga los pasos descritos en este tema para usar el Generador de topologías para definir los puertos de escucha que un servidor o grupo de servidores de mediación aceptará conexiones entrantes desde un sistema del mismo nivel de puerta de enlace.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar los puertos de escucha del servidor de mediación

1. Inicie el Generador de topologías: Haga clic en Inicio **,** Todos los **programas,** Skype Empresarial **Server 2015** y, a continuación, haga clic en Skype Empresarial **Server 2015Topology Builder.**
    
2. En el Generador de topologías,  en el árbol de consola, expanda el nodo Grupos de servidores de mediación y haga clic con el botón secundario en el servidor de mediación creado anteriormente.
    
3. De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico TLS de Skype Empresarial Server y 5067 para el tráfico TLS desde sistemas del mismo nivel (como puertas de enlace, PBX o SBC). El puerto TCP está deshabilitado de forma predeterminada. Debe habilitar el puerto TCP si tiene puertas de enlace que no admiten TLS.
    
4. Especifique el intervalo de puertos de escucha TCP o TLS deseado que el servidor de mediación aceptará conexiones entrantes de puertas de enlace RTC.
    
    > [!NOTE]
    > No es necesario especificar un intervalo de puertos TCP si **no** se ha activado Habilitar puerto TCP. Este valor es opcional.
  

