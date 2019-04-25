---
title: Implementar un servidor de mediación en el generador de Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: Obtenga información sobre cómo definir e implementar un servidor de mediación en el generador de Skype para Business Server.'
ms.openlocfilehash: 558c1324b488d36f69f760a2dc0484f22586d93c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229107"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Implementar un servidor de mediación en el generador de Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo definir e implementar un servidor de mediación en el generador de Skype para Business Server.
  
La carga de trabajo de Enterprise Voice, conferencias y aplicaciones avanzadas de Enterprise Voice (aplicación de grupo de respuesta, aplicación estacionamiento de llamadas, control de admisión de llamadas (CAC) y así sucesivamente), están disponibles en los grupos de servidores Front-End. En el servidor Front-End se incorpora la funcionalidad del servidor de mediación. No es necesario un servidor de mediación independiente independiente. 
  
La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet. Para conectar su infraestructura de Enterprise Voice a su proveedor de troncos SIP, debe implementarse un servidor de mediación independiente.
  
La conexión entre Skype para Business Server (un servidor de mediación se combina en un grupo de servidores Front-End o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica llamada un tronco. En los temas de esta sección se describen cómo definir un tronco y cómo implementar un servidor de mediación independiente, si se conecta a un tronco SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir un servidor de mediación en el Generador de topologías

Puede agregar el servidor de mediación como un rol instalado en un grupo de servidores Front-End, o definir un grupo de servidores de mediación de servidor independiente independiente.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para agregar un servidor de mediación a un grupo de servidores Front-End

1. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En el generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores Front-End.
    
3. En el árbol de consola, haga clic en el tipo de grupo de servidores Front-End que desea y, a continuación, haga clic en **nuevo Front-End del grupo..**.
    
4. Avance por el asistente para **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.
    
5. En los **roles de servidor combinados Select**, marque la opción **Combinar el servidor de mediación**.
    
    > [!NOTE]
    > Si el tipo de grupo de servidores Front-End que ha seleccionado es la edición Enterprise, a continuación, el componente de servidor de mediación se instalará en todos los servidores Front-End de ese grupo de servidores Front-End. 
  
    > [!NOTE]
    > El **grupo del próximo salto** utilizado por el servidor de mediación será el grupo de servidores Front-End donde el servidor de mediación está combinado en.
  
    > [!NOTE]
    > El **grupo de servidores perimetrales** usado por el servidor de mediación será el mismo grupo de servidores perimetrales asociado con el grupo de servidores Front-End donde el servidor de mediación se combina en.
  
6. Haga clic en **Convertir en predeterminada** para utilizar este grupo de servidores Front-End para enrutar las llamadas a la RTC.
    
7. Haga clic en **Finalizar** cuando haya terminado de asociar a uno o más pares al grupo de servidores Front-End.
    
    > [!NOTE]
    > Antes de continuar con el siguiente paso en el proceso de implementación de Enterprise Voice, asegúrese de que el grupo de servidores de mediación (es decir, Front-End un grupo con el componente de servidor de mediación combinado) usa el FQDN que ha especificado. 
  
8. Haga clic en el nodo de **Skype para Business Server 2015** y, a continuación, haga clic en **Publicar topología**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Para agregar un servidor de mediación independiente

1. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En el generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.
    
3. En el árbol de consola, haga clic en el nodo **grupos de servidores de mediación** y, a continuación, haga clic en **grupo de servidores de mediación**.
    
4. En **Definir nuevo grupo de servidores de mediación**, escriba el nombre de dominio completo del grupo de servidor de mediación (FQDN).
    
5. A continuación, siga uno de los procedimientos siguientes:
    
   - Si desea implementar varios servidores de mediación en el grupo de servidores para proporcionar una alta disponibilidad, a continuación, seleccione **el grupo de servidores de varios equipos**.
    
     > [!NOTE]
     > Debe [implementar](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para admitir grupos de servidores de mediación que tienen varios servidores de mediación.
  
   - Si desea implementar un solo servidor de mediación del grupo de servidores debido a que no requieran una alta disponibilidad, a continuación, seleccione **el grupo de servidores de un solo equipo**. Omita el paso siguiente.
    
6. Si ha seleccionado **Grupo de varios equipos** en el paso anterior, en el elemento **Definir equipos de este grupo**, haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los demás servidores de mediación que desea agregar al grupo de servidores. Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente**.
    
7. En la página **Seleccionar el próximo salto** , haga clic en el **grupo del próximo salto**, haga clic en el FQDN del grupo de servidores Front-End que usará este grupo de servidores de servidor de mediación y, a continuación, haga clic en **siguiente**.
    
8. En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:
    
   - Si desea proporcionar conectividad RTC a los usuarios externos habilitados para Enterprise Voice, **Seleccione grupo de servidores perimetrales usado por este servidor de mediación**, haga clic en el FQDN del grupo de servidores de servidor perimetral que usará este grupo de servidores de servidor de mediación para proporcionar conectividad RTC a los usuarios externos y, a continuación, haga clic en **siguiente**.
    
   - Si no planea habilitar a los usuarios externos para Enterprise Voice, o si no desea proporcionar conectividad RTC a los usuarios cuando están fuera de la red interna, haga clic en **siguiente**.
    
9. Haga clic en el nodo de **Skype para Business Server 2015** y, a continuación, haga clic en **Publicar topología**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir los puertos de escucha del servidor de mediación

Siga los pasos descritos en este tema para usar el generador de topología para definir los puertos de escucha de un servidor de mediación o un grupo aceptará conexiones entrantes procedentes de un par de puerta de enlace.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar los puertos de escucha del servidor de mediación

1. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En el generador de topología, en el árbol de consola, expanda el nodo **grupos de servidores de mediación** y haga clic en el servidor de mediación creado anteriormente.
    
3. De forma predeterminada, los puertos de escucha de SIP en el servidor de mediación son 5070 para el tráfico TLS de Skype para Business Server y 5067 para el tráfico TLS de elementos del mismo nivel (por ejemplo, las puertas de enlace, PBXe o SBCs). El puerto TCP está deshabilitado de forma predeterminada. Debe habilitar el puerto TCP si dispone de puertas de enlace que no admiten TLS.
    
4. Especifique el deseado TLS o TCP escucha intervalo de puertos del servidor de mediación aceptará conexiones entrantes procedentes de puertas de enlace RTC.
    
    > [!NOTE]
    > No es necesario indicar este intervalo si no se ha seleccionado **Habilitar puerto TCP**. Este valor es opcional.
  

