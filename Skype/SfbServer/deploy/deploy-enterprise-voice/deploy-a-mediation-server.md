---
title: Implementar un servidor de mediación en el generador de topología en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Resumen: Aprenda a definir e implementar un servidor de mediación en el generador de topologías de Skype empresarial Server.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284651"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Implementar un servidor de mediación en el generador de topología en Skype empresarial Server
 
**Resumen:** Aprenda a definir e implementar un servidor de mediación en el generador de topologías de Skype empresarial Server.
  
La carga de trabajo de telefonía empresarial, las conferencias de acceso telefónico local y las aplicaciones de voz avanzadas para empresas (aplicación de grupo de respuesta, aplicación de Parque de llamadas, control de admisión de llamadas (CAC), etc.) están disponibles en los grupos de aplicaciones para el usuario. La funcionalidad del servidor de mediación está integrada en el servidor front-end. No es necesario disponer de un servidor de mediación independiente independiente. 
  
La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet. Para conectar su infraestructura de voz empresarial con su proveedor de troncal de SIP, se debe implementar un servidor de mediación independiente.
  
La conexión entre Skype empresarial Server (ya sea un servidor de Mediaización en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica denominada tronco. En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente, si se conecta a un tronco de SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definir un servidor de mediación en el Generador de topologías

Puede Agregar un servidor de mediación como un rol colocado en un grupo de servidores front-end o definir un grupo independiente de servidores de mediación independiente.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para agregar un servidor de mediación a un grupo de servidores front-end

1. Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.
    
2. En el generador de topología, en el árbol de consola, expanda el nombre del sitio para el que desea definir un grupo de servidores front-end.
    
3. En el árbol de consola, haga clic con el botón secundario en el tipo de grupo de servidores front-end que desee y, a continuación, haga clic en **nuevo grupo de servidores front-end.**..
    
4. Avance por el asistente para **Definir nuevo grupo de servidores front-end** hasta llegar a la página **Seleccionar roles de servidor combinados**.
    
5. En **Seleccionar roles de servidor**colocados, active la opción servidor de mediación de **Collocate**.
    
    > [!NOTE]
    > Si el tipo de grupo de front-end que seleccionó es Enterprise Edition, el componente de servidor de mediación se instalará en todos los servidores front-end de ese grupo de servidores front-end. 
  
    > [!NOTE]
    > El **grupo de próximos saltos** usado por el servidor de mediación será el grupo de servidores front-end en el que se encuentra el servidor de mediación.
  
    > [!NOTE]
    > El **Grupo perimetral** usado por el servidor de mediación será el mismo grupo perimetral asociado al grupo de servidores front-end en el que se encuentra el servidor de mediación.
  
6. Haga clic en **predeterminado** para usar este grupo de servidores front-end para enrutar llamadas a la RTC.
    
7. Haga clic en **Finalizar** cuando haya terminado de asociar uno o más elementos del mismo nivel al grupo de servidores front-end.
    
    > [!NOTE]
    > Antes de continuar con el siguiente paso del proceso de implementación de voz de empresa, asegúrese de que el grupo de servidores de mediación (es decir, el grupo front-end con el componente de servidor de mediación colocado) esté usando los FQDN que especificó. 
  
8. Haga clic con el botón secundario en el nodo **de Skype empresarial Server 2015** y, a continuación, haga clic en **publicar topología**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Para agregar un servidor de mediación independiente

1. Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.
    
2. En el generador de topologías, en el árbol de consola, expanda el nombre del sitio para el que desea definir un servidor de mediación.
    
3. En el árbol de consola, haga clic con el botón derecho en el nodo de **grupos** de mediación y en **grupo de servidores**de mediación.
    
4. En **definir nuevo grupo**de mediación, escriba el nombre de dominio completo (FQDN) del grupo de servidores de mediación.
    
5. A continuación, siga uno de los procedimientos siguientes:
    
   - Si desea implementar varios servidores de mediación en el grupo para proporcionar alta disponibilidad, seleccione **varios grupos de equipos**.
    
     > [!NOTE]
     > Debe [implementarlo](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) para admitir grupos de servidores de mediación que tengan varios servidores de mediación.
  
   - Si desea implementar solo un servidor de mediación en el grupo porque no necesita alta disponibilidad, seleccione **grupo de equipos únicos**. Omita el paso siguiente.
    
6. Si ha seleccionado **Grupo de varios equipos** en el paso anterior, en el elemento **Definir equipos de este grupo**, haga clic en **FQDN de equipo**, escriba el FQDN de cada servidor del grupo y, a continuación, haga clic en **Agregar**. Repita este paso para todos los demás servidores de mediación que desee agregar al grupo. Cuando haya definido todos los equipos del grupo, haga clic en **Siguiente**.
    
7. En la página **seleccionar el próximo salto** , haga clic en **grupo de próximos saltos**, haga clic en el FQDN del grupo de servidores front-end que usará este grupo de servidores de mediación y, a continuación, haga clic en **siguiente**.
    
8. En la página **Seleccionar un servidor perimetral**, realice una de las operaciones siguientes:
    
   - Si desea proporcionar conectividad RTC a usuarios externos habilitados para telefonía IP empresarial, en **Seleccionar grupo perimetral usado por este servidor**de mediación, haga clic en el FQDN del grupo de servidores perimetrales que usarán este grupo de servidores de mediación para proporcionar conectividad RTC a esos usuarios externos y, a continuación, haga clic en **siguiente**.
    
   - Si no tiene previsto habilitar usuarios externos para telefonía IP empresarial, o si no desea proporcionar conectividad RTC a los usuarios cuando se encuentren fuera de la red interna, haga clic en **siguiente**.
    
9. Haga clic con el botón secundario en el nodo **de Skype empresarial Server 2015** y, a continuación, haga clic en **publicar topología**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definir los puertos de escucha del servidor de mediación

Siga los pasos que se indican en este tema para usar el generador de topología para definir los puertos de escucha que un servidor de mediación o grupo aceptará las conexiones entrantes de una puerta de enlace del mismo nivel.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar los puertos de escucha del servidor de mediación

1. Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.
    
2. En el generador de topología, en el árbol de consola, expanda el nodo **grupos** de mediación y haga clic con el botón secundario en el servidor de mediación creado previamente.
    
3. De forma predeterminada, los puertos de escucha SIP en el servidor de mediación son 5070 para el tráfico de TLS desde Skype empresarial Server y 5067 para el tráfico TLS de homólogos (como puertas de enlace, PBXes o SBCs). El puerto TCP está deshabilitado de forma predeterminada. Debe habilitar el puerto TCP si tiene puertas de enlace que no son compatibles con TLS.
    
4. Especifique el intervalo de puerto de escucha TLS o TCP que desee el servidor de mediación aceptará conexiones entrantes de puertas de enlace RTC.
    
    > [!NOTE]
    > No es necesario indicar este intervalo si no se ha seleccionado **Habilitar puerto TCP**. Este valor es opcional.
  

