---
title: Definir una puerta de enlace en el generador de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumen: Obtenga información sobre cómo definir una puerta de enlace RTC en el generador de Skype para Business Server.'
ms.openlocfilehash: 40658bf91513701cc41eb6efdb02e3976672f1f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892870"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definir una puerta de enlace en el generador de Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo definir una puerta de enlace RTC en el generador de Skype para Business Server.
  
Siga estos pasos para usar el generador de topología para definir a un par con el que se puede asociar un servidor de mediación para proporcionar conectividad a la red telefónica conmutada (RTC) para los usuarios habilitados para Enterprise Voice. Un elemento del mismo nivel para el servidor de mediación puede ser una puerta de enlace de RTC, un sistema IP-PBX o un controlador de borde de sesión (SBC) para un proveedor de servicio de telefonía de Internet (ITSP) al que se conecta mediante la configuración de un tronco SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir un par para el servidor de mediación

1. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server 2015Topology Builder**.
    
2. En Skype para Business Server, el nombre del sitio, componentes compartidos, haga clic en el nodo de **Puertas de enlace RTC** y, a continuación, haga clic en **Nueva puerta de enlace de RTC**.
3. En **Definir nueva puerta de enlace IP/RTC**, escriba el nombre de dominio completo (FQDN) o la dirección IP del par y haga clic en **Siguiente**.
    
    > [!NOTE]
    > Si especifica seguridad de capa de transporte (TLS) como el tipo de transporte, debe especificar el FQDN en lugar de la dirección IP del par del servidor de mediación. 
  
4. Defina el modo de escucha (IPv4 o IPv6) de la dirección IP de la nueva puerta de enlace RTC y haga clic en **Siguiente**.

5. Defina un tronco raíz para la nueva puerta de enlace RTC. Un tronco es una conexión lógica entre un servidor de mediación y una puerta de enlace de identificación única efectuada mediante tupla.
    
    {FQDN de servidor de mediación, puerto de escucha de servidor de mediación (TLS o TCP): puerta de enlace IP y FQDN, puerto de escucha de puerta de enlace}
    
     - Al definir una puerta de enlace RTC en el generador, debe definir un tronco raíz para agregar correctamente la puerta de enlace de RTC a la topología.
    
     - El tronco raíz no puede quitarse hasta que se quite la puerta de enlace RTC asociada.
    
6. En **Puerto de escucha para puerta de enlace IP/RTC**, escriba el puerto de escucha que va a usar la puerta de enlace, PBX o SBC para los mensajes SIP desde el servidor de mediación que se asociará con el tronco raíz de la puerta de enlace de RTC. (De forma predeterminada, los puertos son 5066 para Protocolo de transmisión de control [TCP] y 5067 para la Seguridad de la capa de transporte [TLS] en una puerta de enlace RTC, PBX o SBC. En una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, los puertos predeterminados son 5081 para TCP y 5082 para TLS).
    
7. En **Protocolo de transporte SIP**, haga clic en el tipo de transporte que usa el par y, a continuación, haga clic en **Aceptar**.
    
    > [!NOTE]
    > Por motivos de seguridad, recomendamos encarecidamente que implemente a un punto para el servidor de mediación que pueda usar TLS. 
  
8. En **Servidor de mediación asociado**, seleccione el grupo de servidores de mediación para asociar con el tronco raíz de esta puerta de enlace de RTC.
    
9. En **puerto de servidor de mediación asociado**, escriba el puerto de escucha que se va a usar el servidor de mediación para mensajes SIP desde la puerta de enlace.
    
    > [!NOTE]
    > Compatible con varios tronco en Skype para Business Server, puede definir varios puertos en el servidor de mediación para la comunicación con varias puertas de enlace de RTC de señalización de SIP. Al definir un tronco, el **puerto del servidor de mediación asociado** debe estar dentro del intervalo de puertos de escucha para el protocolo respectivo permitida por el servidor de mediación. Este intervalo de puertos se define en Skype para Business Server y los grupos de servidores de mediación. Haga clic en el grupo de servidores de mediación de interés y seleccione **Editar propiedades**. Specify the port range in the **Listening ports** field.
  
10. Asegúrese de que el par definido está en ejecución y usa el FQDN o la dirección IP que ha especificado. A continuación, haga clic en **Finalizar**
    
11. Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, luego, haga clic en **Publicar topología**.
    

