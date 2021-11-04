---
title: Definir una puerta de enlace en el Generador de topologías en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: aprenda a definir una puerta de enlace RTC en el Generador de topologías en Skype Empresarial Server.'
ms.openlocfilehash: c3ea9b02f39b3ef93c7c725735599a3940f33641
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753611"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definir una puerta de enlace en el Generador de topologías en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo definir una puerta de enlace RTC en el Generador de topologías en Skype Empresarial Server.
  
Siga estos pasos para usar el Generador de topologías para definir un servidor del mismo nivel con el que puede asociar un servidor de mediación para proporcionar conectividad a la red telefónica conmutada (RTC) para los usuarios habilitados para Telefonía IP empresarial. Un punto del servidor de mediación puede ser una puerta de enlace RTC, una IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP) al que se conecte configurando un tronco SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir un par para el servidor de mediación

1. Iniciar generador de topologías: haga clic en Inicio **,** todos los **programas,** haga clic en **Skype Empresarial Server 2015** y, a continuación, haga clic en **Skype Empresarial Server 2015Topology Builder**.
    
2. En Skype Empresarial Server, el nombre del sitio, Componentes **compartidos,** haga clic con el botón secundario en el nodo Puertas de enlace RTC y, a continuación, haga clic en Nueva puerta de enlace **RTC**.
3. En **Definir la nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si especifica Seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del mismo nivel del servidor de mediación. 
  
4. Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.

5. Defina un tronco raíz para la nueva puerta de enlace RTC. Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace identificada de forma única por la tupla.
    
    {FQDN del servidor de mediación, puerto de escucha del servidor de mediación (TLS o TCP): IP y FQDN de puerta de enlace, puerto de escucha de puerta de enlace}
    
     - Al definir una puerta de enlace RTC en el Generador de topologías, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a la topología.
    
     - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
6. En Puerto de escucha para puerta de enlace **IP/RTC,** escriba el puerto de escucha que usará la puerta de enlace, PBX o SBC para los mensajes SIP del servidor de mediación que se asociarán con el tronco raíz de la puerta de enlace RTC. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control (TCP) y 5067 para la Seguridad de la capa de transporte (TLS) en una puerta de enlace RTC, PBX o SBC. En una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS).
    
7. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Por motivos de seguridad, le recomendamos encarecidamente que implemente un servidor del mismo nivel en el servidor de mediación que pueda usar TLS. 
  
8. En **Servidor de mediación asociado,** seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de esta puerta de enlace RTC.
    
9. En **Puerto del servidor de mediación** asociado , escriba el puerto de escucha que usará el servidor de mediación para los mensajes SIP de la puerta de enlace.
    
    > [!NOTE]
    > Con la compatibilidad con varios troncos Skype Empresarial Server, puede definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varias puertas de enlace RTC. Al definir un tronco, **el** puerto del servidor de mediación asociado debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Skype Empresarial Server y grupos de mediación. Haga clic con el botón secundario en el grupo de servidores de mediación de interés y seleccione **Editar propiedades**. Especifique el intervalo de puertos en el campo **Puertos de escucha**.
  
10. Asegúrese de que el sistema del mismo nivel definido se está ejecutando y usando el FQDN o la dirección IP que especificó. Después, haga clic en **Finalizar**.
    
11. Haga clic con el botón **secundario en el Skype Empresarial Server** y, a continuación, haga clic en Publicar **topología**.
    

