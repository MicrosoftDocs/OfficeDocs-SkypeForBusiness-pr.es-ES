---
title: Definir una puerta de enlace en el generador de topologías de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: Aprenda a definir una puerta de enlace RTC en el generador de topologías de Skype empresarial Server.'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286172"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definir una puerta de enlace en el generador de topologías de Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo definir una puerta de enlace RTC en el generador de topologías de Skype empresarial Server.
  
Siga estos pasos para usar el generador de topología para definir un interlocutor con el que pueda asociar un servidor de mediación para proporcionar conectividad a la red de telefonía pública conmutada (RTC) para los usuarios habilitados para telefonía IP empresarial. Un interlocutor al servidor de mediación puede ser una puerta de enlace PSTN, IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet (ITSP) al que se conecta mediante la configuración de un tronco de SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir un par para el servidor de mediación

1. Iniciar generador de topología: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Skype empresarial Server 2015Topology Builder**.
    
2. En Skype empresarial Server, el nombre de su sitio, componentes compartidos, haga clic con el botón derecho en el nodo **puertas de enlace RTC** y, a continuación, haga clic en **nueva puerta de enlace RTC**.
3. En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si especifica la seguridad de la capa de transporte (TLS) como tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del interlocutor del servidor de mediación. 
  
4. Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.

5. Defina un tronco raíz para la nueva puerta de enlace RTC. Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace que se identifica de forma única por la tupla.
    
    {Media Server FQDN, Puerto de escucha del servidor de mediación (TLS o TCP): IP de puerta de enlace y FQDN, Puerto de escucha de la puerta de enlace}
    
     - Al definir una puerta de enlace RTC en el generador de topología, debe definir un tronco raíz para agregar correctamente la puerta de enlace RTC a su topología.
    
     - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
6. En **Puerto de escucha para la puerta de enlace IP/RTC**, escriba el puerto de escucha que usará la puerta de enlace, PBX o SBC para los mensajes SIP del servidor de mediación que se asociará con el tronco raíz de la puerta de enlace RTC. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC. En un equipo de sucursales con la supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS.
    
7. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Por razones de seguridad, le recomendamos encarecidamente que implemente un interlocutor en el servidor de mediación que pueda usar TLS. 
  
8. En **servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociarlo con el tronco raíz de esta puerta de enlace RTC.
    
9. En **Puerto de servidor de mediación asociado**, escriba el puerto de escucha que el servidor de mediación usará para los mensajes SIP de la puerta de enlace.
    
    > [!NOTE]
    > Con la compatibilidad de varios troncales en Skype empresarial Server, puede definir varios puertos de señalización SIP en el servidor de mediación para la comunicación con varias puertas de enlace RTC. Al definir un tronco, el **Puerto de servidor de mediación asociado** debe estar dentro del intervalo de los puertos de escucha para el protocolo respectivo permitido por el servidor de mediación. Este intervalo de puertos se define en Skype empresarial Server y en los grupos de mediación. Haga clic con el botón derecho en el grupo de servidores de mediación de interés y seleccione **Editar propiedades**. Specify the port range in the **Listening ports** field.
  
10. Asegúrese de que el par definido está en ejecución y usa el FQDN o la dirección IP que ha especificado. A continuación, haga clic en **Finalizar**
    
11. Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, luego, haga clic en **Publicar topología**.
    

